# Advanced Playwright Framework

A TypeScript test automation framework built with Playwright. It combines reusable Page Object Model (POM) components with UI end-to-end tests, API coverage, shared fixtures, and test-data utilities.

## Features

- Browser-based login, inventory, cart, and checkout scenarios using page objects.
- API tests for RESTful Booker, including CRUD flows and negative cases.
- Reusable Playwright fixtures for page objects and common application states.
- JSON Schema validation with AJV and JSONPath query examples.
- Test-data generation, structured logging, and custom reporting utilities.
- Environment-aware base URL configuration and optional environment-based credentials.

## Tech Stack

- Node.js, TypeScript, and Playwright Test
- Faker for test data generation
- AJV and JSONPath Plus for API data validation and querying
- Winston for logging
- Allure Playwright integration

## Project Structure

```text
src/
├── api/          API clients and request helpers
├── config/       Environment and credential configuration
├── fixtures/     Shared Playwright fixtures
├── pages/        UI page objects for login and checkout flows
├── testdata/     Login data, booking data, and JSON schemas
├── tests/
│   ├── End2End/  Browser-based end-to-end tests
│   ├── Login/    Login scenarios
│   ├── aiTest/   AI-assisted test-data generation examples
│   └── apisTests/ API, schema, and JSONPath tests
└── utils/        Reporting, logging, API, and validation helpers

playwright.config.ts
package.json
```

## Prerequisites

- Node.js (an active LTS release recommended)
- npm
- A supported Playwright browser

## Installation

Install dependencies and the Chromium browser:

```bash
npm install
npx playwright install chromium
```

## Running Tests

Run the full suite:

```bash
npx playwright test
```

Run tests in a visible browser or open Playwright UI mode:

```bash
npx playwright test --headed
npx playwright test --ui
```

Run a specific test file (adjust the path to the scenario you want):

```bash
npx playwright test src/tests/Login/Login.spec.ts
```

View the HTML report after a run:

```bash
npx playwright show-report
```

## Configuration

The Playwright configuration resolves the base URL in this order:

1. `BASE_URL`, if set directly.
2. The URL for `TTA_ENV`, using the corresponding environment URL variable.
3. The default QA URL.

Supported `TTA_ENV` values are `qa` (default), `dev`, `local`, `stg`, `stage`, `staging`, `prod`, `production`, and `api`. Configure `QA_BASE_URL`, `DEV_BASE_URL`, `STG_BASE_URL`, `PROD_BASE_URL`, or `API_BASE_URL` as needed. The API environment defaults to the RESTful Booker demo service.

Credentials can be supplied through `STANDARD_USER` and `TTA_SECRET`. Keep credentials and other secrets in local environment configuration or a CI secret store; never commit them to the repository.

For example, in PowerShell:

```powershell
$env:TTA_ENV = "stg"
$env:STG_BASE_URL = "https://your-staging-url"
npx playwright test
```

## Reports and Artifacts

Playwright's HTML report is generated in `playwright-report/`. Test runs may also produce traces, screenshots, videos, logs, and custom reports according to the project configuration. Generated results should not be committed unless specifically required.

## License

This project is intended for learning and test automation purposes.
