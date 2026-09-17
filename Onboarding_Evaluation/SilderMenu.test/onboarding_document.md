## Test Suite Overview

**Suite ID:** MENU-MATCH-SUITE-01
**Test cases:** 5

This suite verifies how the getMeunMatcheys function matches a requested URL path against a fixed list of menu routes.

- **Menu Path Matching**
  - **Unique Dependencies:** `./SiderMenu`
  - **TC-MENU-01:** Exact Path Match (dependencies: `./SiderMenu`)
  - **TC-MENU-02:** Non-Matching Path (dependencies: `./SiderMenu`)
  - **TC-MENU-03:** Nested Path Match (dependencies: `./SiderMenu`)
  - **TC-MENU-04:** Parameterized Path Match (dependencies: `./SiderMenu`)
  - **TC-MENU-05:** Nested Parameterized Match (dependencies: `./SiderMenu`)

---

## Group 1: TC-MENU-01, TC-MENU-03, TC-MENU-04, TC-MENU-05

**Shared testing question:** Does the menu matching function correctly identify and return matches for various path structures including exact, nested, and parameterized routes?

### `TC-MENU-01` - Exact Path Match

**Test Objects**

The `getMeunMatcheys` function

**Test Goals**

Verify that an exact simple path is correctly matched.

**Test Activities**

- Step 1: Call `getMeunMatcheys(meun, '/dashboard')`.
- Step 2: Assert the return value as `['/dashboard']`.

### `TC-MENU-03` - Nested Path Match

**Test Objects**

The `getMeunMatcheys` function

**Test Goals**

Verify that a second-level path is correctly matched.

**Test Activities**

- Step 1: Call `getMeunMatcheys(meun, '/dashboard/name')`.
- Step 2: Assert the return value as `['/dashboard/name']`.

### `TC-MENU-04` - Parameterized Path Match

**Test Objects**

The `getMeunMatcheys` function

**Test Goals**

Verify that a parameterized path is correctly matched against the route pattern.

**Test Activities**

- Step 1: Call `getMeunMatcheys(meun, '/userinfo/2144')`.
- Step 2: Assert the return value as `['/userinfo/:id']`.

### `TC-MENU-05` - Nested Parameterized Match

**Test Objects**

The `getMeunMatcheys` function

**Test Goals**

Verify that a nested parameterized path is correctly matched against the route pattern.

**Test Activities**

- Step 1: Call `getMeunMatcheys(meun, '/userinfo/2144/info')`.
- Step 2: Assert the return value as `['/userinfo/:id/info']`.

---

## Group 2: TC-MENU-02

**Shared testing question:** Does the menu matching function correctly return an empty result when the input path does not match any defined route?

### `TC-MENU-02` - Non-Matching Path

**Test Objects**

The `getMeunMatcheys` function

**Test Goals**

Verify that a non-matching path returns an empty result.

**Test Activities**

- Step 1: Call `getMeunMatcheys(meun, '/dashboardname')`.
- Step 2: Assert the return value as `[]`.