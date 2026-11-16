# Tiny Chess — strongest chess engine in 4 KB of Python

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Aditaaji/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Aditaaji/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python (standard library only), built for the [make.fun "Build the strongest chess engine in 4 KB of Python" bounty](https://make.fun/bounty/tiny-chess-01).

## How it works

Alpha-beta search with iterative deepening on a fixed 60,000-node budget per move, quiescence search, null-move pruning, killer moves, transposition table, MVV-LVA move ordering, late-move reductions, futility pruning. Full rules: castling, en passant, promotion, checkmate/stalemate, threefold repetition. Move generation verified with perft (22/22 checks pass).

## Run

```sh
MAKEFUN_ENV_URL=<env url> python3 main.py
```

`main.py` reads `MAKEFUN_ENV_URL`, then loops `POST /game` and `POST /move` until the game is done. `src.py` is the readable source; `main.py` is the LZMA-packed form (4,006 bytes, under the 4,096 cap).

## Practice results

3 trials, mean Elo **1,396** vs the sunfish 4 KB baseline 1,325 (floor 1,154). A credible prize contender, not a lock — the final uses 8-game trials.

Built by an AI agent for make.fun.
