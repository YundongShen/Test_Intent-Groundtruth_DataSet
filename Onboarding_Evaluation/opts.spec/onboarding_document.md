## Test Suite Overview

**Suite ID:** TRIANGLIFY-OPTS-SUITE-01
**Test cases:** 7

This suite verifies that the getSizes and getVariances functions correctly parse, default, and validate resolution and variance options provided as input.

- **Trianglefy Options Validation**
  - **Unique Dependencies:** `./opts`
  - **TC-TRIANGLIFY-01:** Default Value Checks (dependencies: `./opts`)
  - **TC-TRIANGLIFY-02:** Single Resolution Parse (dependencies: `./opts`)
  - **TC-TRIANGLIFY-03:** Multiple Resolutions Parse (dependencies: `./opts`)
  - **TC-TRIANGLIFY-04:** Invalid Resolution Reject (dependencies: `./opts`)
  - **TC-TRIANGLIFY-05:** Single Variance Parse (dependencies: `./opts`)
  - **TC-TRIANGLIFY-06:** Multiple Variances Parse (dependencies: `./opts`)
  - **TC-TRIANGLIFY-07:** Invalid Variance Reject (dependencies: `./opts`)

---

## Group 1: TC-TRIANGLIFY-01

**Shared testing question:** Do the functions return correct default values when invoked without arguments?

### `TC-TRIANGLIFY-01` - Default Value Checks

**Test Objects**

The `getSizes` and `getVariances` functions

**Test Goals**

Confirm that both functions return reasonable default values when no arguments are passed.

**Test Activities**

- Step 1: Call `getSizes()` without arguments and use snapshot assertion to check the return value.
- Step 2: Call `getVariances()` without arguments and use snapshot assertion to check the return value.

---

## Group 2: TC-TRIANGLIFY-02, TC-TRIANGLIFY-03, TC-TRIANGLIFY-05, TC-TRIANGLIFY-06

**Shared testing question:** How do the functions parse valid input strings (single or multiple) into the expected data structures?

### `TC-TRIANGLIFY-02` - Single Resolution Parse

**Test Objects**

The `getSizes` function

**Test Goals**

Verify that a single resolution string is correctly parsed into an array of sizes.

**Test Activities**

- Step 1: Call `getSizes('200x200')`.
- Step 2: Assert the result as `[{ h: 200, w: 200 }]`.

### `TC-TRIANGLIFY-03` - Multiple Resolutions Parse

**Test Objects**

The `getSizes` function

**Test Goals**

Verify that an array of multiple resolution strings is correctly parsed into an array of objects of corresponding sizes.

**Test Activities**

- Step 1: Call `getSizes(['100x200', '300x400'])`.
- Step 2: Assert the result as `[{ w: 100, h: 200 }, { w: 300, h: 400 }]`.

### `TC-TRIANGLIFY-05` - Single Variance Parse

**Test Objects**

The `getVariances` function

**Test Goals**

Verify that a single variance string can be correctly parsed as an array.

**Test Activities**

- Step 1: Call `getVariances('0.61')`.
- Step 2: Assert the result as `[0.61]`.

### `TC-TRIANGLIFY-06` - Multiple Variances Parse

**Test Objects**

`getVariances` function

**Test Goals**

Verifies that multiple variance string arrays can be correctly parsed into corresponding numeric arrays.

**Test Activities**

- Step 1: Call `getVariances(['0.333', '0.1', '1'])`.
- Step 2: Assert the result as `[0.333, 0.1, 1]`.

---

## Group 3: TC-TRIANGLIFY-04, TC-TRIANGLIFY-07

**Shared testing question:** Do the functions correctly reject invalid or out-of-range inputs by throwing exceptions?

### `TC-TRIANGLIFY-04` - Invalid Resolution Reject

**Test Objects**

The `getSizes` function

**Test Goals**

An exception is thrown if an incorrectly formatted resolution string is passed in.

**Test Activities**

- Step 1: Call `getSizes('100xFoo')`.
- Step 2: The assertion function throws an exception.

### `TC-TRIANGLIFY-07` - Invalid Variance Reject

**Test Objects**

`getVariances` function

**Test Goals**

Throws an exception if an out-of-range or invalid variance value is passed in.

**Test Activities**

- Step 1: Call `getVariances('1.1')`, `getVariances('-1')`, and `getVariances('foo')` respectively.
- Step 2: Assert that an exception is thrown on each call.