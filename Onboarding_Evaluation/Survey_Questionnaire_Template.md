# Test Suite Onboarding Survey Template

This task-based survey compares three ways of presenting a test suite. Participants see the tasks first, consult the assigned material as needed, then answer the tasks and rate their experience. They do not need to read the full material.

## Study design

Each participant completes three rounds. Each round uses a different test suite and one of three materials: Code, Baseline, or Intent. By the end, each participant has seen each material type once. Background answers are used for analysis, not assignment.

**Survey flow:** Background questions → Random assignment → In each round: Tasks → Reference material → Feedback.

## Background questions

| Question | Content | Purpose |
| --- | --- | --- |
| BG01 Primary role | Developer, tester, researcher, student, or other | Describe the sample and compare results across roles. |
| BG02 Automated testing experience | From no experience to several years of experience | Account for prior practical experience. |
| BG03 Prior familiarity | Familiarity with reading and writing tests, programming languages, and test frameworks | Account for prior knowledge when comparing materials. |

## Two parts of questions in each round

### Part 1: Task questions

The wording and correct answers depend on the test suite, but each question serves the same purpose across suites.

| Question | General template | Purpose |
| --- | --- | --- |
| Q1 Suite scope | “What does this test suite mainly verify?” | Assess whether the participant can quickly understand the suite as a whole. |
| Q2 Locate a case | “Given a specific problem, which existing test case should you inspect first?” | Assess whether the participant can identify a case relevant to the task. |
| Q3 Select an extension | “Which new test case best covers a scenario that is not yet tested?” | Assess whether the participant can choose a suitable way to extend the suite. |

Participants see these three questions before the assigned material, which is headed **Reference material**. The instructions tell them to consult the material as needed; they do not need to read it in full.

### Part 2: Experience feedback

All suites use the same five-point agreement scale.

| Statement | Purpose |
| --- | --- |
| I quickly understood what this test suite tests. | Perceived ease of understanding the suite. |
| I quickly understood what the test cases verify. | Perceived ease of understanding the cases. |
| I easily found the test case relevant to the task. | Perceived ease of locating a relevant case. |
| I easily decided what new test case to add. | Perceived ease of choosing an extension. |

The main outcomes are accuracy on the three task questions and the reported experience ratings. Q2 measures selection of a relevant case, not actual navigation to a code line. Q3 measures selection of a proposed test, not the ability to write it. Ratings about speed are self-reports, not measured task times.
