# Connect 4 Solver

An interactive Connect 4 game with a built-in perfect solver, built in a single HTML file using HTML, CSS, and JavaScript.

## Features

- **Working Website**: [Working Website](https://mdargahwala.tech/cfour_solver.html)
- **Perfect Solver Integration**: Connects to the [Connect 4 Solver API](https://connect4.gamesolver.org/) to evaluate the board state.
- **Move Recommendations**: Highlights the best column to drop your piece on your turn.
- **Score Evaluation**: Displays the evaluation score for each column (`+` for winning moves, `-` for losing moves, `=` for drawing moves, and `✕` for full columns).
- **Multiple Themes**: Play in Dark, Light, Ocean, Synthwave, Forest, or Cyberpunk themes.
- **Player Selection**: Choose to play as Player 1 (Red) or Player 2 (Yellow).
- **Desktop Cursor Effects**: Includes a custom cursor and hover interactions for pointer/fine-cursor devices.
- **Touch-Friendly Input**: On mobile and touch surfaces, cursor effects and hover ghost indicators are disabled for cleaner gameplay.
- **Mobile Options Menu**: Settings collapse into an Options menu on smaller screens to avoid overflow.
- **Safe Reset Mode**: Optional reset confirmation timer applies during active play and is skipped once a game has ended.
- **Beautiful Animations**: Dropping pieces, winning highlights, and button interactions are accompanied by smooth CSS animations.
- **Game History & Controls**: Keep track of the move sequence, and easily Undo or Reset the game.
- **Responsive Design**: Optimized for desktop, tablet, and small phones.

## Usage

Simply open the `cfour_solver.html` file in any modern web browser to start playing! No build step or installation required.

## How the Solver Works

The UI queries the solver API with the current sequence of moves (e.g., `123123`) and receives back an array of scores corresponding to each column. The UI then translates this into actionable advice:

- **Positive numbers** indicate a forced win in that many moves.
- **Negative numbers** indicate a forced loss if that column is played.
- **Zero** indicates a draw with perfect play.
- The highest score determines the recommended move.

## Tech Stack

- **HTML5**: For the layout and semantic structure.
- **CSS3**: For styling, responsive layouts (CSS Grid/Flexbox), and animations.
- **JavaScript (ES6+)**: For game logic, DOM manipulation, and asynchronous API calls.
