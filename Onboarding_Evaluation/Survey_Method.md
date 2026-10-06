# Survey Method

## Aim

This study compares three ways to read the same test suite.

- **Research Question(GG):** To what extent can an onboarding document, based on extracted test intent, support a practitioner in comprehending and extending a test suite?
- **Research Question(YD):** To what extent does an onboarding document support new testers’ comprehension of a test suite in task-based scenarios (e.g.,changing the tests)?
- **Measured:** The survey measures perceived support.


### Conditions
- **Survey Method:** We use a between-subjects design, so each participant sees only one condition; this avoids carry-over between conditions and keeps the survey short.

Each suite has three conditions:

| Condition | Name                                  | Material                                                                      |
| :-------: | ------------------------------------- | ----------------------------------------------------------------------------- |
|   **A**   | Code only                             | the original test file.                                                       |
|   **B**   | Code and Baseline Onboarding Document | the same test file and a general onboarding document.                         |
|   **C**   | Code and Intent Onboarding Document   | the same test file and an onboarding document based on extracted test intent. |

### Controls

- The code is identical across conditions for a given suite(maybe 3 test suite? I am not sure).
- The questions are identical across all three conditions(B and C has one more document than A, so the question settings will be slightly adjusted...i think).
- The material versions are fixed before recruitment.
- B and C use the same screen layout, a little adjusted on A.

## Participants and assignment

### Assignment

- **Number of suite 1 participant read:** Each participant sees one suite in one condition.
- **No same suite:** No participant sees the same suite or another condition later.
- **Random distribution:** We assign participants at random within each suite, keeping A, B, and C as balanced as possible.
- **Background of participant:** The background answers do not decide the condition. Only used in analysis

### Sample size

- **Numbers of participants:** 60??? (so 20 per condition). And make sure they will finish whole task.

## Survey flow(questions)

1. **Background.** Simple background eliminates background interference
2. **Instructions.** The participant sees the study instructions and selects **Ready to start**.
3. **Material.** The instructions collapse. The assigned material appears. The participant may return to it while answering.
4. **Questions.** The same two question groups appear in A, B, and C.

## Background Questions

**BG01 question:**  Which best describes your current primary role? (Single slection)
   - Software developer / engineer
   - Software test / QA engineer
   - Researcher / academic
   - Others (could input something here)

**BG02 question:**  How long have you worked with automated software tests (reading, writing, or maintaining them)? (Single slection)
   - Less than 1 year
   - 1 to less than 3 years
   - 3 to less than 6 years
   - 6 years or more
     
**BG03 question:**  Before this study, how familiar were you with the following? (1-5 Rating)
   - 	Reading JavaScript or TypeScript test code
   - 	Reading Java (JUnit) test code
   - 	Jest or Bun test
   - 	Browser end-to-end testing (Playwright or Cypress)

## instruction text

> You will see one test suite and its material (if any). The material is an onboarding document for this test suite. Read as much as you need. Then answer a few short questions about your impressions. Please base your answers only on what is shown here.


## A or B or C Materials

## Question group 1: Comprehension Questions

**Main question:** After reading the material, how clear is your overall comprehension of this test suite?

| Level | Response                        |
| :---: | ------------------------------- |
|   1   | Not at all clear                |
|   2   | Slightly clear                  |
|   3   | Moderately clear                |
|   4   | Very clear                      |
|   5   | Extremely clear                 |
|   —   | Cannot judge from this material | If chose this choise need to type why

**Items:** For the items below, ask: **How clear are these parts of the suite?**
1. The behavior or part of the system being tested. (Rating 1-5)
2. Why each existing test case is included. (Rating 1-5)
3. How each test's actions and assertions check its intended behavior. (Rating 1-5)
4. How the cases are grouped and relate to each other. (Rating 1-5)
(Form my side, I think these aspect could find why they understang or not understand thsi test suite)

**Opital: Why question:** Which specific part of the material most shaped your understanding of the suite, and why? What remains unclear?(maybe we can remove this just too much question i think)

## Question group 2: Planning a new test case

**Main question:** If you needed to add a test case to this suite, how much would the material help you plan it?

| Level | Response                        |
| :---: | ------------------------------- |
|   1   | Not at all                      |
|   2   | A little                        |
|   3   | A moderate amount               |
|   4   | A lot                           |
|   5   | A great deal                    |
|   —   | Cannot judge from this material |If chose this choise need to type why

**Items:** For the items below, ask: **How much would the material help you with these steps?**
1. Checking whether a proposed case would repeat an existing test.(Rating 1-5)
2. Finding an existing test case to use as a starting point.(Rating 1-5)
3. Deciding which behavior or condition to test next.(Rating 1-5)
4. Deciding what inputs and expected results a new case would need.(Rating 1-5)

**Opital: Why question:** What information in the material would you rely on first when planning a new test case? What would you still need to find elsewhere?(maybe we can remove this just too much question i think)

## Analysis

### Check

In my opinion, Before conducting a formal survey, we need to have a face-to-face meeting with two or three people to ask them some questions. 

### Background comparison

- We first show a background table for A, B, and C: group size, roles, automated-testing experience, and prior familiarity.
- We report counts and percentages for roles and experience categories, and the distribution of BG03 ratings.
- We check for large differences across groups.
  
### Main comparisons

The main comparisons are **C versus A** and **C versus B**.

1. We can compare the scores of C and A, C and B, Comprehension support, and task support (extension and rewriting test) by comparing the main questions.
2. We can compare the subdivided questions to see in which aspect the material provides good support (explaining why the material can provide support).
3. By actively inputting questions, we can obtain more perspectives.

We will got
- a background table,
- a five-level response chart for each question group,
- a chart of the C–A and C–B differences for the two main questions, and


