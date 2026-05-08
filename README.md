# Enterprise API Automation Framework

![GitHub Actions Status](https://img.shields.io/github/actions/workflow/status/Arzoo-e-Urfa/api-automation-framework/api-tests.yml?branch=main&style=for-the-badge&logo=githubactions)
![Postman](https://img.shields.io/badge/Postman-FF6C37?style=for-the-badge&logo=postman&logoColor=white)
![Newman](https://img.shields.io/badge/Newman-000000?style=for-the-badge&logo=npm&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-43853D?style=for-the-badge&logo=node.js&logoColor=white)

A senior-level, scalable, and professional API testing framework built with **Postman**, **Newman**, and **GitHub Actions**. 

## 🏭 Production Context

This framework simulates real-world API validation workflows for modern SaaS applications. It is designed to mirror the complex architecture of an enterprise backend, testing critical system boundaries including:
*   **Authentication APIs:** Secure token generation and session management.
*   **CRUD Workflows:** Complete lifecycle validation of application resources (Create, Read, Update, Delete).
*   **Token Validation:** Strict enforcement of authorization headers across protected routes.
*   **Asynchronous Request Handling:** Validating state changes and response timing.
*   **Negative Testing:** Ensuring system resilience against malformed payloads and unauthorized access attempts.

## 🏆 Why This Project Matters

This project demonstrates a production-grade approach to API Quality Assurance, highlighting:
*   **Scalable API Automation:** Modular collections and reusable request patterns that can grow with the application.
*   **CI/CD Integration:** Fully automated execution pipelines using GitHub Actions, ensuring immediate feedback on code changes.
*   **Environment-Based Configuration:** Secure, multi-environment (`dev`, `test`) execution without hardcoded credentials.
*   **Production-Grade QA Workflows:** Strict adherence to contract testing and schema validation.
*   **AI-Assisted Test Design:** Leveraging modern LLMs to optimize test coverage and discover edge cases.

## 🤖 AI-Assisted QA

> **ChatGPT, Gemini, and Claude were utilized as pair-programming assistants to elevate this framework.**

These AI tools were specifically used to:
- Generate comprehensive edge cases and negative testing scenarios.
- Draft complex JSON Schema validation structures for strict contract testing.
- Optimize API validation strategies and refine JavaScript assertion logic within the Postman sandbox.

## 📈 Testing Strategy

Our methodology ensures complete confidence in the API layer through rigorous, multi-faceted validation:

### 1. Smoke Testing
Validating the critical "Happy Path" workflows (e.g., successful login, core resource creation) to ensure fundamental system health before deeper testing.

### 2. Regression Testing
Exhaustive validation of all endpoints across the CRUD lifecycle.
*   **Status Code Validation:** Strict checks for `200`, `201`, `204`, etc.
*   **Response Body Validation:** Asserting correct data reflection and variable extraction (e.g., storing a `bookingid` for subsequent requests).

### 3. Negative Testing
Proving the API's resilience and error-handling capabilities.
*   **Unauthorized Access:** Verifying `401` and `403` responses for missing or invalid tokens.
*   **Invalid Payloads:** Sending malformed data to ensure proper `400 Bad Request` handling.
*   **Resource Not Found:** Validating `404` responses for non-existent IDs.

### 4. Schema Validation
Enforcing strict API contracts by validating responses against predefined JSON Schemas to catch structural breaking changes immediately.

### 5. Response Validation
Monitoring API performance by asserting that response times fall within acceptable Service Level Agreement (SLA) thresholds (e.g., `< 3000ms`).

## 🔄 CI/CD Workflow

This repository features a fully automated Continuous Integration pipeline (`.github/workflows/api-tests.yml`) powered by GitHub Actions.

1.  **Trigger:** The workflow automatically executes on every `push` and `pull_request` to the `main` branch.
2.  **Environment:** It spins up a clean Ubuntu runner and provisions the latest Node.js environment.
3.  **Execution:** Installs Newman and securely runs the Postman collections against the test environment.
4.  **Reporting:** Generates a rich, interactive HTML report (`htmlextra`) and automatically uploads it as a downloadable CI artifact, providing deep visibility into test results.

## ⚙️ Setup Instructions

### Prerequisites
*   [Node.js](https://nodejs.org/) (v18+)
*   [npm](https://www.npmjs.com/)

### Installation
1.  **Clone the repository:**
    ```bash
    git clone https://github.com/Arzoo-e-Urfa/api-automation-framework.git
    cd api-automation-framework
    ```
2.  **Install dependencies:**
    ```bash
    npm install
    ```
3.  **Environment Setup:**
    Create a `.env` file from the provided example to securely manage local configurations (Optional for local CLI runs, required if overriding Postman environments via script):
    ```bash
    cp .env.example .env
    ```

## 🛠️ Execution Commands

The framework uses custom npm scripts to trigger Newman with different configurations and reporters.

**Run tests in the Dev environment (CLI + HTML Report):**
```bash
npm run test:dev
```

**Run tests in the Test environment (CLI + HTML Report):**
```bash
npm run test:test
```

**Run tests in Headless/CI mode (CLI + HTML Report to Artifacts):**
```bash
npm run test:ci
```

**View the HTML Report Locally:**
```bash
npm run report
```

---
**Disclaimer:** *This project is a QA automation portfolio piece designed to simulate enterprise API testing. It interacts with public dummy APIs (Restful Booker) and contains no proprietary company data or sensitive credentials.*