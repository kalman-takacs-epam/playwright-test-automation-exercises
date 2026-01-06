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

Please indicate your chosen approach at the beginning of your work and document your experience accordingly.

---

## Mini Project 1: API-Native Automation (Restful-Booker)

**Target:** [Restful-Booker API](https://restful-booker.herokuapp.com/apidoc/index.html)  
A public API for booking management with token-based and basic authentication, supporting full CRUD operations.

### AI-Augmented Requirements
- **MCP Exploration:** Use Playwright MCP to analyze API documentation and auto-generate TypeScript interfaces/types.
- **Layered Architecture:** Implement a Service layer abstracting API calls. Use Copilot to refactor repetitive code into a Builder Pattern for request payloads.
- **Dependency Inversion:** Use AI to design a ServiceFactory for swapping real and mock services.
- **Data Generation:** Integrate faker.js via a Factory Pattern for dynamic booking data.
- **Quality Gates:** Integrate ESLint, Prettier, and Husky. Use Copilot to resolve linting conflicts.

### User Stories
- As a tester, I want to use Copilot to generate a secure AuthService that manages token state globally via Playwright storageState.
- As a tester, I want to use MCP-guided prompts to generate a sequence of tests: Create → Verify (GET) → Update (PUT/PATCH) → Delete.
- As a tester, I want to use AI to brainstorm and generate edge-case scenarios (invalid tokens, malformed JSON) and verify 4xx/5xx responses.
- As a tester, I want Allure reports integrated into the CI/CD pipeline with GitHub Actions.
- As a tester, I want the pipeline to fail if linting or tests fail, and to upload the Allure report as an artifact.

---

## Mini Project 2: E2E Hybrid Automation (Automation Exercise)

**Target:** [Automation Exercise](https://automationexercise.com/)  
A public e-commerce demo site with a full UI and backend API.

### AI-Augmented Requirements
- **Agentic POM Generation:** Use Playwright MCP to inspect the website and have Copilot generate Page Object Models (POM) with optimized locators.
- **UI-API Synchronization:** Implement hybrid testing—use the API to set up test state (e.g., creating a user) and the UI to perform actions (e.g., shopping).
- **Self-Healing Implementation:** Configure Playwright Healer Agent to identify and suggest fixes for broken selectors during UI updates.
- **Architecture:** Adhere to DRY and SOLID principles. Use Copilot Chat for "Refactor Sessions" on Page Objects.

### User Stories
- As a tester, I want to register a user via UI and immediately verify their existence in the backend via the API service.
- As a tester, I want to add items to a cart via the API and verify they appear correctly in the UI cart, ensuring data consistency.
- As a tester, I want to complete a purchase and use an AI-generated script to verify the order history matches the UI confirmation.
- As a tester, I want to test negative scenarios (e.g., invalid login, out-of-stock purchase) and verify error handling.
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
- [ ] No Hardcoded Data: All test data is generated via an AI-guided Data Factory.
- [ ] Strict Layering: No direct page or request calls inside `.spec` files (must go through Service/Page layers).
- [ ] Custom Fixtures: Playwright fixtures are used to inject Services/Pages into tests.

### 2. AI Tooling Integration
- [ ] Prompt Documentation: A `PROMPTS.md` file exists, logging how Copilot/MCP were used to solve complex architectural hurdles.
- [ ] MCP Usage: Evidence of using Playwright MCP for site exploration and locator generation.
- [ ] Automated Healing: At least one instance of using AI to fix a test failure is demonstrated.

### 3. CI/CD & Reporting
- [ ] Pre-commit Hooks: Husky blocks commits that fail ESLint or Prettier.
- [ ] Pipeline: GitHub Actions runs tests in parallel (sharding enabled) and uploads Allure Reports as artifacts.
- [ ] Traceability: Failed tests in CI generate a Playwright Trace for review.
- [ ] (Optional) Allure Report is published to GitHub Pages automatically from the pipeline.
