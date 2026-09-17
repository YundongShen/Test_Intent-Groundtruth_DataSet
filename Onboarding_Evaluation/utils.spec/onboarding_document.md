## Test Suite Overview

**Suite ID:** LEVENSTEIN-SUITE-01
**Test cases:** 5

This suite verifies that the levenstein function correctly computes the edit distance between pairs of strings by testing identical strings, completely different strings, and various email address variations.

- **Levenshtein Edit Distance Verification**
  - **Unique Dependencies:** `chai`, `./utils`
  - **TC-LEVENSTEIN-01:** Same String Distance (dependencies: `chai`, `./utils`)
  - **TC-LEVENSTEIN-02:** Different String Distance (dependencies: `chai`, `./utils`)
  - **TC-LEVENSTEIN-03:** Similar Email Distance (dependencies: `chai`, `./utils`)
  - **TC-LEVENSTEIN-04:** Different Email Distance (dependencies: `chai`, `./utils`)
  - **TC-LEVENSTEIN-05:** Complex String Distance (dependencies: `chai`, `./utils`)

---

## Group 1: TC-LEVENSTEIN-01, TC-LEVENSTEIN-02, TC-LEVENSTEIN-03, TC-LEVENSTEIN-04, TC-LEVENSTEIN-05

**Shared testing question:** Does the Levenshtein function correctly calculate the edit distance between two strings?

### `TC-LEVENSTEIN-01` - Same String Distance

**Test Objects**

The `levenstein` function

**Test Goals**

Verify that the edit distance between two same strings is calculated correctly.

**Test Activities**

- Step 1: Call `levenstein('aaa', 'aaa')`.
- Step 2: Assert the return value to 0.

### `TC-LEVENSTEIN-02` - Different String Distance

**Test Objects**

The `levenstein` function

**Test Goals**

Verify that the edit distance between two different strings is calculated correctly.

**Test Activities**

- Step 1: Call `levenstein('abc', 'def')`.
- Step 2: Assert the return value to 3.

### `TC-LEVENSTEIN-03` - Similar Email Distance

**Test Objects**

The `levenstein` function

**Test Goals**

Verify that the edit distance between two same email strings is calculated correctly.

**Test Activities**

- Step 1: Call `levenstein('gmail.com', 'gnail.com')`.
- Step 2: Assert the return value to be 1.

### `TC-LEVENSTEIN-04` - Different Email Distance

**Test Objects**

`levenstein` function

**Test Goals**

Verify that the edit distance between two different email strings is calculated correctly.

**Test Activities**

- Step 1: Call `levenstein('gmail.com', 'gnaul.com')`.
- Step 2: Assert the return value to be 2.

### `TC-LEVENSTEIN-05` - Complex String Distance

**Test Objects**

`levenstein` function

**Test Goals**

Verify that the edit distance between two strings is calculated correctly.

**Test Activities**

- Step 1: Call `levenstein('mail.com', 'gnaul.com')`.
- Step 2: Assert the return value to be 3.