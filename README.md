# Connect4

Connect4 is a classic, web-based two-player strategy game. Players take turns dropping colored discs from the top into a seven-column, six-row vertically suspended grid. The objective of the game is to be the first to form a horizontal, vertical, or diagonal line of four of one's own discs.

---

## Project Category
**Category:** Web Application / Game Development / Front-End

---

## Key Features

*   **Interactive Two-Player Gameplay:** Seamless local multiplayer experience where Player 1 (Red) and Player 2 (Yellow) take turns dropping discs.
*   **Dynamic Gravity System:** Clicking any tile in a column automatically places the disc at the lowest available row in that column.
*   **Win Detection & Score Tracking:** Real-time win evaluation checks horizontally, vertically, and diagonally after every move, automatically updating the persistent session scoreboard.
*   **Immersive Audio Effects:** High-quality audio feedback including discrete pop sounds upon disc insertion and a victory tune upon winning.
*   **Celebration Effects:** Employs a browser-based particle confetti system to celebrate the winning player.
*   **Responsive Space-Themed UI:** Sleek cosmic styling with responsive layouts, an instructions modal, and button controls.

---

## Tech Stack & Hardware Components

### Software & Technologies
*   **Frontend UI:** HTML5
*   **Styling & Themes:** CSS3 (featuring custom animations, glassmorphism-like borders, flexbox/grid layouts, and media queries for mobile responsiveness)
*   **Logic Engine:** Vanilla JavaScript (ES6) for DOM rendering, event registration, grid matrix calculations, and audio integration
*   **Particle Library:** Canvas Confetti (loaded via CDN)

---

## Directory Structure

```text
connect4.gg/
├── index.html        # Main markup file containing game containers, scoreboard, and modals
├── style.css         # Primary stylesheet defining layout and theme configurations
├── media.css         # Stylesheet handling media queries and responsiveness for smaller viewports
├── script.js         # Core game logic, matrix search, score display, and sound trigger control
├── space3.jpg        # Background graphic asset used across the game board and UI elements
├── popsound.mp3      # Sound effect file triggered upon coin drop
└── win-sound.mp3     # Audio file played when a player wins a match
```

---

## How It Works (High-Level Workflow)

### 1. Board Setup and Game Loop
1. The game loads, displaying a pop-up window detailing the rules of Connect4.
2. Clicking "Play !!" hides the modal and triggers the game initialization sequence.
3. The board generator dynamically creates a 6x7 grid of tiles in the DOM, allocating coordinates to each cell and binding click listeners.
4. Player Red starts the round.

### 2. Piece Placement and Win Validation
1. A player clicks a tile within a target column.
2. The game logic checks the lowest empty row index in that column.
3. The server/browser updates the internal grid matrix state and updates the tile class to render either a red or yellow disc.
4. A disc drop sound effect plays, and the column's next available height coordinate is decremented.
5. The win logic scans the matrix horizontally, vertically, and diagonally to find a consecutive line of 4 identical tokens.
6. If a win is detected, the scoreboard increments, a victory tune plays, and confetti particles are launched across the screen.

---

## Getting Started

### Prerequisites
*   A modern web browser (Google Chrome, Mozilla Firefox, Safari, Microsoft Edge, etc.)
*   A local web server (optional, but recommended for playing media files smoothly)

### Installation & Local Setup

1.  **Clone the repository:**
    ```bash
    git clone https://github.com/AjitM07/connect4.gg.git
    cd connect4.gg
    ```

2.  **Open the application:**
    *   Simply double-click `index.html` to run the game directly in any browser.
    *   Alternatively, serve it locally using a simple Python server:
        ```bash
        python -m http.server 8000
        ```
        Then, navigate to `http://localhost:8000` in your web browser.
