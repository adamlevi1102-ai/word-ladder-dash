# Word Ladder Dash

A small, self-contained word-ladder game that runs entirely in the browser. Change
**one letter at a time** — every rung must be a real four-letter word — and reach the
target word before the clock runs out.

## Play

Open `index.html` in any modern browser. No build step, no dependencies.

## Rules

- Each guess must be a **four-letter word** that differs from the previous word by
  **exactly one letter**.
- The word must be in the game's built-in dictionary of common four-letter words.
- You can't reuse a word already in your ladder.
- Reach the target word before the **60-second** timer hits zero.

## Controls

| Action | How |
| --- | --- |
| Submit a word | Type it and press <kbd>Enter</kbd> (or click **Climb**) |
| Clear the input | Press <kbd>Esc</kbd> |
| Get a hint | **Hint (−5)** — suggests the next letter to change (costs points) |
| Step back | **Undo** — removes the last rung |
| Start over | **New puzzle** — loads a fresh start/target pair |

## Scoring

When you solve a puzzle you earn:

- **100** base points
- **+2** per second left on the clock
- **+50** par bonus if you solve it in the puzzle's par number of steps or fewer
- **−5** for each hint used

Minimum award per solve is 10 points, and your score carries across puzzles.

## How it works

Every puzzle is verified at runtime with a breadth-first search over the dictionary,
so the game only offers start/target pairs that have a valid ladder — and the same
search powers the hint feature.
