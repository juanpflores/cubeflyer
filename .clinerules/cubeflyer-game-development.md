## Brief overview
Project-specific guidelines for the CubeFly game, a JavaScript-based 3D browser game built with Babylon.JS. These rules cover the established patterns, architecture, and conventions used in this modular game development project.

## Project architecture
- Use modular file structure with separate files for each game component (player.js, barrier.js, scene.js, etc.)
- Follow the GameObject inheritance pattern - all game entities should extend the base GameObject class
- Implement required GameObject methods: init(), onDestroy(), update(deltaTime)
- Use the global state management system via state-manager.js functions (createObject, destroyObject, etc.)
- Load scripts in dependency order in index.html, not as ES6 modules
- When trying to run the game, dont use python, ask teh user to open the index.html within the games folder

## Babylon.JS conventions
- Use BABYLON namespace for all Babylon.JS objects and functions
- Create meshes using BABYLON.MeshBuilder methods
- Use BABYLON.Vector3 for 3D positions and BABYLON.Vector2 for 2D physics vectors
- Apply materials using BABYLON.StandardMaterial and set properties like diffuseColor
- Handle input through BABYLON.DeviceSourceManager for cross-platform compatibility
- Use scene.registerBeforeRender() for game loop updates

## Code style and formatting
- Use tabs for indentation with 4-space tab width (follows .prettierrc configuration)
- Maintain 120 character line width limit
- Use camelCase for variables and functions, PascalCase for classes
- Declare global variables with var, class properties with this.property
- Use const for true constants like physics values and configuration

## Input handling patterns
- Implement multi-platform input support (mouse, touch, keyboard, gamepad)
- Use DeviceSourceManager.onDeviceConnectedObservable for device detection
- Handle input events through onInputChangedObservable callbacks
- Support gamepad input via GamepadManager.onGamepadConnectedObservable
- Centralize input handling logic within relevant game object classes

## Game development practices
- Use physics-based movement with gravity and velocity vectors
- Implement collision detection through testCollision methods on game objects
- Handle game state transitions (menu, playing, game over) through object creation/destruction
- Use timer-based spawning systems for dynamic content generation
- Implement proper cleanup in onDestroy() methods to prevent memory leaks

## Browser-based development workflow
- Test by opening game/index.html directly in browser
- Use browser developer tools (F12) for debugging and console output
- No build process required - all dependencies loaded via CDN
- Support cross-platform compatibility (desktop, mobile, tablet)
- Use console.log() for debugging output during development

## File organization
- Keep all game source files in game/src/ directory
- Place assets like textures in game/img/ directory
- Use descriptive filenames that match their primary class or function
- Maintain clear separation between game logic, rendering, and UI components
- Follow the established script loading order in index.html
