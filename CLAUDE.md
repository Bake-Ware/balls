# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a complete 3D marble race game and track editor built as a single HTML file (`balls.html`) using Three.js and Cannon-ES physics. The entire application is self-contained with no build process or external dependencies beyond CDN imports.

## Core Architecture

### Single-File Structure
- **Main File**: `balls.html` - Contains the complete application (HTML, CSS, JavaScript)
- **No Build Process**: Direct browser execution, no compilation or bundling required
- **Self-Contained**: All code, styles, and logic in one file for easy sharing

### Key Systems

#### 3D Rendering & Physics (`balls.html:1074-1200`)
- **Three.js r165**: 3D scene management, rendering, materials
- **Cannon-ES**: Physics simulation with SAP broadphase for performance
- **Post-processing**: Bloom effects via EffectComposer and UnrealBloomPass
- **Global Variables**: `scene`, `camera`, `renderer`, `world`, `trackPieces[]`, `marbles[]`

#### Track Editor System (`balls.html:1253-1656`)
- **Piece Types**: Start platform, straight, curve, end, pipes, half-pipes, obstacles
- **Custom Curve Builder**: Mathematical curve creation with 3D rotation parameters
- **Face Painting System**: Advanced cascade/flood-fill painting with triangle adjacency
- **Transform Controls**: Move/rotate/scale with W/E/R hotkeys
- **Multi-Selection**: Ctrl+click support with grouped transformations
- **Material System**: PBR materials with custom textures, glow effects

#### Ball Management (`balls.html:3542-4500`)
- **Ball Roster**: `raceRoster[]` array manages race participants
- **Ball Sets**: Flexible starting position system (no fixed start platform)
- **Custom Properties**: Color, metalness, roughness, glow, procedural textures
- **Physics Integration**: Cannon.js rigid bodies with material properties

#### Camera System (`balls.html:5624-6200`)
- **Camera Mode Dropdown**: Replaced toggle button with dropdown menu for mode selection
- **5 Camera Modes**: Panning, FPV, Behind, Ride Along, Oncoming
- **Dual Dropdown UI**: Camera dropdowns in both left and right toolbar positions (synced)
- **Enhanced Lead Tracking**: Improved marble closest-to-finish detection logic
- **Dynamic Following**: Tracks lead marble based on travel distance
- **Camera Sets**: Marble-triggered cinematic camera positions with follow modes
- **ViewCube**: 3D navigation with orthographic view switching

#### Object Management (`balls.html:7000-8000`)
- **Hierarchical Tree**: Three-level organization (Main Type → Specific Type → Instances)
- **Multi-Selection**: Object tree and 3D view synchronization
- **Custom Naming**: Persistent object names stored in `pieceNames` Map
- **Blueprint Export**: OBJ file export for selected pieces

## Development Commands

### Testing the Application
```bash
# Open directly in browser (no build required)
open balls.html
# or
firefox balls.html
```

### File Operations
```bash
# View track save files
ls *.json

# Check assets
ls *.jpg *.obj *.mtl *.dae
```

## Key Functions & Entry Points

### Core Initialization
- `init()` (`balls.html:1123`) - Sets up Three.js scene, physics world, controls
- `setupLighting()` (`balls.html:1198`) - Configures ambient and directional lighting
- `setupPhysicsMaterials()` (`balls.html:1229`) - Creates Cannon.js material definitions

### Track Building
- `addPiece(type, transform, customModelData)` (`balls.html:1253`) - Creates new track pieces
- `updatePhysicsForPiece(piece)` (`balls.html:1555`) - Syncs visual/physics geometry
- `getPieceConfig(type)` (`balls.html:1656`) - Returns piece specifications

### Race Management
- `startRace()` (`balls.html:3542`) - Initiates marble physics simulation
- `restartRace()` (`balls.html:3572`) - Resets marbles to starting positions
- `updateRaceResults()` (`balls.html:4132`) - Updates live race standings

### Camera Control
- **Camera Mode Dropdowns** (`balls.html:3791-3804`) - Event handlers for dual dropdown system
- `toggleCameraMode()` (`balls.html:8394`) - Legacy function, now uses dropdown selection
- `checkCameraZones()` (`balls.html:5624`) - Handles camera set triggers
- `updateCameraTarget()` (`balls.html:2423`) - Focuses camera on selected objects

### Face Painting System
- `toggleFacePaintMode()` (`balls.html:7202`) - Activates face painting interface
- `paintFace(mesh, faceIndex)` (`balls.html:7258`) - Applies paint to individual faces
- `findSimilarFaces()` (`balls.html:7594`) - Cascade painting with angle threshold
- `applyPerFaceMaterials()` (`balls.html:7330`) - Creates face-specific materials
- `clearAllFacePaint()` (`balls.html:7744`) - Removes all face paint from object

### Custom Curve Builder
- `showCustomCurveDialog()` (`balls.html:4434`) - Opens curve creation interface
- `createCustomCurve()` (`balls.html:4469`) - Generates mathematical curves with 3D rotation
- `CustomArcCurve` class (`balls.html:2356`) - Three.js curve implementation for custom geometry

## Data Structures

### Track Pieces
```javascript
// Each piece has:
{
    mesh: THREE.Mesh,           // Visual representation
    body: CANNON.Body,          // Physics body
    type: string,               // Piece category
    userData: {
        pieceType: string,      // Specific type
        // Additional properties based on type
    }
}
```

### Marbles
```javascript
// Marble objects contain:
{
    mesh: THREE.Mesh,           // Visual sphere
    body: CANNON.Body,          // Physics body
    nameplate: THREE.Sprite,    // Floating name label
    properties: {               // Custom appearance
        color, metalness, roughness, glow, etc.
    }
}
```

### Face Paint Data
```javascript
// Face painting metadata stored in mesh.userData:
{
    paintedFaces: Map,              // faceIndex -> paint properties
    originalMaterial: Material,     // Pre-paint material for restoration
    materials: Array,               // Multi-material array for painted faces
    faceMaterials: Map             // faceIndex -> material mapping
}
```

### Custom Curve Data
```javascript
// Custom curve pieces store mathematical parameters:
{
    customData: {
        angleX, angleY, angleZ,     // 3D rotation parameters in radians
        radiusX, radiusY, radiusZ,  // Curve dimensions
        segments,                   // Geometry resolution
        clockwise: boolean          // Curve direction
    }
}
```

### Save Format
- **JSON Structure**: Complete scene serialization
- **Face Paint Persistence**: Painted faces and materials saved per object
- **Custom Curve Storage**: Mathematical parameters for curve reconstruction
- **Base64 Assets**: Embedded textures for portability
- **Backward Compatibility**: Supports loading older formats

## Physics Integration

### Materials & Friction
- Water zones, ice surfaces, brake zones use different friction coefficients
- Exact visual-to-physics matching via Trimesh collision detection
- Real-time affector zones modify physics properties continuously
- **Enhanced Stability**: Improved solver iterations and contact material properties

### Collision Detection
- SAP (Sweep and Prune) broadphase algorithm for performance
- Custom finish line detection using contact events
- Camera set trigger zones use bounding box intersections
- **Rotational Physics**: Proper rotation application to track pieces for accurate collision

### Lead Marble Tracking
- **Distance-Based Logic**: Tracks marble closest to finish line (not furthest from start)
- **Frame-Accurate Detection**: Improved marble position calculations for race results

## Important Notes

### Performance Considerations
- Large numbers of marbles impact physics simulation
- Complex geometry increases collision detection overhead
- Particle systems and bloom effects are GPU-intensive

### File Dependencies
- Three.js and Cannon-ES loaded from CDN
- All textures/models should be base64 encoded for portability
- No external build tools or package managers required

### Debugging
- Use browser developer tools console for error messages
- Physics debug renderer available but disabled by default
- Object tree panel shows real-time scene hierarchy for debugging
- **Face Paint Mode**: Crosshair cursor and visual feedback for face selection debugging
- **Camera Dropdown Sync**: Both toolbar dropdowns stay synchronized for UI state debugging