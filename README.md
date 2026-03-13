# Flappy Chick

A console-based Flappy Bird clone built in C# for the Windows terminal, featuring ASCII art, progressive difficulty, a coin system, and full sound support.

---

## Project Info

| Detail        | Value              |
| ------------- | ------------------ |
| IDE           | Visual Studio 2022 |
| Language      | C#                 |
| Framework     | .NET 8.0           |
| Audio Library | NAudio 2.2.1       |
| Platform      | Windows (Console)  |

---

## Team

Developed by students from **Laguna State Polytechnic University (LSPU)** as a Final Project requirement.

| Name                     | Role                                                        |
| ------------------------ | ----------------------------------------------------------- |
| Joshua Bartolome         | Team Leader — workflow coordination, code & design          |
| John Christopher Pascual | Core Developer — initial concept & base game implementation |
| Cholo Duran              | Documentation & design suggestions                          |

---

## Features

- **Main Menu** — ASCII art title screen with animated blinking prompt and keyboard navigation
- **Gameplay** — Flappy Bird-style mechanics with gravity, flap control, and scrolling pipe obstacles
- **Progressive Difficulty** — pipe gap narrows and flap strength weakens as score increases
- **Coin System** — collectible coins spawn between pipes with three tiers:
  - Yellow coin — +2 points
  - Blue coin — +5 points
  - Purple coin — +10 points
- **High Score Tracking** — session-persistent high score displayed during play
- **Pause / Resume** — pause the game at any time mid-run
- **Settings Menu** — toggle background music on/off and adjust volume (0–100%)
- **About Us Screen** — animated team info page
- **Game Over Screen** — displays score, high score, and cause of death
- **Full Sound Design** — background music with looping and 11 distinct sound effects

---

## Controls

### In-Game

| Key     | Action                      |
| ------- | --------------------------- |
| `Space` | Flap (also starts the game) |
| `P`     | Pause / Resume              |

### Menus

| Key       | Action                 |
| --------- | ---------------------- |
| `W` / `↑` | Move selection up      |
| `S` / `↓` | Move selection down    |
| `Enter`   | Confirm selection      |
| `Esc`     | Back / Exit (Settings) |

---

## Sound Files

All audio files must be placed in the `Sounds/` folder inside the project directory. The following files are required:

| File             | Used For                    |
| ---------------- | --------------------------- |
| `Background.mp3` | Looping background music    |
| `Select.mp3`     | Menu navigation hover       |
| `Push.mp3`       | Menu item confirmed         |
| `Start.mp3`      | Game start                  |
| `Flap.mp3`       | Bird flap                   |
| `Pause.mp3`      | Game paused                 |
| `Point.mp3`      | Pipe cleared (+1 score)     |
| `Coin.mp3`       | Coin collected              |
| `Danger.mp3`     | Difficulty increase warning |
| `Death.mp3`      | Player death                |
| `GameOver.mp3`   | Game over screen music      |

---

## Project Structure

```
Flappy_Chick/
├── Program.cs          # Entry point, game loop, all screens and rendering logic
├── SoundManager.cs     # Static audio manager using NAudio (BGM + SFX)
├── Sounds/             # MP3 audio assets (copied to output on build)
└── Flappy_Chick.csproj # Project file (.NET 8.0, NAudio 2.2.1)
```

---

## Getting Started

### Prerequisites

- [.NET 8.0 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)
- Visual Studio 2022 (or `dotnet` CLI)

### Build & Run

**Visual Studio 2022:**

1. Open `Flappy_Chick.sln`
2. Set `Flappy_Chick` as the startup project
3. Press `F5` to build and run

**CLI:**

```bash
cd Flappy_Chick
dotnet run
```

> **Note:** Run in a maximized Windows terminal for the best experience. The game renders using `Console` positioning and relies on sufficient window width and height.

---

## How to Play

1. Launch the application — the main menu appears with the **Flappy Chick** ASCII title.
2. Select **Start** and press `Enter`.
3. Press `Space` to begin — your chick will flap upward.
4. Navigate through the gaps in the green pipe obstacles.
5. Collect coins between pipes for bonus points.
6. Watch out — pipes get closer and flap strength decreases as your score climbs.
7. The game ends if the chick hits a pipe or falls to the ground.
8. Press `Enter` on the Game Over screen to return to the main menu.

---

## Difficulty Scaling

| Score Milestone  | Event                                           |
| ---------------- | ----------------------------------------------- |
| Every 10 points  | Pipe horizontal gap decreases (min: 25 columns) |
| Every 100 points | Flap strength decreases (min: -1)               |

Both changes are announced on screen with a red warning and a danger sound effect.

---

## License

This project was created for academic purposes at LSPU. All rights reserved by the authors.
