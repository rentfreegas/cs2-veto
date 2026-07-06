# CS2 Veto Predictor

**Live app: https://rentfreegas.github.io/cs2-veto/**

Predicts the map veto for any professional Counter-Strike 2 matchup — each
team's expected bans and picks, the most likely full veto sequence, and the
probability that each map gets played.

## How it works

Pro teams are creatures of habit: two thirds of them ban the same map first
in at least 8 of their last 10 vetos. This app models the veto as a sequence
of choices — at every step, a model scores each remaining map from both
teams' recent veto tendencies (recency-weighted ban/pick rates, map form,
and what the *opponent* is likely to want) and then walks every possible
veto path to produce exact probabilities.

Everything runs **in your browser**. The model weights and team profiles
(500+ teams, built from public veto records) are baked into a single HTML
file. No backend, no accounts, no tracking, no cookies.

## Accuracy

Measured on 2,194 held-out pro matches (Apr–Jul 2026) the model had never
seen, with the acting order unknown (true pre-match conditions):

| What | Hit rate |
|---|---|
| A team's first ban | 81% |
| A team's map pick | 55% |
| At least 2 of the 3 maps played in a BO3 | 86% |
| All 3 maps exactly | 32% |
| All 3 played maps within its top-4 | 62% |

(Random guessing gets a first ban right 14% of the time.)

## Notes

- Not affiliated with Valve, Counter-Strike, or HLTV.
- Predictions are for entertainment — pros occasionally surprise everyone,
  which is why they're pros.
- Team profiles reflect the data snapshot shown in the app footer and are
  refreshed periodically.
