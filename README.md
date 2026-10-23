# Poker Coach

A solo, phone-friendly **live poker coach** — a fork of the OC Poker Table's decision engine.
Enter your hand by tapping cards; it estimates your **equity** (Monte-Carlo, vs. random opponent
hands) and **pot odds**, and recommends a solid baseline play (bet / raise / call / check / fold)
with the reasoning — recomputing live as the hand develops.

Reuses the same `pokersolver` evaluator and the same Monte-Carlo equity approach as the poker
room's bots, repackaged as a client-side tool.

## Run
Fully static — no server, no build, works offline.
- **Locally:** open `index.html` in a browser.
- **On your phone:** host the folder (e.g. GitHub Pages) and open the URL, or copy the folder to
  the phone and open `index.html`. (It's self-contained: `index.html` + `vendor/pokersolver.js`.)

## MVP scope (v0.1)
- No-Limit Hold'em.
- Inputs: your 2 cards, the board, # opponents, pot, amount-to-call.
- Output: equity %, pot odds %, recommended action + size + why, and your current made hand.

## Not yet (roadmap)
- Omaha / hi-lo (reuse the room's `bestOmahaHigh` / `bestLowOmaha`).
- Position + stack-depth inputs to sharpen preflop advice.
- Opponent-tendency input (the room's T3 "reads" layer).
- A fuller "why" trace and a hand-history/review log.

## Notes
- It knows only **your cards + the board** — opponents are modeled, not read. It's a math/strategy
  coach, not a mind-reader.
- Real-time assistance is banned in most cardrooms and online sites. Intended for **home games and
  study/drilling.**

Vendored: `pokersolver` v2.1.4 (MIT, GoldFire Studios) — see `vendor/pokersolver.LICENSE.md`.
