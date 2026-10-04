# Test Suite Onboarding Survey Template

This questionnaire compares three ways to present a test suite: its source code, a baseline onboarding document, and a Test Intent onboarding document. Participants use the assigned material to answer task questions. They do not need to read the material from start to finish.

Each participant completes three rounds. Each round uses a different test suite and one material type. Across the three rounds, each participant sees each material type once. Suite order and material order are assigned at random. Background answers do not affect assignment.

## Background

### Primary role

**Question:** Which best describes your current primary role?

**Response options:**

- Software developer or engineer
- Software test or QA engineer
- Researcher or academic
- Student
- Other, with a text field

**Purpose:** Describe the sample and check whether responses differ by role.

### Automated testing experience

**Question:** How long have you worked with automated software tests, including reading, writing, or maintaining them?

**Response options:**

- No experience
- Less than 1 year
- 1 to less than 3 years
- 3 to less than 5 years
- 5 years or more

**Purpose:** Record practical testing experience before the survey.

### Prior familiarity

**Question:** Before this study, how familiar were you with the following?

**Items:**

- Reading automated tests in an unfamiliar project
- Writing or extending automated test cases
- Reading JavaScript test code
- Reading TypeScript test code
- Reading Java test code
- JUnit
- Jest
- Bun test
- Playwright
- Cypress

**Response scale:** 0 = Not at all familiar; 1 = Slightly familiar; 2 = Moderately familiar; 3 = Quite familiar; 4 = Very familiar.

**Purpose:** Record prior knowledge of the tasks, languages, and frameworks. These answers are used in analysis, not to assign materials.

## Repeated round

Use the same structure for every test suite and every material type. Write one set of task questions for each suite. Show that set without changing its wording across the three material types.

### Task instructions

> First, review the three questions below. Then use the material to find the answers. You do not need to read the entire material; focus on the parts relevant to each question. Return to the questions after consulting the material.

### Task 1: Identify the suite scope

**Question:** Which statement best describes what this test suite verifies?

**Response format:** One choice from four suite-specific statements. Include one correct description and three plausible but incorrect descriptions.

**Purpose:** Test whether the participant can identify the suite's overall scope.

### Task 2: Identify a relevant test case

**Question template:** A change causes [specific failure or observed behavior]. Which existing test case would you inspect first?

**Response format:** One choice from four existing test cases in the suite. The scenario must point to one case without relying on information absent from a material.

**Purpose:** Test whether the participant can identify the case most relevant to a concrete task. This question does not measure the exact time taken to find it or whether the participant opened a particular code line.

### Task 3: Select a useful new test

**Question template:** A new test is needed for [behavior not covered by the current suite]. Which proposed test best adds this coverage?

**Response format:** One choice from four proposed tests. Only one proposal should cover the stated gap without merely repeating an existing case.

**Purpose:** Test whether the participant can select a suitable extension to the suite. This question does not measure whether they can write or run the test.

### Assigned material

Show a clear heading, **Reference material**, followed by the material assigned for this round. Show only one of the following:

- Source test code
- Baseline onboarding document
- Test Intent onboarding document

The material appears after the three task questions and before the feedback question. The participant may return to the task questions while reading it.

### Feedback

**Question:** How was your experience using this material?

**Instruction:** Rate each statement based on the material you just used.

**Items:**

- I quickly understood what this test suite tests.
- I quickly understood what the test cases verify.
- I easily found the test case relevant to the task.
- I easily decided what new test case to add.

**Response scale:** Strongly disagree; Disagree; Neutral; Agree; Strongly agree.

**Purpose:** Record perceived ease of understanding, finding a relevant case, and choosing an extension. These ratings are self-reports, not measured task times.

## Scoring and records

Score each task question as correct or incorrect using a suite-specific answer key kept outside the participant questionnaire. The three task scores can be summed within a round, from 0 to 3. Keep the four feedback ratings as separate measures unless a combined score is justified later.

Record the participant's background answers, round number, suite ID, material type, assignment order, task responses, feedback ratings, and completion status. Check each suite's questions against its source test file before release. Use the same answer key for all three materials of that suite.
