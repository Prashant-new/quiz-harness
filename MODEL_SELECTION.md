# Model selection — Quiz application harness

Date: November 1, 2026  
Selected model: **Big Pickle**, accessed through OpenCode.

## Method

We compared three models using the same prompt: inspect `server.py`, explain answer validation, session management and scoring, identify a possible retry problem, and run `python tools/check_questions.py` and `python -m py_compile main.py server.py` without modifying source files.

The results below come from the recorded OpenCode screenshots. This was one guided task per model, not a general coding benchmark. The prompt directed attention to retry behavior; it did not measure independent bug discovery.


## Decision and justification

We selected **Big Pickle** because it successfully completed our analysis task, ran the required checks, identified the suspected defect, and had a shorter visible total duration than DeepSeek in our recorded runs. Its free access also suits our student-project budget. Nemotron completed the same task, but its total completion time was unavailable, so we cannot claim Big Pickle was the fastest of all three.

Privacy is a trade-off rather than a reason to prefer Big Pickle. Its free-period data may be used to improve the model. This does **not** establish that data is used only for training or that confidentiality is guaranteed. For this project, our intended use is non-sensitive quiz code and synthetic examples; we will not submit passwords, API keys, personal student records or confidential material. If stronger privacy becomes necessary, we will reconsider the model and hosting arrangement. DeepSeek's documented provider retention and training conditions are more restrictive than Big Pickle's on these criteria.

## Limits and interpretation

- All three models acknowledged that code inspection did not reproduce the retry problem against a live server in these comparison runs.
- The question checker validates question-bank structure. Compilation checks syntax. Neither proves that the quiz behaves correctly at runtime.
- Model-weight licences and hosted-service terms are different. We recorded hosted access conditions and explicitly marked unverified model licences instead of guessing.
- Free access and policies can change. The choice is provisional and should be reviewed as the project develops.

## Sources

Official pages

1. [OpenCode models: model list, pricing, free models and privacy](https://opencode.ai/v2/docs/console/models/). Covers the exact three display names used in the comparison and their model-specific privacy conditions.
2. [OpenCode Terms of Use](https://opencode.ai/legal/terms-of-service). Distinguishes hosted-service terms from the licence of the open-source client.
3. [OpenCode Privacy Policy](https://opencode.ai/legal/privacy-policy). General policy for personal data processed by the service; supplements the model-specific statements.


