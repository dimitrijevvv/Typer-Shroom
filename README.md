# Typer Shroom

A C# and MonoGame typing game where you defend a mushroom from waves of bugs by typing the words they carry.

> Team project for the **Programming Paradigms** course at the Faculty of Mathematics, University of Belgrade.
> Originally developed at [matf-pp/2026_Typer-Shroom](https://github.com/matf-pp/2026_Typer-Shroom). Full development history, including [pull requests and code reviews](https://github.com/matf-pp/2026_Typer-Shroom/pulls), is available there.

## Gameplay

Waves of bugs march across the screen toward a mushroom on the right, each carrying a word above it. Start typing a word to lock onto that bug, and finish it to squash the bug before it reaches the mushroom. Every bug that gets through damages the mushroom, and you have **3 lives**.

Each wave brings more bugs that spawn and move faster, so later waves demand both speed and accuracy.

## Screenshots

![Main Menu](screenshots/01_main_menu.png)
![Gameplay 1](screenshots/02_wave1_letters.png)
![Gameplay 2](screenshots/03_1_heart_left.png)
![Game Over and High Scores](screenshots/04_game_over_results.png)

## Controls

| Key | Action |
|-----|--------|
| Letters | Type to target and kill bugs |
| `ESC` | Quit from main menu or mid-game |
| `SPACE` | View high scores (from main menu) |
| `Enter` | Confirm name entry |

## Features

- 6 animated bug types: spider, ant, fly, mosquito, worm and butterfly
- Mushroom with 4 progressive damage states and a hit flash
- Splash death animation when a bug is squashed
- Background music plus mistype, squash and eat sound effects
- Wave-cleared notification between waves
- Lives shown as hearts in the HUD
- Game over → name entry → results screen (top 5) → main menu
- Local high scores (top 10) saved to `scores.json`

## Project Structure

```
TyperShroom.Core/    — Game logic (GameEngine, Bug, GameState, WordManager)
TyperShroom.UI/      — MonoGame frontend, screens and rendering
TyperShroom.Data/    — Score persistence (ScoreRepository → scores.json)
TyperShroom.Tests/   — Console test runner
```

The game logic in `Core` is kept separate from the MonoGame frontend in `UI`, so it can be tested on its own.

## Running the Game

### From source

Requires the [.NET SDK](https://dotnet.microsoft.com/download).

```bash
git clone https://github.com/dimitrijevvv/Typer-Shroom.git
cd Typer-Shroom
dotnet run --project TyperShroom.UI
```

### From a published build

**Linux**
```bash
chmod +x TyperShroom.UI
./TyperShroom.UI
```

**Windows**

Run `TyperShroom.UI.exe` from the publish folder.

## Authors

- Dimitrije Vujko
- Mihajlo Tasić
- Sreten Milekić
