# Sources

Links only.

## Specification

- Afterstring Module 4.5, Fail-Close Runtime Governor, "An Earlier Yes Is Not an Endless One". Platinum, 22 Oct 2026. X Article 2113390407216406917: https://x.com/i_am_Paddy_Sham/status/2113390407216406917

## Model

- Gemma 4 E4B, instruction-tuned, 4-bit, MLX: `mlx-community/gemma-4-e4b-it-4bit`, revision `475b9088d29754a3379866cf5aeb6b41acd313c2`. No weights are included. Model card: https://huggingface.co/mlx-community/gemma-4-e4b-it-4bit. Licence note: that card lists its licence as `gemma`; its base model, `google/gemma-4-E4B-it` (https://huggingface.co/google/gemma-4-E4B-it), is listed as Apache 2.0.

## Software

- Python standard library (`unittest`), Python 3.9 as reported by the Builder. The model adapter would import mlx-lm, which was not installed and never pinned (no lock file exists). No mlx-lm version was ever chosen.

## Method

- One-sided exact binomial (Clopper-Pearson) bounds. Clopper, C. J. and Pearson, E. S. (1934). The use of confidence or fiducial limits illustrated in the case of the binomial. Biometrika 26(4): 404–413. https://doi.org/10.1093/biomet/26.4.404

## Related work

- `afterstring-local-model-eval`: https://github.com/IAmPaddySham/afterstring-local-model-eval (where the reachability question came from: the published B6 result).
- `afterstring-model-collapse-toy`: https://github.com/IAmPaddySham/afterstring-model-collapse-toy (the same one-question, one-run discipline).
