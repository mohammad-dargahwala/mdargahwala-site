# Connect 4 Solver

A Connect 4 board with move scores and a suggested move for the player you choose. The board and controls are written in one HTML file.

[Play online](https://mdargahwala.tech/cfour_solver.html)

## Playing

Click a column to drop a piece. Choose Player 1 (red) or Player 2 (yellow) to control whose turns get a move recommendation. Both players' moves are entered manually; the app does not play an opponent's moves for you.

You can undo and redo moves, review the move list, jump back to an earlier position, and restart the game. The interface also includes score and recommendation toggles, an optional reset confirmation, and six themes: Dark, Light, Ocean, Synthwave, Forest, and Cyberpunk.

Game progress and theme choices are held in page memory and reset on reload.

## Where the scores come from

The solver runs at [connect4.gamesolver.org](https://connect4.gamesolver.org/), outside this repository. After a move, the browser sends the move sequence to:

```text
https://connect4.gamesolver.org/solve?pos=<move-sequence>
```

The page displays the returned scores for the player whose turn it is:

| Display | Meaning |
| --- | --- |
| Positive score | Winning move with perfect play |
| Negative score | Losing move with perfect play |
| `=` | Draw with perfect play |
| `✕` | Full column or a move marked unavailable by the solver |
| `?` | The solver request failed |

The recommendation picks the highest-scoring legal column on your selected player's turn. Ties prefer columns closest to the center.

The score is a solver evaluation, not a direct count of moves until the game ends. On an empty board, the page shows placeholder draw scores without contacting the solver; those opening scores are not a computed evaluation.

The board's rules and win detection run in the browser. Evaluations need internet access and depend on the external service being available and allowing the browser request.

## Run locally

Open [`cfour_solver.html`](cfour_solver.html) in a browser. There is no package installation or build step.

The CSS and JavaScript are included in the HTML. The font loads from Google Fonts, and evaluations come from the solver service.

## Hosting

The included `wrangler.toml` names a Cloudflare Worker, `cfour-solver`, and serves the repository directory as static assets. There is no backend solver or database in this project. The playable page is `cfour_solver.html`; the repository does not include an `index.html`.

