# Air Defence System

A real-time interactive air defence game built with **OpenGL (GLUT)** featuring dynamic radar, guided missiles, and particle effects.

## Overview

The Air Defence System is a graphical simulation where you defend against incoming enemy drones using guided missiles. The game features:

- **Real-time Radar System** - Circular radar display that detects incoming drones within range
- **Missile Defense** - Automatic or manual missile targeting system
- **Dynamic Graphics** - Parallax cloud layers, road traffic, street lighting, and procedurally generated scenery
- **Particle Effects** - Realistic explosions with sparks, smoke, and debris
- **Score Tracking** - Earn points by destroying enemy drones

## Technical Details

### Technology Stack

- **Graphics API**: OpenGL (GLUT)
- **Language**: C++
- **Display Size**: 1200x700 pixels
- **Platform**: Windows/Linux/macOS (with OpenGL support)

### Key Features

#### Game Entities

- **Drones** (MAX_DRONES: 6) - Enemy aircraft moving across the screen
- **Missiles** (MAX_MISSILES: 10) - Guided projectiles targeting drones
- **Explosions** (MAX_EXPLOSIONS: 10) - Blast effects with expanding radius
- **Particles** (MAX_PARTICLES: 80) - Individual spark, smoke, and debris particles
- **Vehicles** (5) - Road traffic (cars and motorcycles)
- **Clouds** (20) - Parallax scrolling background layers

#### Core Systems

- **Radar Subsystem**
  - Detection range: 420 units (world-space)
  - Display radius: 88 units (screen-space)
  - Continuous rotation for threat scanning
- **Physics Simulation**
  - Euclidean distance calculations for collision detection
  - Velocity-based particle dynamics
  - Guided missile targeting system

- **Graphics Rendering**
  - Procedural terrain with 200 stars and 20 street lights
  - Color-coded vehicles and entities
  - Smooth animations and frame-based updates

## Building & Running

### Prerequisites

- C++ compiler (g++, clang, or MSVC)
- OpenGL development libraries
- GLUT library (FreeGLUT recommended)

### Compilation

```bash
g++ Main.cpp -o AirDefenceSystem -lGL -lGLU -lglut -lm
```

### Execution

```bash
./AirDefenceSystem
```

## Game Mechanics

### Scoring

Destroy drones to earn points. Your current score is displayed on-screen.

### Gameplay Loop

1. Drones spawn automatically every 200 frames
2. Radar detects drones within 420 units
3. Assign missiles to target detected drones
4. Explosions occur when missiles hit their targets
5. Particle effects provide visual feedback
6. Highway traffic and background provide immersion

### Controls

Refer to in-game instructions for missile targeting and pause controls.

## Code Structure

The project uses efficient **pool-based allocation** for all game entities:

- Fixed-size arrays for predictable memory usage
- Boolean `active` flags for entity lifecycle management
- Direct indexing instead of dynamic allocations for performance

## Gameplay Parameters

| Parameter          | Value      |
| ------------------ | ---------- |
| Window Width       | 1200 px    |
| Window Height      | 700 px     |
| Max Drones         | 6          |
| Max Missiles       | 10         |
| Radar Detect Range | 420 units  |
| Spawn Interval     | 200 frames |
| Max Particles      | 80         |

## Future Enhancements

- [ ] Different difficulty levels
- [ ] Power-up systems
- [ ] Boss drones
- [ ] Multi-wave missions
- [ ] Sound effects and background music
- [ ] High score persistence
- [ ] Gameplay tutorials

## License

This project is provided as-is for educational and entertainment purposes.

## Author Notes

The Air Defence System demonstrates real-time graphics programming with efficient entity management, physics simulation, and particle effects. The code prioritizes performance through pool allocation and spatial awareness using the radar system.
