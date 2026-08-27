# BYRSA — read-only fork provenance

This fork is **read-only** for the BYRSA workspace. No code in this repository
is modified; this file is the entire diff.

The BYRSA workspace forks five repositories on the instruction to *"pin the
version, mine one idea each"*. This records the pin and the idea, so a later
session can tell what was borrowed and check it against the source.

| | |
|---|---|
| **Pinned commit** | `1b7af2005bcd1a53e9698435618776b0f3443200` (`1b7af20`, 2026-06-18) |
| **Idea mined** | **PUCT over heterogeneous decision points.** MageZero searches a game whose decision points are not all the same shape. BYRSA has four concurrency shapes in a single round — simultaneous Pledge, sequential Rescue, simultaneous Ballot, sequential flip-buy — so an agent interface that assumes one actor per state cannot express it. |
| **Where it landed** | The seven-method agent contract in `byrsa-sim/byrsa_sim/agents/base.py`, one method per decision point, and the phase split in the OpenSpiel harness where `current_player()` returns SIMULTANEOUS for the Pledge and a real seat for the Rescue |
| **Cited in** | `01` §3 |

## Why pinning matters

A borrowed idea that drifts with upstream is an unrecorded dependency. The BYRSA
corpus requires every finding to carry a git SHA and seed range; a technique
borrowed from a moving target would break that chain. This fork is not tracked
for updates — if the idea needs revisiting, it is revisited against **this**
commit.

## What was NOT taken

No rule from any bundled game, ever. BYRSA's rules live in exactly one place:
A2 of the corpus, implemented by `byrsa-sim/byrsa_sim/rules.py`. What is
borrowed here is *methodology* — how to structure a bot roster, how to shape a
report, how to parameterise a strategy — never a mechanic.
