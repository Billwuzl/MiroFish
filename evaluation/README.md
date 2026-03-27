# MiroFish Prediction Evaluation

## Purpose

Track MiroFish prediction accuracy against Polymarket pricing and actual outcomes.

## How to Run a Prediction

1. Write a seed document in `seeds/<question-id>.md`
2. Note the current Polymarket YES price and URL
3. Start MiroFish: `npm run dev` from the MiroFish root
4. Open http://localhost:3000
5. Create new prediction → paste seed document content
6. Set agent count and rounds, start simulation
7. After completion, interview agents: "What is your probability estimate (0-100%) that [question]?"
8. Compute median of agent responses
9. Add a row to `tracking.csv`
10. Write observations in `notes/<run-id>.md`

## Model Config

Edit `.env` in MiroFish root:

| Model | .env value | Cost/run | Use for |
|-------|-----------|----------|---------|
| qwen-flash | `LLM_MODEL_NAME=qwen-flash` | ~¥3 | Smoke tests |
| qwen-plus | `LLM_MODEL_NAME=qwen-plus` | ~¥12 | Real predictions |

## Tracking Format

See `tracking.csv` header for field definitions.
Full spec: `../docs/superpowers/specs/2026-03-26-mirofish-evaluation-design.md` (in parent project)
