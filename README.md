# AI-Native Playwright Test Automation Mini Projects

This repository contains two professional-grade test automation mini projects. The goal is to build robust Playwright-based frameworks, leveraging AI tools (GitHub Copilot, Playwright MCP) for code generation, exploration, and self-healing, while following strict software engineering principles.

**Planned Duration:** 2 weeks

---

## Recommended Trainings

If you are new to Playwright, GitHub Copilot, or GitHub Actions, the following trainings are recommended (but not required):

- [Master Test Automation with Playwright (LinkedIn Learning)](https://www.linkedin.com/learning/paths/master-test-automation-with-playwright?dApp=53239054&leis=LAA&u=2113185)
- [GitHub Actions Cert Prep by Microsoft Press](https://www.linkedin.com/learning/github-actions-cert-prep-by-microsoft-press?u=2113185)
- [GitHub Copilot for Software Developers by Microsoft Press](https://www.linkedin.com/learning/github-copilot-for-software-developers-by-microsoft-press?u=2113185)

**Nice to have:**  
- [Playwright MCP Videos](https://playwright.dev/community/mcp-videos)  
- [Playwright Learn Videos](https://playwright.dev/community/learn-videos)

---

## AI Usage Approach

Before starting, please choose your preferred approach for using AI during the projects:

- **Full AI-First Approach:**  
  Use AI tools (GitHub Copilot, Playwright MCP, etc.) as your primary assistants for exploration, code generation, refactoring, and troubleshooting throughout the entire development process.

- **AI as Support:**  
  Use AI tools mainly as a helper when you are stuck, need inspiration, or want to speed up the implementation of specific features, but rely primarily on your own knowledge and manual coding.

**Documentation Requirement:**  
For each major feature or task, briefly document whether you used AI, manual coding, or a combination, and why you chose that approach. This can be done in a `PROMPTS.md` or as comments in your code.

---

## Mini Project 1: API-Native Automation (Restful-Booker)

**Target:** [Restful-Booker API](https://restful-booker.herokuapp.com/apidoc/index.html)  
A public API for booking management with token-based and basic authentication, supporting full CRUD operations.

### Requirements
- Use Playwright MCP and/or manual exploration to analyze API documentation and generate TypeScript interfaces/types.
- Implement a Service layer abstracting API calls, using Copilot or manual refactoring as preferred.
- Apply design patterns and principles (e.g., Dependency Inversion, Builder, Factory for data), with or without AI assistance.
- Integrate faker.js for dynamic booking data, either with AI assistance or by hand.
- Integrate ESLint, Prettier, and Husky for code quality and pre-commit checks, resolving issues with or without Copilot.
- Implement Allure reporting.
- Use GitHub for version control, GitHub Actions for CI, and optionally Copilot for code suggestions.
- Create a CI pipeline that runs tests, lints code, and generates reports.

### User Stories
- As a tester, I want to implement authentication (using either AI-generated code or my own solution) and document my approach.
- As a tester, I want to create, update, and delete bookings, experimenting with both AI-assisted and manual test generation.
- As a tester, I want to handle negative scenarios (e.g., invalid tokens, malformed JSON), optionally brainstorming edge cases with AI, and compare with my own ideas.
- As a tester, I want to generate and view Allure reports for all test runs.
- As a tester, I want the pipeline to fail if linting or tests fail, and to upload the Allure report as an artifact.

---

## Mini Project 2: E2E Hybrid Automation (Automation Exercise)

**Target:** [Automation Exercise](https://automationexercise.com/)  
A public e-commerce demo site with a full UI and backend API.

### Requirements
- Use Playwright MCP and/or manual inspection to generate Page Object Models (POM) with optimized locators.
- Implement hybrid testing—use the API to set up test state (e.g., creating a user) and the UI to perform actions (e.g., shopping), with or without AI support.
- Configure Playwright Healer Agent and/or manual strategies to identify and fix broken selectors during UI updates.
- Apply DRY and SOLID principles, using Copilot Chat for refactoring sessions or manual refactoring as preferred.
- Integrate ESLint, Prettier, and Husky.
- Implement Allure reporting.
- Use GitHub, GitHub Actions, and optionally Copilot.

### User Stories
- As a tester, I want to register a user via UI and verify their existence in the backend via the API service, using either AI or manual implementation.
- As a tester, I want to add items to a cart via the API and verify they appear correctly in the UI cart, ensuring data consistency, and document my approach.
- As a tester, I want to complete a purchase and verify the order history matches the UI confirmation, optionally comparing AI-generated and hand-written scripts.
- As a tester, I want to test negative scenarios (e.g., invalid login, out-of-stock purchase) and verify error handling, using AI for brainstorming or my own ideas.
- As a tester, I want the GitHub Actions pipeline to fail on linting/test errors and provide a Playwright Trace Viewer link for visual debugging.

---

## Shared Technical Standards

| Component         | Technology / Pattern                                      |
|-------------------|----------------------------------------------------------|
| Language          | TypeScript (Strict Mode)                                 |
| Testing Engine    | Playwright (using Fixtures and Locators)                 |
| AI Tools          | GitHub Copilot + Playwright MCP (Planner/Healer)         |
| Patterns          | POM, Factory, Builder, Dependency Inversion              |
| Infrastructure    | GitHub Actions, Husky, Allure Reports                    |

---

## Definition of Done (DoD)

### 1. Architectural Excellence
- [ ] No Hardcoded Data: All test data is generated via an AI-guided Data Factory or manually implemented factory.
- [ ] Strict Layering: No direct page or request calls inside `.spec` files (must go through Service/Page layers).
- [ ] Custom Fixtures: Playwright fixtures are used to inject Services/Pages into tests.

### 2. AI Tooling Integration
- [ ] Prompt Documentation: A `PROMPTS.md` file exists, logging how Copilot/MCP or manual approaches were used to solve complex architectural hurdles.
- [ ] MCP Usage: Evidence of using Playwright MCP for site exploration and locator generation, or documentation of manual alternatives.
- [ ] Automated Healing: At least one instance of using AI or manual strategies to fix a test failure is demonstrated.

### 3. CI/CD & Reporting
- [ ] Pre-commit Hooks: Husky blocks commits that fail ESLint or Prettier.
- [ ] Pull request: A pull request is created for the whole framework.
- [ ] Pipeline: GitHub Actions runs tests in parallel (sharding enabled) and uploads Allure Reports as artifacts.
- [ ] Traceability: Failed tests in CI generate a Playwright Trace for review.
- [ ] (Optional) Allure Report is published to GitHub Pages automatically from the pipeline.

---

**Remember:**  
For each major feature, document your chosen approach (AI, manual, or both) and your reasoning. This reflection is a key part of the learning process!
