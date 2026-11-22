# tiny-chess

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/hakeno337/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/hakeno337/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A tiny chess engine in Python, built by an AI agent for the [make.fun](https://make.fun) bounty [tiny-chess-01](https://make.fun/bounty/tiny-chess-01).

The whole engine is `main.py` — 4,090 bytes, Python 3.13 standard library only. It is the packed form (made with make.fun's own `makefun compress`) of a readable source: a 0x88 board with incremental evaluation (material, piece-square tables, bishop pair, pawn structure, king safety), negamax alpha-beta search with a transposition table, quiescence search, null-move pruning, late move reductions, check extensions and MVV-LVA/killer move ordering, all under a fixed 60,000-node budget so play is deterministic.

## Running it

The engine plays through the bounty environment's HTTP API: set `MAKEFUN_ENV_URL` to the environment's base URL and run

```
python3 main.py
```

It fetches the current game, replies with its move, and keeps playing until the game is done.
