# API Automation Framework

[![API Automation Tests](https://github.com/Arzoo-e-Urfa/api-automation-framework/actions/workflows/api-tests.yml/badge.svg)](https://github.com/Arzoo-e-Urfa/api-automation-framework/actions)

A clean, scalable, and professional API testing framework built with **Postman** and **Newman**. This repository serves as a portfolio project demonstrating modern QA automation practices, continuous integration (CI/CD), and robust API validation strategies.

## 🚀 Project Overview

This framework is designed to test RESTful APIs with an emphasis on reusability, environment separation, and comprehensive assertions. It uses the public [Reqres API](https://reqres.in/) as a dummy target to safely demonstrate production-grade testing techniques without exposing proprietary data.

### Tech Stack
*   **Testing Tool:** [Postman](https://www.postman.com/)
*   **CLI Runner:** [Newman](https://learning.postman.com/docs/running-collections/using-newman-cli/command-line-integration-with-newman/)
*   **Language:** JavaScript (ES6+ within Postman sandbox)
*   **CI/CD:** GitHub Actions
*   **Reporting:** `newman-reporter-htmlextra` and CLI
*   **Environment Management:** Configured via `dotenv` and Postman Environment files.

## 🤖 AI-Assisted Testing

> **AI tools like ChatGPT, Gemini, and Claude were utilized to optimize QA workflows.**

This framework showcases how AI can accelerate test development by helping to:
- Generate comprehensive negative scenarios and edge cases.
- Draft complex JSON Schema validation structures.
- Refine assertion logic and optimize reusable request patterns.

## 🎯 API Testing Strategy

The collection is modularized into distinct testing strategies to ensure high coverage and reliability:

### 1. Authentication Testing
- **Valid Login:** Verifies successful token generation and acceptable response times.
- **Invalid Credentials:** Validates proper error handling and 400 status codes.

### 2. CRUD Operations
- **POST (Create):** Validates 201 status, payload reflection, and strict JSON Schema compliance.
- **GET (Read):** Ensures data retrieval logic and response structure.
- **PUT (Update):** Verifies state changes and timestamp updates.
- **DELETE (Delete):** Confirms successful 204 no-content removal.

### 3. Negative Testing
- Proves system resilience by intentionally injecting invalid payloads.
- Validates 404 handling for non-existent resources.
- Verifies unauthorized access paths.

### 4. Advanced Assertions
- **Status Code Validation**
- **Response Body Extraction & Chaining** (e.g., passing a generated ID to subsequent requests)
- **JSON Schema Validation** for contract testing
- **Performance Thresholds** (Response Time Validation)

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
    Create a `.env` file from the provided example (optional for local CLI overriding):
    ```bash
    cp .env.example .env
    ```

## 🛠️ Execution Commands

The framework uses Newman to run tests across different configurations.

**Run tests in the Dev environment (with HTML report generation):**
```bash
npm run test:dev
```

**Run tests in the Test environment (with HTML report generation):**
```bash
npm run test:test
```

**Run tests in Headless/CI mode (CLI output only):**
```bash
npm run test:ci
```

**View the HTML Report:**
After running a suite with the HTML reporter, open the generated file:
```bash
npm run report
```

## 🔄 CI/CD Integration

This repository features a fully configured **GitHub Actions** workflow (`.github/workflows/api-tests.yml`). 
- It automatically triggers on every `push` and `pull_request` to the `main` branch.
- It sets up a fresh Node environment, installs Newman, and executes the Postman collections.
- It generates and uploads the testing artifacts, ensuring a continuous testing loop that proves CI/CD readiness.

---
**Disclaimer:** *This project is designed as a QA automation portfolio piece. It uses public dummy APIs to simulate real-world testing scenarios and contains no proprietary company data.*
