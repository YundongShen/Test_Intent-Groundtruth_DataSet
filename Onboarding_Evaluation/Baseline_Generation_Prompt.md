# Baseline Generation Prompt

The Baseline Onboarding Document is generated from the complete, unprocessed test file with this prompt:

## Prompt

```text
You are helping a developer who has just joined this project. Below is one test file from the project's test suite.

Write an onboarding document in Markdown that helps this new team member understand the test suite: what it tests and what they should know before working on it.

Use only what the test file shows. Do not invent behavior that is not in the code.
Write in English, use no emoji, and keep it under {max_words} words.

Test file: {file_name}

{source}
```

## Placeholders

| Placeholder   | Value                    |
| ------------- | ------------------------ |
| `{file_name}` | the test file name       |
| `{source}`    | its complete source code |
| `{max_words}` | see **Word limit** below |

## Word limit

For each suite, `{max_words}` is the word count of its Intent Onboarding Document, rounded up to the next multiple of 50. This count uses the Intent version before an overview was added. For example, 452 words gives a 500-word limit.

## Model settings

Baseline generation uses Qwen3.5-27B, with thinking disabled and max_tokens set to 8000, as in the Intent generation setting.
