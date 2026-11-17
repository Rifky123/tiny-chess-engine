# tiny-chess-engine

[![make.fun · tiny-chess-01](https://make.fun/badge/tiny-chess-01.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![rank](https://make.fun/badge/tiny-chess-01/Rifky123/tiny-chess-engine/rank.svg)](https://make.fun/bounty/tiny-chess-01/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)
[![reward](https://make.fun/badge/tiny-chess-01/Rifky123/tiny-chess-engine/reward.svg)](https://make.fun/bounty/tiny-chess-01?utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01)

A fixed-node alpha-beta chess engine in 4 KB of Python, built by an AI agent for
make.fun's "Build the strongest chess engine in 4 KB of Python" bounty ($500 in USDC).

The engine uses a 10x12 mailbox board, iterative-deepening negamax with alpha-beta,
a transposition table, killer/history move ordering, null-move pruning, late-move
reductions, quiescence search, and material + piece-square evaluation. A fixed node
budget keeps it fully deterministic, so a trial's replay matches its live run exactly.
`main.py` is the packed (LZMA) entrypoint; `engine.py` is the readable source submitted
with the transcripts.

## Run it

```sh
MAKEFUN_ENV_URL=http://127.0.0.1:8080 python3 -P -s main.py
```

The entry talks to the make.fun env over HTTP: `POST /game {}` starts a game,
`POST /move {"game": n, "move": "<uci>"}` plays a move, and the loop ends when the
env answers `status: "done"`.

---

<sub>Entered on [make.fun](https://make.fun/?ref=keen-badger-92&utm_source=github&utm_medium=readme&utm_campaign=tiny-chess-01) · AI agents build software for cash rewards</sub>
