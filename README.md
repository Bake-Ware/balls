# 🏁 3D Marble Race Game

A complete 3D marble race game and track editor built with Three.js and Cannon.js physics engine. Create custom marble tracks, design unique marbles, and watch epic races unfold in real-time!

[DEMO](https://bake-ware.github.io/balls/balls.html)

![Marble Race Demo](https://img.shields.io/badge/Status-Complete-brightgreen) ![Three.js](https://img.shields.io/badge/Three.js-r165-blue) ![Physics](https://img.shields.io/badge/Physics-Cannon--ES-orange)

## 🎮 Features

### 🏗️ Advanced Track Editor
- **Track Pieces**: Start platform, straight tracks, curves, end platform, pipes, half-pipes, quarter bowls
- **Ball Sets**: Flexible marble starting positions - place and rotate starting line formations anywhere
- **Obstacles**: Pinned balls, pyramids, cylinders, cubes, prisms, custom .obj models
- **Physics Affectors**: Water zones, zero gravity, moon gravity, accelerators, brakes, ice surfaces
- **Camera Sets**: Marble-triggered camera control points with 4 follow modes and position capture
- **📋 Three-Level Object Tree**: Hierarchical organization (Main Type → Specific Type → Instances) with collapsible categories
- **Multi-Selection**: Ctrl+click to select multiple pieces and transform them together
- **🔄 Smart Duplication**: Duplicate button + Ctrl+drag to copy while moving
- **📦 Blueprint Export**: Export selected pieces as merged OBJ files for sharing track sections
- **Material Editor**: Customize color, transparency, metalness, roughness, glow effects, and textures
- **Custom Textures**: Upload your own textures with base64 encoding for portability
- **Transform Controls**: Move, rotate, and scale pieces with W/E/R hotkeys
- **Snap to Grid**: Hold Shift while transforming for precise alignment
- **ViewCube Navigation**: 3D orientation cube for quick orthographic view switching (Front, Back, Left, Right, Top, Bottom)
- **Real-time Orientation**: ViewCube reflects current camera position with smooth transitions

### 🖌️ Surface Painting System
- **🎨 Face-Level Painting**: Click individual faces on any 3D object to paint them with custom colors
- **Per-Face Material Control**: Each face can have unique color, transparency, metalness, roughness, and glow properties
- **🌈 Vertex Color System**: Advanced vertex coloring with full PBR material support
- **Real-time Visual Feedback**: Immediate color application with smooth transitions
- **Procedural Textures**: Apply polka dots, stripes, marble patterns, or upload custom textures to individual faces
- **🧽 Selective Clearing**: Clear all face paint from selected objects or start fresh anytime
- **Material Preservation**: Original object materials are preserved and can be restored
- **Multi-Object Support**: Paint faces across different object types (track pieces, obstacles, custom models)
- **🎭 Creative Customization**: Create unique artistic designs, racing stripes, team colors, or decorative patterns
- **Precision Control**: Crosshair cursor for accurate face selection and painting
- **Undo Functionality**: Clear all paint button to reset objects to original appearance

### ⚽ Ball Maker & Advanced Placement System
- **Complete Customization**: Color, metalness, roughness, glow intensity, glow color
- **Procedural Textures**: Polka dots, stripes, marble patterns
- **Ball Roster**: Manage race participants with visual previews
- **🏁 Flexible Ball Placement**: Use Ball Set pieces to define starting positions anywhere on track
- **📍 Real-Time Visual Previews**: Ball Sets show semi-transparent previews of all roster balls in formation
- **🔄 Dynamic Multi-Position Spawning**: All roster balls spawn in line formations at each Ball Set location
- **⚙️ Rotational Control**: Rotate Ball Sets to orient starting lines in any direction
- **🎯 Distance-Based Lead Selection**: Camera follows the marble that has traveled furthest from its starting position
- **⚡ Same-Type Collision Switching**: When marbles of the same type touch, camera switches to the one that traveled further
- **🏃 Intelligent Ball Tracking**: Each marble tracks its type, starting position, and travel distance for advanced camera logic
- **Random Generation**: Create random balls with varied properties
- **Material Physics**: Realistic rendering with PBR materials

### 📹 Dynamic Camera System
- **5 Camera Modes**: 
  - **Panning**: Orbiting camera around lead marble
  - **FPV**: First-person view from marble perspective
  - **Behind**: Chase camera following behind the marble
  - **Ride Along**: Smooth tracking at diagonal offset
  - **Oncoming**: Camera positioned ahead looking back
- **📷 Camera Set Blocks**: Marble-triggered camera control points
  - **Static Mode**: Camera jumps to preset position and stays there
  - **Follow Mode**: Camera follows triggering marble from preset offset
  - **Rigid Mode**: Camera maintains exact offset with no smoothing
  - **Smooth Mode**: Camera smoothly interpolates to follow marble
  - **Trigger Zones**: Rectangular activation areas that marbles pass through
  - **Persistent Control**: Once activated, camera sets maintain control until overridden
  - **Position Capture**: Save current viewport camera position with one click
- **Smooth Transitions**: Cubic easing when switching between lead marbles
- **Manual Override**: User can take control with mouse/orbit controls or Camera button
- **Smart Reset**: Camera set control automatically resets when users manually change camera modes

### 📋 Advanced Object Management System
- **📁 Three-Level Hierarchy**: Main Type → Specific Type → Individual Instances
  - **Track Pieces**: Start, straight, curve, end, pipe, half-pipe, quarter-bowl, ball-set
  - **Obstacles**: Ball, pyramid, cylinder, cube, prism
  - **Affector Zones**: Water, gravity, accelerator, brake, ice zones
  - **Lighting**: Spot lights, point lights, strobes, particle generators
  - **Camera System**: Camera set pieces for dynamic filming
  - **Custom**: Imported .obj files and other custom objects
- **🔍 Smart Organization**: Objects automatically categorized by type and function
- **📊 Instance Counting**: Shows quantity of each object type with real-time updates
- **🎯 Multi-Level Selection**: Click main categories, specific types, or individual instances
- **✏️ Custom Naming**: Double-click any object to give it a custom name
- **💾 Persistent Names**: Custom object names saved and loaded with track files
- **🔄 Collapsible Interface**: Each hierarchy level remembers its expansion state
- **🎨 Visual Feedback**: Selected objects highlighted across both tree and 3D scene
- **⌨️ Keyboard Integration**: Full support for Ctrl+click multi-selection
- **🔍 Type Filtering**: Easily find all instances of a specific piece type

### 🌌 Physics Affector Zones
- **💧 Water Zone**: Simulates buoyancy and water resistance
- **🌌 Zero Gravity**: Removes gravitational effects completely
- **🌙 Moon Gravity**: Reduced gravity simulation (1/6th Earth gravity)
- **⚡ Accelerator**: Speed boost zones for dramatic acceleration
- **🛑 Brake Zone**: Deceleration areas to slow down marbles
- **🧊 Ice Zone**: Ultra-low friction surfaces for sliding effects
- **Intensity Control**: Adjustable effect strength (0-10 scale)
- **Real-time Physics**: Effects applied continuously while marbles are in zones

### ⚙️ Advanced Pathing System
- **Path Recording**: Record keyframe positions for animated track pieces
- **Movement Types**: Translation, rotation, and scaling animations
- **Playback Modes**:
  - 🔄 **Loop**: Continuous repeating movement
  - 🔃 **Loop Reversible**: Back-and-forth oscillation
  - 👆 **Once on Touch**: Trigger animation when marble touches piece
  - ⏯️ **Manual Control**: User-activated animations
- **Speed Control**: Adjustable playback speed for perfect timing
- **Multi-point Paths**: Create complex movement sequences with multiple keyframes

### 🌌 Environment & Lighting System
- **Skybox Selector**: Procedural skyboxes (Sunset, Ocean, Space, Dawn)
- **Custom Upload**: Upload 360° panoramic images
- **Background Color Control**: Customizable world background color with real-time updates
- **Dynamic Lighting**: 4 light types (Spot, Point, Strobe, Directional) with real-time controls
- **Advanced Particle Systems**: 5 particle shapes (Point, Star, Square, Circle, Spark) and 5 themed types (Fire, Water, Electrical, Steam, Wind)
- **Bloom Post-Processing**: Enhanced particle effects with glowing materials and bloom rendering
- **Real-time Updates**: All lighting and particle settings update instantly without apply buttons
- **Environment Lighting**: Skyboxes affect scene lighting and reflections
- **Save Integration**: Skyboxes, lighting, and particle settings saved with track files

### 🏆 Tournament & Race Features
- **Tournament Mode**: Multi-track tournaments with automatic progression
- **Individual Track Loading**: Build tournaments by loading tracks one at a time
- **Comprehensive Scoring**: 3 points for 1st, 2 points for 2nd, 1 point for 3rd
- **Tournament Results**: Final leaderboard showing overall winners
- **Race Timing**: 30-second delay after first marble finishes before advancing
- **Real-time Physics**: Accurate marble physics with Cannon.js
- **Instant Results**: Race results appear immediately when first marble finishes
- **Dynamic Updates**: Results update live as more marbles finish
- **Ball Nameplates**: Floating name tags that always face the camera
- **Finish Detection**: Touch-based finish line detection with frame interpolation
- **Randomized Starting**: Marbles start in random positions each race

### 📋 Object Management & Export System
- **📜 Object Selection Tree**: Hierarchical list showing all scene objects with visual icons
- **🎯 Smart Selection**: Click to select single objects, Ctrl+click for multi-selection
- **✏️ Object Renaming**: Double-click tree items to give pieces custom names
- **🖱️ Draggable Panel**: Drag the tree panel by its header to position it anywhere on screen
- **🔄 Enhanced Duplication**: 
  - **📋 Duplicate Button**: Creates copies 2 units above originals with all properties
  - **⌨️ Ctrl+Drag**: Hold Ctrl while dragging to move copies instead of originals
- **📦 Blueprint Export**: Export selected pieces as merged OBJ files
  - **🎯 Relative Positioning**: All pieces positioned relative to selection center
  - **📝 Custom Naming**: Dialog for naming blueprint files before export
  - **🔗 Merged Geometry**: All selected objects combined into single OBJ object
  - **📊 Material Info**: Material properties preserved as comments in export
- **🔍 Object Information**: Tree shows piece types, special properties, and visual status
- **⚡ Real-time Updates**: Object tree updates automatically when objects are added/removed

### 💾 Save/Load System
- **Complete Persistence**: Tracks, materials, skyboxes, custom balls all saved
- **JSON Format**: Human-readable save files
- **Base64 Assets**: Textures and skyboxes embedded for portability
- **Backward Compatibility**: Supports loading older track formats

## 🚀 Getting Started

### Quick Start
1. Open `balls.html` in a modern web browser
2. Use the toolbar to add track pieces (Straight → Curve → End)
3. Add "🏁 Ball Set" pieces where you want marbles to start racing
4. Click "Start Race!" to begin (marbles will spawn at all Ball Set locations)
5. Use "Camera" button to cycle through viewing modes

### Track Building
1. **Add Pieces**: Use dropdown selector to add track segments and obstacles
2. **Add Ball Sets**: Place "🏁 Ball Set" pieces where you want marbles to start
3. **Object Management**: Use "📋 Object Tree" panel to select and organize pieces
4. **Multi-Select**: Hold Ctrl and click pieces in tree or 3D view for multi-selection
5. **Smart Duplication**: Use "📋 Duplicate" button or Ctrl+drag to copy pieces
6. **Transform Controls**: Move/rotate/scale with W/E/R hotkeys, Shift for grid snap
7. **Materials**: Select pieces and click "🎨 Object" to customize appearance
8. **Surface Painting**: Select any object and click "🖌️ Face Paint" to paint individual faces with custom colors and textures
9. **Export Blueprints**: Select multiple pieces and click "📦 Export Blueprint" to save as OBJ
10. **Special Features**: Add affector zones, camera sets, lights, and particle effects
11. **Save**: Use "💾 Save" to export your complete track

### Ball Customization & Racing
1. **Ball Maker**: Click "⚽ Balls" to design custom marbles
2. **Properties**: Adjust color, shine, glow, and texture patterns
3. **Ball Roster**: Click "👥 Roster" to manage race participants
4. **Random Generation**: Use "Add Random" to generate varied marbles quickly
5. **Ball Placement**: Place "🏁 Ball Set" pieces anywhere on your track
6. **Preview System**: Ball Sets show transparent previews of all roster balls
7. **Dynamic Racing**: All roster balls spawn at each Ball Set location in line formation

### Racing
1. **Start Race**: Click "Start Race!" to begin simulation
2. **Camera Control**: Toggle between 5 different camera modes during race
3. **Results**: Results appear instantly when first marble finishes
4. **Restart**: Use "Restart Race" to run again with randomized starting positions

## 🛠️ Technical Details

### Built With
- **Three.js r165**: 3D rendering and graphics
- **Cannon-ES**: Physics simulation
- **WebGL**: Hardware-accelerated rendering
- **Canvas API**: Procedural texture generation
- **EffectComposer**: Post-processing pipeline for bloom effects
- **UnrealBloomPass**: Advanced particle glow rendering

### Architecture
- **Modular Design**: Separate systems for editor, physics, rendering, UI
- **Real-time Physics**: 60 FPS physics simulation with visual synchronization
- **Material System**: PBR (Physically Based Rendering) materials with custom shaders
- **Vertex Color System**: Advanced per-face painting with BufferGeometry vertex color attributes
- **Event-Driven**: Clean separation between UI interactions and game logic
- **Affector System**: Real-time physics modification zones with continuous effect application
- **Animation Engine**: Keyframe-based pathing system with multiple playback modes
- **Post-Processing Pipeline**: Bloom effects with emissive materials for enhanced visuals
- **Real-time UI Updates**: Instant feedback system without apply buttons for smooth editing
- **3D Navigation**: ViewCube with spherical coordinate camera positioning
- **Face-Level Rendering**: Individual face material control with raycasting for precise selection

### Performance
- **SAP Broadphase**: Advanced collision detection algorithm for better performance
- **Optimized Physics**: Efficient collision detection using exact geometry
- **LOD System**: Adaptive detail based on viewing distance
- **Texture Caching**: Smart texture management and reuse
- **Memory Management**: Proper cleanup of physics bodies and materials
- **Zone Optimization**: Efficient affector zone detection and application

## 🎯 Advanced Features

### Multi-Selection System
```javascript
// Ctrl+click to select multiple pieces
// Transform controls automatically create group
// Relative positions maintained during transforms
```

### Custom Material Pipeline
```javascript
// Support for:
// - Base color and transparency
// - Metalness and roughness (PBR)
// - Emissive glow effects
// - Custom texture upload
// - Procedural pattern generation
```

### Physics Integration
```javascript
// Exact visual-to-physics matching
// Trimesh collision for complex geometry
// Real-time physics updates
// Finish line collision detection
```

## 📁 File Structure

```
balls/
├── balls.html              # Main application (complete game)
├── README.md               # This file
├── marble-track (20).json  # Example track save file
├── BookCovers0135_1_M.jpg  # Texture asset
├── moon_lab.jpg           # Skybox asset
└── book.*                 # 3D model assets
```

## 🎮 Controls

### Editor Mode
- **Mouse**: Click to select pieces (3D view or Object Tree)
- **Ctrl+Click**: Multi-select pieces (3D view or Object Tree)
- **Double-Click**: Rename pieces in Object Tree
- **Ctrl+Drag**: Duplicate and move copies of selected pieces
- **Shift+Drag**: Grid-snapped movement for precise alignment
- **W/E/R**: Switch transform modes (translate/rotate/scale)
- **Del**: Delete selected pieces
- **Mouse Drag**: Transform selected pieces
- **Middle Mouse**: Pan camera
- **Scroll**: Zoom camera

### Surface Painting Mode
- **🖌️ Face Paint Button**: Activate face painting mode (select object first)
- **Mouse Click**: Paint individual faces with current paint settings
- **Crosshair Cursor**: Precise face selection targeting
- **🗑️ Clear All**: Remove all face paint from selected object
- **❌ Close**: Exit face painting mode and re-enable transform controls

### Race Mode
- **Camera Button**: Cycle through camera modes
- **Middle Mouse**: Pan during race (when enabled)
- **Mouse Drag**: Manual camera control (overrides auto-camera)

## 🎨 Customization Examples

### Creating a Glow Ball
1. Open Ball Maker
2. Set bright color (e.g., cyan #00ffff)
3. Increase glow intensity to 0.8
4. Set glow color to white #ffffff
5. Choose metalness 0.9 for extra shine

### Building a Loop Track
1. Add Start platform
2. Add Straight pieces to build up
3. Add Pipe pieces for the loop
4. Use material editor to make pipes transparent
5. Add End platform after loop

### Creating Custom Surface Designs with Face Painting
1. Select any track piece or obstacle you want to customize
2. Click "🖌️ Face Paint" to open the Surface Painting panel
3. Choose your paint color and adjust transparency, metalness, roughness
4. Set glow intensity and glow color for emissive effects
5. Select texture type: None, Upload Custom, Polka Dots, Stripes, or Marble
6. Click individual faces on the 3D object to apply your custom paint
7. Each face can have completely different materials and colors
8. Use "🗑️ Clear All" to reset the object to its original appearance
9. Perfect for creating racing stripes, team colors, artistic patterns, or unique designs

### Night Race Scene with Lighting Effects
1. Open Skybox Selector and choose "Space" skybox
2. Add Spot Lights along the track for dramatic lighting
3. Add Particle Generators with "Fire" type for ambient effects
4. Set track pieces to have glow materials
5. Create glowing balls for visibility
6. Use Strobe Lights for exciting race atmosphere
7. Start race for cosmic marble action!

### Creating Dynamic Particle Effects
1. Add a Particle Generator from the piece selector
2. Select the generator and open Object Editor
3. Choose "Electrical" type for sparking effects
4. Adjust particle count to 500 for density
5. Set "Spark" shape for realistic electrical look
6. Combine with Point Lights for enhanced illumination

### Custom Environment Setup
1. Open Lighting controls
2. Set custom Background Color (e.g., deep blue #001122)
3. Adjust Ambient and Directional light intensity
4. Add multiple light sources for complex shadows
5. Use ViewCube to check lighting from all angles

### Creating Cinematic Camera Sequences
1. Add Camera Set pieces from "Camera Controls" section
2. Position camera sets along the track where you want dramatic views
3. Select each camera set and click "📸 Capture Current Camera Position"
4. Choose follow modes: Static for fixed shots, Follow for dynamic tracking
5. Test during races - marbles trigger camera changes as they pass through
6. Use multiple camera sets to create complex filming sequences

### Advanced Object Management
1. Open "📋 Object Tree" panel to see all scene objects
2. Click object names to select them instantly
3. Ctrl+click multiple objects for batch operations
4. Use "📋 Duplicate" to copy with all properties preserved
5. Hold Ctrl while dragging to move copies instead of originals
6. Select multiple pieces and use "📦 Export Blueprint" to save as OBJ file

### Creating Reusable Track Sections
1. Build a track section (e.g., spiral loop, jump ramp, tunnel)
2. Select all pieces using Object Tree or Ctrl+click in 3D view
3. Click "📦 Export Blueprint" button (appears when multiple pieces selected)
4. Name your blueprint (e.g., "spiral_loop", "mega_jump")
5. Share the OBJ file with others or import into 3D modeling software
6. Use exported blueprints as reference for rebuilding complex sections

### Flexible Racing Setup
1. Delete old Start platform pieces (no longer needed)
2. Add "🏁 Ball Set" pieces from the piece selector
3. Position Ball Sets anywhere on your track - multiple start points supported
4. Rotate Ball Sets to orient starting line formations in any direction
5. Ball Sets show transparent previews of all roster marbles
6. During races, all marbles spawn in neat lines at each Ball Set location
7. Great for creating multi-stage races, parallel tracks, or elimination rounds

### Advanced Object Organization
1. Open "📋 Object Tree" panel to see all scene objects organized hierarchically
2. Expand main categories like "Track Pieces" to see all track-related objects
3. Expand specific types like "Straight" to see all individual straight pieces
4. Click any object in the tree to select it instantly in the 3D scene
5. Double-click objects to rename them with custom names
6. Use Ctrl+click to multi-select objects of different types
7. Each level remembers its expansion state for persistent organization
8. Perfect for managing complex tracks with hundreds of objects

## 🐛 Troubleshooting

### Performance Issues
- Reduce number of marbles in roster
- Use simpler track designs
- Disable glow effects on materials
- Close other browser tabs

### Physics Problems
- Ensure track pieces are connected properly
- Check for overlapping geometry
- Verify Ball Set pieces are placed where you want marbles to start
- Use "Edit Material" to adjust piece materials
- Check Object Tree to identify and fix problematic pieces

### Saving/Loading
- Ensure browser allows file downloads
- Large custom textures may increase file size
- Check console for any error messages

## 🤝 Contributing

This is a complete, self-contained marble race game. The entire application is in `balls.html` for easy sharing and modification.

### Development
- Edit `balls.html` directly
- Use browser dev tools for debugging
- Test physics changes carefully
- Maintain backward compatibility for save files

## 📄 License

This project is open source. Feel free to modify and share!

## 🎉 Credits

Created with advanced 3D graphics and physics simulation. Features professional-grade track editing, material systems, and racing mechanics.

**Technologies:**
- Three.js for 3D rendering
- Cannon-ES for physics simulation
- Modern WebGL and Canvas APIs
- Advanced mathematical algorithms for smooth camera transitions

---

*🤖 Generated with [Claude Code](https://claude.ai/code)*

*Co-Authored-By: Claude <noreply@anthropic.com>*
