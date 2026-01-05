# Test Automation Exercises (Mini Projects)

This repository collects two test-automation mini projects with requirements and user stories. Use this as a training / practice repo for building Playwright-based frameworks, CI pipelines, and reporting.

---

## Mini Project 1: API-Only Testing with Playwright

API: https://restful-booker.herokuapp.com/apidoc/index.html

A public API for booking management with token-based and basic authentication. It supports full CRUD operations and resets data every 10 minutes, ensuring a consistent test environment.

### Requirements
- Build a Playwright test framework for API testing from scratch.
- Implement a layered architecture (test, service, utils, config).
- Use design patterns and principles (e.g., Dependency inversion principle, Builder, Factory for data).
- Integrate ESLint, Prettier, and Husky for code quality and pre-commit checks.
- Implement Allure reporting.
- Use GitHub for version control, GitHub Actions for CI, and GitHub Copilot for code suggestions.
- Create a CI pipeline that runs tests, lints code, and generates reports.

### User Stories
- As a tester, I want to authenticate using the /auth endpoint so that I can obtain a token for subsequent requests.
- As a tester, I want to create a new booking and verify the booking details via GET requests.
- As a tester, I want to update an existing booking and validate the changes.
- As a tester, I want to delete a booking and confirm it is no longer retrievable.
- As a tester, I want to verify that unauthorized requests are rejected with appropriate error codes.
- As a tester, I want to generate and view Allure reports for all test runs.
- As a tester, I want the pipeline to fail if linting or tests fail, and to upload the Allure report as an artifact.

---

## Mini Project 2: UI and Backend End-to-End Testing

Site: https://automationexercise.com/

Automation Exercise is a public e-commerce demo site with a full UI and backend API, designed for testing purposes.

### Requirements
- Build a Playwright test framework for end-to-end (UI + API) testing from scratch.
- Use a layered architecture (test, page objects, API services, utils, config).
- Apply design principles and patterns (Page Object Model, DRY, SOLID).
- Integrate ESLint, Prettier, and Husky.
- Implement Allure reporting.
- Use GitHub, GitHub Actions, and GitHub Copilot.
- Create a CI pipeline that runs UI and API tests, lints code, and generates reports.

### User Stories
- As a tester, I want to register a new user via the UI and verify the user is created via the backend API.
- As a tester, I want to log in as a user and add products to the cart, verifying cart contents via the API.
- As a tester, I want to complete a purchase and confirm the order appears in the user’s order history.
- As a tester, I want to test negative scenarios (e.g., invalid login, out-of-stock purchase) and verify error handling.
- As a tester, I want to generate and view Allure reports for all test runs.
- As a tester, I want the pipeline to fail if linting or tests fail, and to upload the Allure report as an artifact.

---

## Prerequisite Training

Recommended training:
- Master Test Automation with Playwright (LinkedIn Learning)  
  https://www.linkedin.com/learning/paths/master-test-automation-with-playwright?dApp=53239054&leis=LAA&u=2113185
