# Test Intent Groundtruth Dataset

This repository contains the source test artifacts, LLM extraction outputs, and
reference (Groundtruth) test intents used for evaluating automated Test Intent
extraction. A test intent is represented as a triplet: Test Object, Test Goal,
Test Activities.

## Directory Structure

```
Test_Case/           Original test artifacts, organized by test suite and framework
LLM_Extraction/      Extracted test intents, organized by model and prompting strategy
Groundtruth/         Reference test intents, split to test-case level
Comparison_Results/  Per-test-case alignment verdicts, LLM extraction vs. Groundtruth
Peer_Review/         Independent manual annotation records preceding the LLM-assisted pass
Onboarding_Evaluation/ Materials for evaluating generated Onboarding Documents
```

### Test_Case/

98 original test suite files across 13 frameworks: `cucumber`, `cypress`,
`jest_spec`, `jest_test`, `junit_spring`, `junit_unit`, `k6`, `locust`,
`playwright`, `pytest_api`, `pytest_unit`, `rtl`, `supertest`.

### LLM_Extraction/

Extraction results for 210 test files, organized as `<Model>/<Strategy>/<framework>/`.

| Model | Independent | Combined | Chain |
|---|---|---|---|
| Qwen3.5-27B | yes | yes | yes |
| DeepSeek-7B | yes | - | - |
| Gemini-2.5-Flash | yes | - | - |
| Gemini-3.1-Pro | yes | - | - |

Combined and Chain extraction were only run with Qwen3.5-27B; the other three
models were only run with Independent extraction.

### Groundtruth/

Reference test intents, split from the 98 test suites down to individual test
case level (one file per test case; suites containing more than one test case
use a `_1`, `_2`, ... suffix). Each record was first produced by LLM extraction
and then manually reviewed and corrected.

### Comparison_Results/

`test_intent_alignment.csv` — one row per test case, with the alignment
verdict (Fully Aligned / Partially Aligned / Misaligned) for each of the six
model and prompting-strategy combinations in `LLM_Extraction/`, obtained by
comparing each extraction against its Groundtruth record.

### Peer_Review/

Spreadsheet with the original independent annotations from three researchers
per test case (objects, goals, activities), their agreement level, and the
revised version used as the basis for `Groundtruth/`.

### Onboarding_Evaluation/

Materials for evaluating generated Onboarding Documents: a set of test
suites paired with their generated Onboarding Document, plus a help page
explaining how to read one. Survey results from this evaluation will be
added here.

## Dataset Composition

98 test suites split into 210 test cases.

| Test cases per suite | Number of suites | Percentage | Cumulative test cases |
|---|---|---|---|
| 1 | 44 | 44.9% | 44 |
| 2 | 21 | 21.4% | 42 |
| 3 | 19 | 19.4% | 57 |
| 4 | 9 | 9.2% | 36 |
| 5 | 2 | 2.0% | 10 |
| 6 | 1 | 1.0% | 6 |
| 7 | 1 | 1.0% | 7 |
| 8 | 1 | 1.0% | 8 |
| Total | 98 | 100% | 210 |

## Extraction Alignment Results

Each extracted test intent was compared against its corresponding Groundtruth
record and labeled **Fully Aligned**, **Partially Aligned**, or **Misaligned**
based on semantic correspondence of the object, goal, and activities.

### By prompting strategy (model fixed: Qwen3.5-27B), n=210

| Strategy | Fully Aligned | Partially Aligned | Misaligned |
|---|---|---|---|
| Independent | 178 (84.8%) | 31 (14.8%) | 1 (0.5%) |
| Combined | 111 (52.9%) | 72 (34.3%) | 27 (12.9%) |
| Chain | 131 (62.4%) | 30 (14.3%) | 49 (23.3%) |

### By model (strategy fixed: Independent), n=210

| Model | Fully Aligned | Partially Aligned | Misaligned |
|---|---|---|---|
| DeepSeek-7B | 54 (25.7%) | 73 (34.8%) | 83 (39.5%) |
| Qwen3.5-27B | 178 (84.8%) | 31 (14.8%) | 1 (0.5%) |
| Gemini-2.5-Flash | 170 (81.0%) | 36 (17.1%) | 4 (1.9%) |
| Gemini-3.1-Pro | 190 (90.5%) | 19 (9.0%) | 1 (0.5%) |

### By test category (model: Qwen3.5-27B, strategy: Independent)

| Category | n | Fully Aligned | Partially Aligned | Misaligned |
|---|---|---|---|---|
| Unit | 91 | 79 (86.8%) | 11 | 1 |
| Integration | 11 | 11 (100.0%) | 0 | 0 |
| API | 32 | 22 (68.8%) | 10 | 0 |
| Browser Automation | 45 | 37 (82.2%) | 8 | 0 |
| Performance | 12 | 12 (100.0%) | 0 | 0 |
| BDD | 19 | 17 (89.5%) | 2 | 0 |
