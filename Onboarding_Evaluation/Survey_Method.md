# Survey Method

## Materials

Each test suite has three material conditions: the original test file (Code), a general onboarding document (Baseline), and a test-intent document (Intent). The Baseline document is generated from the full, unprocessed test file with this prompt:

```text
You are helping a developer who has just joined this project. Below is one test file from the project's test suite.

Write an onboarding document in Markdown that helps this new team member understand the test suite: what it tests and what they should know before working on it.

Use only what the test file shows. Do not invent behavior that is not in the code.
Write in English, use no emoji, and keep it under {max_words} words.

Test file: {file_name}

{source}
```

Here, `{file_name}` is the test file name, such as `csp.spec.ts`, and `{source}` is its complete source code without preprocessing. For each suite, `{max_words}` is the word count of its Intent document, rounded up to the next multiple of 50. The count uses the Intent document *before* an overview was added. For example, 452 words gives a 500-word limit.

Baseline generation uses Qwen3.5-27B, with thinking disabled and `max_tokens` set to 8000, matching the Intent generation settings.

## Study design

Each participant completes three rounds: one for each material type, with a different test suite in each round. Suite and material assignments are randomized to limit order effects. Three rounds keep the workload manageable. A participant sees each suite only once so that familiarity with the same test cases does not make a later material easier to use.

In each round, participants see the three task questions before the assigned material. They can consult the material as needed rather than read it in full. The questions have the same purpose across suites: identify the suite's scope, locate a relevant existing test case, and select a useful new test case. The specific questions and correct answers depend on the suite. Feedback follows the material and tasks. Background questions record role, automated testing experience, and prior familiarity for analysis; they do not determine assignment.

## Planned analysis

- **Suite understanding:** Accuracy on the scope question and ratings of how easily participants understood the suite and its test cases.
- **Task support:** Accuracy on locating an existing case and choosing a new case, alongside ratings of how easily participants made those decisions.
- **Participant groups:** Task accuracy and experience ratings by role, automated testing experience, and prior familiarity.
