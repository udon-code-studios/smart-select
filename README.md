# SmartSelect

ML-powered League of Legends Champion Selector

<img alt="neural-network" src="https://i.imgur.com/z8dYqpV.png" width="150" />

## Vision

1. Solo Queue Champion Select tool which lets users input the current state of draft, then see ML-generated recommended picks (best to worst based on model, can be filtered by role, and by champion pool). Also shows chess-style draft win/loss prediction update with course of draft.

- In the future could feature a client overlay which integrates with the draft UI and updates in real-time to the draft.

2. Pro Play Champion Select tool which can be used by teams to aid drafting, or by broadcast with ML-generated win predictions and pick suggestions (would generate interesting discussion and add a sponsor spot opportunity e.g. Domino's Draft King Prediction, Wegman's Draft Winner).

## Training Features

Champion Features

- hard cc count: `num`
- has airborne: `bool`
- range type: `{melee, ranged}`
- damage type: `{ad, ap, mixed}`
- classes: `[{marksman, assassin, etc.}, ...]` (see: https://leagueoflegends.fandom.com/wiki/Champion_classes)
- gameplay type: `{pick, teamfight, poke, split}`

Champion Stats

- positional playrates:
  - top: `[0-1]`
  - jg: `[0-1]`
  - mid: `[0-1]`
  - bot: `[0-1]`
  - sup: `[0-1]`
- positional winrates:
  - top: `[0-1]`
  - jg: `[0-1]`
  - mid: `[0-1]`
  - bot: `[0-1]`
  - sup: `[0-1]`
- overall winrate (current patch): `[0-1]`

Examples

- picks (ordered) + predicted roles + bans -> game result

## ML Inputs

- pick/ban state: e.g. `{bans: ['Yasuo', ...], b1: 'Renekton', ...}`

## ML Outputs

- next pick possibilities (give each champ a pick score)
- projected odds
