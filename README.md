# Fly Paper Plane

> A 3D web-based paper plane flight game with time attack challenges, built with React and Three.js.

## Overview

Fly Paper Plane is a Roblox-style 3D flight game where players control a paper plane to navigate through obstacles and reach the goal in the shortest time possible. Features include real-time physics simulation, a third-person camera system, email-based authentication, and a global leaderboard.

## Features

### Gameplay
- **Intuitive flight controls**: WASD keys for directional movement, Shift for speed boost
- **3D environment**: Immersive graphics powered by Three.js and React Three Fiber
- **Obstacle avoidance**: Navigate past trees, buildings, and various obstacles
- **Time attack mode**: Race to reach the goal in the shortest time
- **Real-time camera**: Third-person perspective that follows the plane

### Social
- **Email authentication**: Simple email-based login system
- **Leaderboard**: Global player ranking system
- **Record management**: Personal best time tracking and storage

### UI/UX
- **Main menu**: Game start, leaderboard, settings
- **Game HUD**: Real-time timer, speedometer
- **Result screen**: Post-game record display and submission
- **Sound system**: Background music and sound effects

## Controls

| Key | Action |
|-----|--------|
| **W** | Ascend |
| **S** | Descend |
| **A** | Move left |
| **D** | Move right |
| **Shift** | Boost (speed increase) |

## Tech Stack

| Category | Technology |
|----------|------------|
| **UI Framework** | React 18, TypeScript |
| **3D Rendering** | Three.js, @react-three/fiber, @react-three/drei |
| **Physics** | cannon-es (flight), @react-three/rapier (collision) |
| **State Management** | Zustand |
| **Styling** | Tailwind CSS |
| **Animation** | Framer Motion |
| **Forms** | React Hook Form + Zod |
| **Build Tool** | Vite |
| **Testing** | Vitest, Testing Library, Playwright, Stryker (mutation) |

## Getting Started

### Prerequisites
- Node.js v18.0 or higher
- npm

### Installation

```bash
git clone https://github.com/AnsibleMage/Web_Fly_paper_plane.git
cd Web_Fly_paper_plane
npm install
```

### Running

```bash
# Development server (http://localhost:5173)
npm run dev

# Production build
npm run build

# Preview production build
npm run preview
```

## Project Structure

The project follows a **4-Layer Fractal Architecture** organized into Blocks, Features, and Tasks:

```
1 Product = 4 Blocks = 14 Features = 70 Tasks
```

```
src/
├── blocks/
│   ├── block1-flight-control/     # Flight physics, input, camera
│   │   └── features/
│   │       ├── f1-input-handler/      # Keyboard & mouse input
│   │       ├── f2-flight-physics/     # Physics engine & dynamics
│   │       └── f3-camera-system/      # Camera follow & constraints
│   ├── block2-game-core/          # Course, timer, collision
│   │   └── features/
│   │       ├── f1-course-manager/     # Course definition & checkpoints
│   │       ├── f2-timer-record/       # Timer & record management
│   │       └── f3-collision-state/    # Collision detection & game state
│   ├── block3-social/             # Auth, leaderboard, records
│   │   └── features/
│   │       ├── f1-email-auth/         # Email validation & auth
│   │       ├── f2-leaderboard-display/ # Ranking table & display
│   │       └── f3-record-manager/     # Record submission & storage
│   └── block4-ui-ux/             # Menu, HUD, sounds (in progress)
│       └── features/
│           ├── f1-main-menu/
│           ├── f2-game-hud/
│           ├── f3-result-screen/
│           ├── f4-3d-environment/
│           └── f5-sound-effects/
├── components/                    # Shared React components
├── hooks/                         # Custom React hooks
└── App.tsx                        # Main application entry
```

## Testing

```bash
# Unit tests (watch mode)
npm test

# Test coverage (target: >90%)
npm run test:coverage

# Mutation testing (target: >80%)
npm run test:mutation

# E2E tests
npm run test:e2e

# E2E tests (headed mode)
npm run test:e2e:headed
```

### Test Status

| Block | Tests | Status |
|-------|-------|--------|
| Block 1 - Flight Control | 454 | Complete |
| Block 2 - Game Core | 204 | Complete |
| Block 3 - Social | 183 | Complete |
| Block 4 - UI/UX | 6 | In Progress |
| **Total** | **847** | **64% Complete** |

## Development Methodology

Built using **4-Layer Fractal TDD + Pyramid Workflow**:

```
Task Unit Test -> Feature Integration Test -> Block Module Test -> Product E2E Test
```

Core principles:
- **TDD**: Red -> Green -> Refactor -> Mutation
- **Pyramid Workflow**: Complete lower layers before integrating upper layers
- **Zero-Guess Protocol**: All code derives from specification documents

## Performance Targets

| Metric | Target |
|--------|--------|
| Initial Load | < 3s |
| FPS | >= 60 |
| Input Response | < 16ms |
| Leaderboard Query | < 1s |

## Documentation

- `doc/Product_PRD_*.md` -- Product requirements specification
- `doc/CJ_AI_*.md` -- Development methodology guide
- `doc/LAUNCH_ROADMAP.md` -- Launch roadmap

## License

MIT

---

*Built with React, Three.js, and Claude Code by AnsibleMage*
