# 👑 Jump King — Web Edition

> A browser-based precision platformer built from scratch with vanilla JavaScript and the HTML5 Canvas API.  
> **No frameworks. No game engine. Just code.**

<br>

[![Live Demo](https://img.shields.io/badge/▶%20Play%20Now-Live%20Demo-blue?style=for-the-badge)](https://tanmoy34.github.io/WebGames/)
[![HTML5](https://img.shields.io/badge/HTML5-Canvas%20API-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Live Demo](#-live-demo)
- [Gameplay](#-gameplay)
- [Controls](#-controls)
- [Features](#-features)
- [Technical Implementation](#-technical-implementation)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Author](#-author)

---

## 🎮 About the Project

**Jump King Web Edition** is a faithful web reimagining of the beloved precision platformer genre, built entirely from scratch using **vanilla JavaScript** and the **HTML5 Canvas API** — with zero external dependencies.

The game challenges players to climb an increasingly difficult series of platforms using a charge-based jump mechanic. Every jump requires careful timing: hold too short and you fall short, hold too long and you overshoot. One wrong move can send you tumbling back to the bottom.

This project was built as a personal challenge to deeply understand browser-based game development — from physics simulation and collision detection to responsive UI and mobile input systems — without relying on any game engine or framework.

---

## 🌐 Live Demo

**👉 [Play it here: tanmoy34.github.io/WebGames](https://tanmoy34.github.io/WebGames/)**

Fully playable in any modern browser. No installation required. Mobile-friendly.

---

## 🕹️ Gameplay

The objective is simple: **reach the top**.

- The player character climbs a vertical world filled with platforms
- Each jump must be carefully **charged** — hold the jump key to build power, release to launch
- **HEIGHT** (how high you've climbed) and **FALLS** (how many times you've fallen) are tracked live in the HUD
- Reach the summit to trigger the **Victory screen**

The longer you play, the more you appreciate just how punishing — and rewarding — precision platforming can be.

---

## 🎯 Controls

### Desktop

| Key | Action |
|-----|--------|
| `←` `→` | Move Left / Right |
| `SPACE` (hold) | Charge jump power |
| `SPACE` (release) | Launch the jump |

> **Tip:** The longer you hold, the higher you jump. Mastering charge timing is everything.

### Mobile

| Input | Action |
|-------|--------|
| `←` `→` buttons | Move Left / Right |
| `JUMP` (hold) | Charge jump power |
| `JUMP` (release) | Launch the jump |

Full on-screen touch controls are available for mobile and tablet players.

---

## ✨ Features

- **⚡ Charge-Based Jump System** — Variable jump height controlled by how long you hold the jump key
- **📊 Live HUD** — Real-time HEIGHT and FALLS counter displayed throughout the game
- **📱 Mobile Support** — On-screen virtual buttons with full touch input handling
- **🏆 Victory Screen** — Triggered when the player reaches the top of the level
- **📋 In-Game Modals** — Controls reference and Credits screen accessible during gameplay
- **🔄 Instant Restart** — Jump back in immediately after a game over
- **🚫 Zero Dependencies** — No libraries, no frameworks, no build tools required

---

## 🔧 Technical Implementation

### Physics Engine

A custom physics system handles all movement and collision:

- **Gravity** — Constant downward acceleration applied every frame
- **Charge accumulation** — Jump force builds linearly while the key is held
- **Trajectory calculation** — Horizontal and vertical velocity resolved on release
- **Collision detection** — AABB (Axis-Aligned Bounding Box) against all platform rectangles
- **Landing / wall response** — Velocity reset and position correction on collision

### Rendering

- All visuals drawn each frame via the **Canvas 2D Context**
- Layered draw calls: background → platforms → player → HUD → UI modals
- Smooth 60fps game loop using `requestAnimationFrame`

### Game State Machine

The game runs through distinct states, each with its own update and render logic:

```
MENU  ──►  PLAYING  ──►  VICTORY
                │
                ▼
             (fall — resume from last safe height)
```

### Input System

- **Keyboard:** `keydown` / `keyup` event listeners mapped to game actions
- **Touch:** `touchstart` / `touchend` listeners on virtual button elements, mirroring keyboard behaviour

### Mobile Layout

- Viewport meta tag ensures correct scaling on all screen sizes
- On-screen `←`, `→`, and `JUMP` buttons rendered below the canvas
- Touch events independently tracked so multi-touch (move + jump) works correctly

---

## 📁 Project Structure

```
WebGames/
│
├── index.html          # Entry point — game canvas + UI markup
├── style.css           # Layout, HUD styling, modal styling, mobile buttons
├── game.js             # Core game loop, physics, collision, state machine
│
└── assets/
    ├── player.png      # Player sprite
    └── platform.png    # Platform tile (if used)
```

---

## 🚀 Getting Started

No build step needed. Just clone and open.

```bash
# Clone the repository
git clone https://github.com/tanmoy34/WebGames.git

# Open in your browser
cd WebGames
open index.html
```

Or simply visit the **[live demo](https://tanmoy34.github.io/WebGames/)** — no setup required.

---

## 👤 Author

**Tanmoy Ghatak**  
Senior Game Developer — Unity, Unreal Engine, HTML5

- 🌐 Portfolio: [tanmoy34.github.io](https://tanmoy34.github.io/)
- 💼 LinkedIn: [linkedin.com/in/tanmoy-ghatak-b8707a14b](https://www.linkedin.com/in/tanmoy-ghatak-b8707a14b/)
- 📧 Email: tanmoyghatak1199@gmail.com

---

> *Built with patience, ruined by falls, perfected by persistence.*  
> — The Jump King experience
