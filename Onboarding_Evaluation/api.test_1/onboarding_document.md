## Test Suite Overview

**Suite ID:** BOOKS-API-SUITE-01
**Test cases:** 8

This suite verifies the Create, Read, Update, and Delete (CRUD) operations of the Books API, ensuring that the system correctly processes requests for both existing and non-existent book resources by returning appropriate status codes and data payloads.

- **Books API CRUD Verification**
  - **Unique Dependencies:** `supertest`
  - **TC-BOOKS-01:** List All Books (dependencies: `supertest`)
  - **TC-BOOKS-02:** Get Existing Book (dependencies: `supertest`)
  - **TC-BOOKS-03:** Get Missing Book (dependencies: `supertest`)
  - **TC-BOOKS-04:** Create New Book (dependencies: `supertest`)
  - **TC-BOOKS-05:** Update Existing Book (dependencies: `supertest`)
  - **TC-BOOKS-06:** Update Missing Book (dependencies: `supertest`)
  - **TC-BOOKS-07:** Delete Existing Book (dependencies: `supertest`)
  - **TC-BOOKS-08:** Delete Missing Book (dependencies: `supertest`)

---

## Group 1: TC-BOOKS-01, TC-BOOKS-02, TC-BOOKS-04, TC-BOOKS-05, TC-BOOKS-07

**Shared testing question:** Does the API correctly handle requests for existing resources by returning success status codes and valid data?

### `TC-BOOKS-01` - List All Books

**Test Objects**

`GET /api/books` Interface

**Test Goals**

Verify that calling this interface returns the expected status code and the response body is an array.

**Test Activities**

- Step 1: Send a GET request to `/api/books`.
- Step 2: Check that the status code is 200.
- Step 3: Check that the response body is an array.

### `TC-BOOKS-02` - Get Existing Book

**Test Objects**

`GET /api/books/:id` Interface

**Test Goals**

Verify that requesting an existing resource returns a success status code with the correct data.

**Test Activities**

- Step 1: Send a GET request to `/api/books/1`.
- Step 2: Check that the status code is 200.
- Step 3: Check that the `id` field in the returned body is 1.

### `TC-BOOKS-04` - Create New Book

**Test Objects**

`POST /api/books` API

**Test Goals**

Verify that creating a new book with valid data returns a success response with the correct book information.

**Test Activities**

- Step 1: Construct new book data (title: "Dune", author: "Frank Herbert", genre: "Sci-Fi", copiesAvailable: 4).
- Step 2: Send a POST request to `/api/books`, carrying the above JSON data.
- Step 3: Check that the status code is 201.
- Step 4: Check that the `title` in the returned body is "Dune".

### `TC-BOOKS-05` - Update Existing Book

**Test Objects**

`PUT /api/books/:id` API

**Test Goals**

Verify that updating an existing book returns a success status code and the book data is updated.

**Test Activities**

- Step 1: Send a PUT request to `/api/books/1`, with the body containing `{ title: "Updated Title" }`.
- Step 2: Check that the status code is 200.
- Step 3: Check that the `title` in the returned body is "Updated Title".

### `TC-BOOKS-07` - Delete Existing Book

**Test Objects**

`DELETE /api/books/:id` Interface

**Test Goals**

Verify that deleting an existing book returns a success status code.

**Test Activities**

- Step 1: Send a DELETE request to `/api/books/1`.
- Step 2: Check that the status code is 200.

---

## Group 2: TC-BOOKS-03, TC-BOOKS-06, TC-BOOKS-08

**Shared testing question:** Does the API correctly handle requests for non-existent resources by returning appropriate error status codes?

### `TC-BOOKS-03` - Get Missing Book

**Test Objects**

`GET /api/books/:id` API

**Test Goals**

Verify that requesting a non-existent resource returns an error status code.

**Test Activities**

- Step 1: Send a GET request to `/api/books/999`.
- Step 2: Check that the status code is 404.

### `TC-BOOKS-06` - Update Missing Book

**Test Objects**

`PUT /api/books/:id` API

**Test Goals**

Verify that updating a non-existent book returns an error.

**Test Activities**

- Step 1: Send a PUT request to `/api/books/999`, with the body containing `{ title: "No Book" }`.
- Step 2: Check that the status code is 404.

### `TC-BOOKS-08` - Delete Missing Book

**Test Objects**

`DELETE /api/books/:id` Interface

**Test Goals**

Verify that deleting a non-existent book returns an error.

**Test Activities**

- Step 1: Send a DELETE request to `/api/books/999`.
- Step 2: Check that the status code is 404.