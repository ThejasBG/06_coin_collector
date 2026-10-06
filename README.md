# Coin Collector

A simple top-down Coin Collector game built with **Python and Pygame**. The player moves around the play area, collects different types of coins, avoids obstacles, and tries to achieve the highest possible score before the round ends.

## Features

### 🪙 Coin Collection

- Coins are collected when the player touches them.
- Each coin can only be collected **once**.
- Collected coins are removed from the play area immediately.
- The game contains three different coin types:

| Coin Type | Value |
|---|---:|
| Bronze | 1 point |
| Silver | 3 points |
| Gold | 5 points |

Each coin type has a different color so that they can be distinguished visually.

### 🚧 Obstacles

- Obstacles are randomly placed within the play area.
- The player must avoid obstacles while collecting coins.
- Colliding with an obstacle costs **one life**.
- The player starts with **3 lives**.
- A short collision cooldown prevents a single collision from immediately removing multiple lives.
- Obstacles do not spawn directly on top of the player's starting position.

### ⏱️ Timed Round

- Each round has a **30-second time limit**.
- The remaining time is displayed during gameplay.
- The round ends when:
  - All coins have been collected.
  - The 30-second timer reaches zero.
  - The player loses all lives.

### 🏆 Final Score

When all coins are collected, the final score is calculated using:

```text
Final Score = (Score / Time Taken) × 100
```

For example:

```text
Score = 24
Time Taken = 12 seconds

Final Score = (24 / 12) × 100
            = 200
```

A faster completion time therefore results in a higher final score.

If the round ends because of the timer or because the player loses all lives, the game also displays the final score.

### 🔄 Restart

After a round ends:

```text
Press R to start a new round
```

Starting a new round resets:

- Score
- Lives
- Timer
- Coins
- Obstacles
- Player position
- Final score

## Controls

| Key | Action |
|---|---|
| ↑ | Move up |
| ↓ | Move down |
| ← | Move left |
| → | Move right |
| R | Restart after game over |

## Project Structure

```text
06_coin_collector/
│
├── coin-collector/
│   ├── game/
│   │   ├── coin.py
│   │   ├── collection.py
│   │   ├── game_engine.py
│   │   ├── player.py
│   │   └── renderer.py
│   │
│   ├── main.py
│   └── requirements.txt
│
└── README.md
```

### Main Components

**`game/coin.py`**

Defines the different coin types, their values, colors, and collision rectangles.

**`game/collection.py`**

Handles collision detection between the player and coins.

**`game/game_engine.py`**

Controls the main game logic, including:

- Player movement
- Coin spawning
- Coin collection
- Score
- Obstacles
- Lives
- Timer
- Round state
- Final score
- Restarting rounds

**`game/player.py`**

Defines the player and handles player movement and boundaries.

**`game/renderer.py`**

Handles drawing:

- Player
- Coins
- Obstacles
- Score
- Lives
- Timer
- Game-over screen

**`main.py`**

Runs the Pygame application and game loop.

## Installation

Clone the repository:

```bash
git clone https://github.com/ThejasBG/06_coin_collector.git
```

Enter the project directory:

```bash
cd 06_coin_collector/coin-collector
```

Install the dependencies:

```bash
pip install -r requirements.txt
```

Run the game:

```bash
python main.py
```

## Implementation Checklist

### Task 1 — Fix Coin Collection

- [x] Detect when the player touches a coin
- [x] Award the coin's value
- [x] Remove the collected coin
- [x] Prevent the same coin from being scored repeatedly
- [x] Verify that standing on a coin does not continuously increase the score

### Task 2 — Multiple Coin Types

- [x] Implement bronze coins
- [x] Implement silver coins
- [x] Implement gold coins
- [x] Bronze = 1 point
- [x] Silver = 3 points
- [x] Gold = 5 points
- [x] Give each type a distinct color
- [x] Award the correct value for each coin

### Task 3 — Obstacles

- [x] Add obstacles to the play area
- [x] Keep obstacles within the play area
- [x] Prevent obstacles from spawning directly on the player
- [x] Detect player-obstacle collisions
- [x] Remove one life when an obstacle is hit
- [x] Add collision cooldown
- [x] End the round when all lives are lost

### Task 4 — Timed Round

- [x] Add a 30-second countdown
- [x] Display remaining time
- [x] End the round when the timer reaches zero
- [x] End the round when all coins are collected
- [x] End the round when all lives are lost
- [x] Calculate the final score
- [x] Display the final score
- [x] Allow the player to restart with `R`
- [x] Reset score, lives, timer, coins, obstacles, and player position

## Completion Status

| Task | Status |
|---|---|
| Coin collection bug | ✅ Complete |
| Multiple coin types | ✅ Complete |
| Obstacles and lives | ✅ Complete |
| 30-second timer | ✅ Complete |
| Final score calculation | ✅ Complete |
| Restart system | ✅ Complete |

**Project status: Complete ✅**
