
# Synth Grid Engine

A blueprint-driven simulation shell where geometry becomes computation.

This project is an experimental system that treats space like a filesystem and entities like autonomous executors. The world itself becomes a programmable environment.

Inspired by:
- TRON Grid Worlds
- Geometry Wars style spatial computation
- Modular OS-like simulation environments

---

# Core Idea

Instead of building a fixed application, the engine loads **blueprints** that define how the world behaves.

The system consists of three blueprint layers:

1. **Shell Blueprint**
   Defines the world geometry.

2. **Module Blueprints**
   Attach systems into the world.

3. **Execution Layer**
   Deterministic simulation loop.

Geometry = storage  
Movement = computation  
Entities = executors  

---

# Math-First Simulation

The engine is math-first, not graphics-first.

The simulation runs entirely in deterministic 2D vector space, while the rendering layer projects the world to appear visually 3D.

This approach provides several advantages:

• extremely low CPU usage

• deterministic reproducible worlds

• simple debugging and validation

• portable execution on almost any hardware


Even older machines (2010–2012 era laptops) can run the simulation smoothly.

# 2D Core → Visually 3D

All world logic runs in 2D simulation space.

Rendering then projects that simulation into a visually 3D environment using techniques such as:

- perspective scaling

- layered sprites

- cube grid projection

- depth shading

This creates a 3D-like environment without the cost of a full 3D engine.


---

# Example World


![Demo](images/Image1.jpeg)

The included example blueprint: blueprint_octagon.json

Builds an octagon shell structure where modules can attach.

---

# Controls
```
{
| Key | Action |
|----|----|
| WASD | Move master control |
| Mouse | Aim vector |
| C | Toggle reticle |
| ` | Toggle debug overlay |
| R | Reset |
}
```
---

# Running the Engine

1. Download the repository
2. Open index.html


in a browser.

No server required.

---

# Loading Blueprints

Upload blueprints into the runtime UI.

Recommended order:

1️⃣ Shell blueprint  

2️⃣ Ship module  

3️⃣ Scanner module  

4️⃣ HUD module (optional)  

---

# Blueprint Format

Example module blueprint

```json
{
  "moduleType": "scanner",
  "id": "SCAN_01",
  "style": "default",
  "config": {},
  "script": ""
}
```




