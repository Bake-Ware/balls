# 🏁 3D Marble Race Game

A complete 3D marble race game and track editor built with Three.js and Cannon.js physics engine. Create custom marble tracks, design unique marbles, and watch epic races unfold in real-time!

[DEMO](https://bake-ware.github.io/balls/balls.html)

![Marble Race Demo](https://img.shields.io/badge/Status-Complete-brightgreen) ![Three.js](https://img.shields.io/badge/Three.js-r165-blue) ![Physics](https://img.shields.io/badge/Physics-Cannon--ES-orange)

## 🎮 Features

### 🏗️ Advanced Track Editor
- **Track Pieces**: Start platform, straight tracks, curves, end platform, pipes, half-pipes, quarter bowls
- **Obstacles**: Pinned balls, pyramids, cylinders, cubes, prisms, custom .obj models
- **Physics Affectors**: Water zones, zero gravity, moon gravity, accelerators, brakes, ice surfaces
- **Camera Sets**: Marble-triggered camera control points with 4 follow modes and position capture
- **Multi-Selection**: Ctrl+click to select multiple pieces and transform them together
- **Material Editor**: Customize color, transparency, metalness, roughness, glow effects, and textures
- **Custom Textures**: Upload your own textures with base64 encoding for portability
- **Transform Controls**: Move, rotate, and scale pieces with W/E/R hotkeys
- **Snap to Grid**: Hold Shift while transforming for precise alignment
- **ViewCube Navigation**: 3D orientation cube for quick orthographic view switching (Front, Back, Left, Right, Top, Bottom)
- **Real-time Orientation**: ViewCube reflects current camera position with smooth transitions

### ⚽ Ball Maker System
- **Complete Customization**: Color, metalness, roughness, glow intensity, glow color
- **Procedural Textures**: Polka dots, stripes, marble patterns
- **Ball Roster**: Manage race participants with visual previews
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

### 💾 Save/Load System
- **Complete Persistence**: Tracks, materials, skyboxes, custom balls all saved
- **JSON Format**: Human-readable save files
- **Base64 Assets**: Textures and skyboxes embedded for portability
- **Backward Compatibility**: Supports loading older track formats

## 🚀 Getting Started

### Quick Start
1. Open `balls.html` in a modern web browser
2. Use the toolbar to add track pieces (Start → Straight → Curve → End)
3. Click "Start Race!" to begin
4. Use "Camera" button to cycle through viewing modes

### Track Building
1. **Add Pieces**: Use dropdown selector to add track segments and obstacles
2. **Enable Transform**: Click "Enable Transform" and select pieces to move/rotate/scale
3. **Multi-Select**: Hold Ctrl and click multiple pieces to transform together
4. **Snap Controls**: Hold Shift while transforming for precise grid alignment
5. **Materials**: Select a piece and click "Edit Material" to customize appearance
6. **Affector Zones**: Add physics-modifying zones to create unique track effects
7. **Camera Sets**: Place camera control points that activate when marbles pass through
8. **Pathing**: Record movement paths for animated track pieces
9. **Save**: Use "Save Track" to export your creation

### Ball Customization
1. **Ball Maker**: Click "Ball Maker" to design custom marbles
2. **Properties**: Adjust color, shine, glow, and texture patterns
3. **Ball Roster**: Click "Manage Roster" to organize race participants
4. **Random Balls**: Use "Add Random" to generate varied marbles quickly

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
- **Event-Driven**: Clean separation between UI interactions and game logic
- **Affector System**: Real-time physics modification zones with continuous effect application
- **Animation Engine**: Keyframe-based pathing system with multiple playback modes
- **Post-Processing Pipeline**: Bloom effects with emissive materials for enhanced visuals
- **Real-time UI Updates**: Instant feedback system without apply buttons for smooth editing
- **3D Navigation**: ViewCube with spherical coordinate camera positioning

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
- **Mouse**: Click to select pieces
- **Ctrl+Click**: Multi-select pieces
- **W/E/R**: Switch transform modes (translate/rotate/scale)
- **Mouse Drag**: Transform selected pieces
- **Middle Mouse**: Pan camera
- **Scroll**: Zoom camera

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

## 🐛 Troubleshooting

### Performance Issues
- Reduce number of marbles in roster
- Use simpler track designs
- Disable glow effects on materials
- Close other browser tabs

### Physics Problems
- Ensure track pieces are connected properly
- Check for overlapping geometry
- Verify start/end platforms are present
- Use "Edit Material" to adjust piece materials

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
