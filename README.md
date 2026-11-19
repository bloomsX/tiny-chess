# tiny-chess

[![make.fun](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/bloomsX/tiny-chess/rank.svg)](https://make.fun/bounty/tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/bloomsX/tiny-chess/reward.svg)](https://make.fun/bounty/tiny-chess-01)

A chess engine in 4,077 bytes of Python (stdlib only): alpha-beta search with a 0x88 board, Zobrist hashing, transposition table, killer + history heuristics, null-move pruning, LMR, quiescence search, MVV-LVA move ordering, piece-square tables, bishop-pair and king-phase interpolation. Iterative deepening on a cumulative node budget — deterministic, no clock, no model calls, no network. Built for the [make.fun bounty](https://make.fun/bounty/tiny-chess-01) (referral code `r4pcp2sw`).

Practice Elo ~1,433 (3 trials, 18 games: 10W/3D/5L) against the house gauntlet — above the 1,154 floor and the ~1,365 sunfish baseline.

## The size rule

- `main.py` is the whole engine: 4,077 bytes as committed, Python 3.13, standard library only. It is an lzma+base85 loader that decompresses and execs the real engine — compression is allowed and counted.
- It reads, imports or execs no other file in the repository.
- Search uses a fixed node budget, never a clock, so replays play the same moves.
