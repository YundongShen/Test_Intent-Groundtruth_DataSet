## Test Suite Overview

**Suite ID:** BOOTSTRAP4-SUITE-01
**Test cases:** 6

This suite verifies Bootstrap 4 page content visibility, alert styling, and modal dialog behavior by checking initial body states, CSS application timing, and modal interaction logic.

- **Bootstrap 4 Verification Suite**
  - **Unique Dependencies:** `@playwright/test`
  - **TC-BOOTSTRAP4-01:** Initial Body Hidden (dependencies: `@playwright/test`)
  - **TC-BOOTSTRAP4-02:** Body Becomes Visible (dependencies: `@playwright/test`)
  - **TC-BOOTSTRAP4-03:** Alert Style Applied (dependencies: `@playwright/test`)
  - **TC-BOOTSTRAP4-04:** Modal Count Hidden (dependencies: `@playwright/test`)
  - **TC-BOOTSTRAP4-05:** Modal Button Exists (dependencies: `@playwright/test`)
  - **TC-BOOTSTRAP4-06:** Modal Opens On Click (dependencies: `@playwright/test`)

---

## Group 1: TC-BOOTSTRAP4-01, TC-BOOTSTRAP4-02

**Shared testing question:** Does the page correctly manage the initial visibility state of the body element?

### `TC-BOOTSTRAP4-01` - Initial Body Hidden

**Test Objects**

The page's `body` element

**Test Goals**

Confirm that the `body` element is hidden during initial page load.

**Test Activities**

- Step 1: Visit the homepage `/`.
- Step 2: Check that the `body` element is hidden.

### `TC-BOOTSTRAP4-02` - Body Becomes Visible

**Test Objects**

The page's `body` element

**Test Goals**

Confirm that the `body` element becomes visible after the page loads.

**Test Activities**

- Step 1: Visit the homepage `/`.
- Step 2: Check that the `body` element eventually becomes visible.

---

## Group 2: TC-BOOTSTRAP4-03

**Shared testing question:** Are Bootstrap styles correctly applied to page elements after loading?

### `TC-BOOTSTRAP4-03` - Alert Style Applied

**Test Objects**

The style of the `.alert-primary` element

**Test Goals**

Verify that the alert style is applied after Bootstrap CSS loads.

**Test Activities**

- Step 1: Visit the homepage `/`.
- Step 2: Get the initial background color of the first `.alert-primary` element.
- Step 3: Wait for the Bootstrap CSS request to complete.
- Step 4: Get the background color of the same element again.
- Step 5: Assert that the two colors are different.

---

## Group 3: TC-BOOTSTRAP4-04

**Shared testing question:** Is the modal component correctly initialized with the expected count and hidden state?

### `TC-BOOTSTRAP4-04` - Modal Count Hidden

**Test Objects**

Modal element `[role="dialog"]`

**Test Goals**

Confirm that there is only one modal on the page, and its initial state is hidden.

**Test Activities**

- Step 1: Visit the homepage `/`.
- Step 2: Locate the `[role="dialog"]` element.
- Step 3: Assert that its quantity is 1.
- Step 4: Get the `aria-hidden` attribute of this element.
- Step 5: Assert that the attribute value is `"true"`.

---

## Group 4: TC-BOOTSTRAP4-05

**Shared testing question:** Does the UI provide the necessary trigger element to interact with the modal?

### `TC-BOOTSTRAP4-05` - Modal Button Exists

**Test Objects**

"Launch demo modal" button

**Test Goals**

Confirm that a button for opening a modal exists on the page.

**Test Activities**

- Step 1: Visit the homepage `/`.
- Step 2: Find the button element with the text `"Launch demo modal"`.
- Step 3: Assert that the element is defined (exists).

---

## Group 5: TC-BOOTSTRAP4-06

**Shared testing question:** Does the modal component respond correctly to user interaction by changing its visibility state?

### `TC-BOOTSTRAP4-06` - Modal Opens On Click

**Test Objects**

Modal `[role="dialog"]` and its launch button

**Test Goals**

Verify that the modal opens after clicking the button.

**Test Activities**

- Step 1: Access the homepage `/`.
- Step 2: Locate the modal and obtain its `aria-hidden` attribute.
- Step 3: Find the `"Launch demo modal"` button and click it.
- Step 4: Check if the modal's `aria-hidden` attribute value is `"false"`.