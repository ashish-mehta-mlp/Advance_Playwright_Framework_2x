# Advance Playwright Framework

A Playwright-based test automation framework built with the Page Object Model (POM) pattern for scalable UI test coverage.

## Overview

This project is designed for end-to-end browser testing using Playwright with a structured test architecture that separates:

- test specifications
- page objects
- reusable utility modules
- environment configuration
- reporting and logging

## Tech Stack

- Playwright
- TypeScript
- Node.js
- Page Object Model
- Winston logger
- Allure/HTML reporting support

## Project Structure

```text
AdvancePlaywrightFramework/
├── src/
│   ├── pages/
│   │   ├── BasePage.ts
│   │   ├── LoginPage.ts
│   │   ├── InventoryPage.ts
│   │   ├── CartPage.ts
│   │   ├── CheckoutStepOnePage.ts
│   │   ├── CheckoutStepTwoPage.ts
│   │   ├── CheckoutCompletePage.ts
│   │   └── ItemDetailsPage.ts
│   ├── tests/
│   │   ├── example.spec.ts
│   │   └── login.spec.ts
│   ├── utils/
│   │   ├── CustomReporter.ts
│   │   ├── DataGenerator.ts
│   │   ├── logger.ts
│   │   └── UtilElementLocator.ts
│   └── config/
├── playwright.config.ts
├── package.json
├── .gitignore
├── README.md
├── logs/
├── reports/
├── playwright-report/
└── test-results/
```

## Prerequisites

Before running the tests, ensure you have:

- Node.js installed
- npm installed
- Playwright browsers installed

## Installation

```bash
npm install
npx playwright install
```

## Run Tests

Run all tests:

```bash
npx playwright test
```

Run a specific spec file:

```bash
npx playwright test src/tests/login.spec.ts
```

Open the Playwright HTML report:

```bash
npx playwright show-report
```

## Configuration

The framework uses `playwright.config.ts` for configuration such as:

- base URL resolution
- test directory
- timeout settings
- browser project setup
- reporter configuration
- screenshot/video/trace capture behavior

## Reporting

Test results can be generated in the default Playwright HTML report and custom reporting folders such as:

- `playwright-report/`
- `playwright_reports/`
- `reports/`

## Notes

This project is intended as a reusable automation foundation for UI testing workflows and can be extended with additional features like:

- environment-specific configs
- CI/CD integration
- API testing modules
- custom assertions and helpers
- data-driven test scenarios

## License

This project is for learning and test automation purposes.
