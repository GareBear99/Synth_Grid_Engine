Synth Grid Engine

A blueprint-driven simulation shell where geometry becomes computation.

This project is an experimental system that treats space like a
filesystem and entities like autonomous executors. The world itself
becomes a programmable environment.

Inspired by: - TRON Grid Worlds - Geometry Wars style spatial
computation - Modular OS-like simulation environments

------------------------------------------------------------------------

Core Idea

Instead of building a fixed application, the engine loads blueprints
that define how the world behaves.

The system consists of three blueprint layers:

1.  Shell Blueprint Defines the world geometry.

2.  Module Blueprints Attach systems into the world.

3.  Execution Layer Runs the deterministic simulation loop.

Core metaphor:

Geometry = storage Movement = computation Entities = executors Paths =
allocated space

------------------------------------------------------------------------

Math-First Simulation

The engine is math-first, not graphics-first.

The simulation runs entirely in deterministic 2D vector space, while the
rendering layer projects the world to appear visually 3D.

Advantages: - extremely low CPU usage - deterministic reproducible
worlds - simple debugging and validation - portable execution on almost
any hardware

Even older machines (2010–2012 era laptops) can run the simulation
smoothly.

------------------------------------------------------------------------

2D Core → Visually 3D

All world logic runs in 2D simulation space.

Rendering then projects that simulation into a visually 3D environment
using techniques such as: - perspective scaling - layered sprites - cube
grid projection - depth shading

This creates a 3D-like environment without the cost of a full 3D engine.

------------------------------------------------------------------------

Architecture

Engine Core - deterministic simulation loop - fixed timestep updates -
fail-closed execution model

Blueprint System Blueprints describe how the world is built.

Examples include: - Shell blueprints (world structure) - Ship modules -
Scanner modules - HUD modules

Example included blueprint: blueprint_octagon.json

This builds an octagon shell structure where modules can attach.

------------------------------------------------------------------------

Controls

WASD - Move master control Mouse - Aim vector C - Toggle reticle ` -
Toggle debug overlay R - Reset

------------------------------------------------------------------------

Running the Engine

1.  Download the repository
2.  Open index.html in a browser

No server required.

------------------------------------------------------------------------

Loading Blueprints

Upload blueprints into the runtime UI.

Recommended order:

1.  Shell blueprint
2.  Ship module
3.  Scanner module
4.  HUD module (optional)

------------------------------------------------------------------------

Blueprint Format

Example module blueprint:

{ “moduleType”: “scanner”, “id”: “SCAN_01”, “style”: “default”,
“config”: {}, “script”: “” }

------------------------------------------------------------------------

What People Will Understand It As

A modular simulation engine where you build worlds by attaching
blueprints instead of writing code.

The system treats space itself as a programmable structure where modules
define behavior and entities act as executors inside the environment.
