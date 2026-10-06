# Survey Method

## Aim

This study compares three ways to read the same test suite. It asks whether an Intent Onboarding Document changes how well readers think they understand the suite and how well they think they could plan a new test case. The survey measures perceived support. It does not measure test accuracy or the ability to write a working test.

## Materials

Each suite has three conditions:

- **A — Code only:** the original test file.
- **B — Code and Baseline Onboarding Document:** the same test file and a general onboarding document.
- **C — Code and Intent Onboarding Document:** the same test file and an onboarding document based on extracted test intent.

The code is identical across conditions for a given suite. The questions are identical across all three conditions. The material versions are fixed before recruitment. We record the word count of each document. B and C use the same screen layout.

The Baseline Onboarding Document is generated from the complete, unprocessed test file with this prompt:

    You are helping a developer who has just joined this project. Below is one test file from the project's test suite.

    Write an onboarding document in Markdown that helps this new team member understand the test suite: what it tests and what they should know before working on it.

    Use only what the test file shows. Do not invent behavior that is not in the code.
    Write in English, use no emoji, and keep it under {max_words} words.

    Test file: {file_name}

    {source}

Here, {file_name} is the test file name, and {source} is its complete source code. For each suite, {max_words} is the word count of its Intent Onboarding Document, rounded up to the next multiple of 50. This count uses the Intent version before an overview was added. For example, 452 words gives a 500-word limit. Baseline generation uses Qwen3.5-27B, with thinking disabled and max_tokens set to 8000, as in the Intent generation setting.

## Participants and assignment

Each participant sees one suite in one condition. No participant sees the same suite or another condition later. We assign participants at random within each suite, keeping A, B, and C as balanced as possible. The background answers do not decide the condition.

We aim for 60 complete responses, about 20 per condition. If three suites are used, we aim for about 6–7 complete responses per suite and condition. We record how many people start and finish each condition. The study is exploratory; this sample is not intended to detect small differences or support detailed comparisons between roles. Recruitment ends at the planned sample target or a stated closing date, not when a preferred result appears.

## Survey flow

1. **Background.** BG01 asks for the participant's current role. BG02 asks about experience with automated tests. BG03 records prior familiarity with reading and writing tests, relevant languages, and test frameworks. BG03 is one background question group, not an outcome measure.
2. **Instructions.** The participant sees the study instructions and selects **Ready to start**.
3. **Material.** The instructions collapse. The assigned material appears. The participant may return to it while answering.
4. **Questions.** The same two question groups appear in A, B, and C.

Suggested instruction text:

> You will see one test suite and material about it. Read as much as you need. Then answer questions about your understanding and how the material might help you add a test case. You do not need to write a test. There are no right or wrong answers. Please base your answers only on the material shown here.

The page must not tell participants which condition they received or suggest that one document is better.

## Question group 1: Understanding the test suite

**Main question:** After reading the material, how clear is your understanding of this test suite overall?

Use the same response options for the main question and the four items below: **Not at all clear / Slightly clear / Moderately clear / Very clear / Extremely clear**. Add **Cannot judge from this material** as a separate option.

For the items below, ask: **How clear are these parts of the suite?**

1. The behavior or part of the system being tested.
2. Why each existing test case is included.
3. How each test's actions and assertions check its intended behavior.
4. How the test cases fit together.

**Why question:** Which specific part of the material most shaped your understanding of the suite, and why? What remains unclear?

## Question group 2: Planning a new test case

**Main question:** If you needed to add a test case to this suite, how much would the material help you plan it?

Use the same response options for the main question and the four items below: **Not at all / A little / A moderate amount / A lot / A great deal**. Add **Cannot judge from this material** as a separate option.

For the items below, ask: **How much would the material help you with these steps?**

1. Checking whether a proposed case would repeat an existing test.
2. Finding an existing test case to use as a starting point.
3. Deciding which behavior or condition to test next.
4. Deciding what inputs and expected results a new case would need.

**Why question:** What information in the material would you rely on first when planning a new test case? What would you still need to find elsewhere?

These are judgments about the material. Participants do not choose, design, or write an actual test case.

## Pilot and analysis

Before recruitment, we ask 6–9 people to try the survey. We check whether the instructions and questions are clear, whether the survey is too long, and whether participants can answer the two planning items without a specific change request. We revise the survey before the main study. Pilot responses are not included in the analysis.

The two main questions are the primary outcomes. The four items in each group explain which parts of understanding or planning participants found easier or harder. We do not treat all items as one score unless a later validation supports that choice.

We first show a background table for A, B, and C: group size, roles, automated-testing experience, and prior familiarity. We report counts and percentages for roles and experience categories, and the distribution of BG03 ratings. We check for large differences across groups. We do not use a non-significant test as proof that the groups are identical.

The main comparisons are **C versus A** and **C versus B**. For each primary outcome, we show all five response levels by condition. The top two response levels count as a high rating. We report the share of high ratings, the difference between conditions, and a 95% confidence interval. The other items are reported separately. We count and show **Cannot judge** responses; we do not treat them as the middle of the scale. As a check, we fit an ordinal regression with condition, assigned suite, and BG02 experience. If the data are too sparse for a stable model, we report only the direct group comparisons and say so. With this sample size, estimates and their uncertainty matter more than a pass/fail significance result.

We review the open answers for concrete reasons. Two researchers first code a sample of answers independently, agree on a short set of themes, then code the rest. Themes may include useful explanations, missing context, hard-to-find information, and unclear links between the document and code. We compare the themes across A, B, and C and include short anonymous examples.

The results should include a background table, a five-level response chart for each question group, a chart of the C–A and C–B differences for the two main questions, and a short theme table. We will describe the findings as perceived support for understanding and planning an extension. We will not claim that the study measured actual understanding, speed, or test-writing performance.

## Sources for question design

- Yu, Treude, and Aniche, [Comprehending Test Code: An Empirical Study](https://mauricioaniche.com/publications/test-code-comprehension/).
- Winkler, Urbanke, and Ramler, [Investigating the Readability of Test Code](https://link.springer.com/article/10.1007/s10664-023-10390-z).
- Ju et al., [A Case Study of Onboarding in Software Teams](https://arxiv.org/abs/2103.05055).
