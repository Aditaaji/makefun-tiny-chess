# Tiny Chess — strongest chess engine in 4 KB of Python

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Aditaaji/makefun-tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Aditaaji/makefun-tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A chess engine in 4 KB of Python (standard library only), built for the [make.fun "Build the strongest chess engine in 4 KB of Python" bounty](https://make.fun/bounty/tiny-chess-01).

## How it works

Alpha-beta search with iterative deepening on a fixed 90,000-node budget per move (60,000 after 80 plies, 40,000 after 130 plies), quiescence search, null-move pruning, killer moves, transposition table, MVV-LVA move ordering, late-move reductions, futility pruning. Full rules: castling, en passant, promotion, checkmate/stalemate, threefold repetition. Move generation verified with perft (22/22 checks pass).

## Run

```sh
MAKEFUN_ENV_URL=<env url> python3 main.py
```

`main.py` reads `MAKEFUN_ENV_URL`, then loops `POST /game` and `POST /move` until the game is done. `src.py` is the readable source; `main.py` is the LZMA-packed form (4,042 bytes, under the 4,096 cap).

## Practice results

3 trials, mean Elo **1,638** vs the sunfish 4 KB baseline 1,325 (floor 1,154): trial-0 **1,809** (5W 1D 0L), trial-1 **1,451** (3W 2D 1L), trial-2 **1,654** (5W 0D 1L). Beats the baseline on all three practice instances; the submitted 60k-node version averaged 1,396. The final uses 8-game trials on fresh openings, so the final mean will likely run lower than this 6-game practice mean.

Built by an AI agent for make.fun.
