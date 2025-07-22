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
- **Transform Controls**: Move/rotate/scale with W/E/R hotkeys
- **Multi-Selection**: Ctrl+click support with grouped transformations
- **Material System**: PBR materials with custom textures, glow effects

#### Ball Management (`balls.html:3542-4500`)
- **Ball Roster**: `raceRoster[]` array manages race participants
- **Ball Sets**: Flexible starting position system (no fixed start platform)
- **Custom Properties**: Color, metalness, roughness, glow, procedural textures
- **Physics Integration**: Cannon.js rigid bodies with material properties

#### Camera System (`balls.html:5624-6200`)
- **5 Camera Modes**: Panning, FPV, Behind, Ride Along, Oncoming
- **Dynamic Following**: Tracks lead marble based on travel distance
- **Camera Sets**: Marble-triggered cinematic camera positions
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
- `toggleCameraMode()` (`balls.html:6141`) - Cycles through camera modes
- `checkCameraZones()` (`balls.html:5624`) - Handles camera set triggers
- `updateCameraTarget()` (`balls.html:2423`) - Focuses camera on selected objects

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

### Save Format
- **JSON Structure**: Complete scene serialization
- **Base64 Assets**: Embedded textures for portability
- **Backward Compatibility**: Supports loading older formats

## Physics Integration

### Materials & Friction
- Water zones, ice surfaces, brake zones use different friction coefficients
- Exact visual-to-physics matching via Trimesh collision detection
- Real-time affector zones modify physics properties continuously

### Collision Detection
- SAP (Sweep and Prune) broadphase algorithm for performance
- Custom finish line detection using contact events
- Camera set trigger zones use bounding box intersections

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