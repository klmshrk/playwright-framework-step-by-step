# Playwright Test Automation Framework

This framework follows the Page Object Model pattern and includes support for data-driven testing, API testing, and different test suites (smoke, sanity, regression).

## Project Structure

```
├── env/                   # Environment configuration
├── fixtures/             
│   ├── api/              # API testing fixtures and utilities
│   │   ├── api-request-fixtures.ts
│   │   ├── plain-function.ts
│   │   ├── schemas.ts
│   │   └── types-guards.ts
│   └── pom/              # Page Object Model fixtures
│       ├── page-object-fixture.ts
│       └── test-options.ts
├── pages/                # Page Object Models
│   └── clientSite/
│       ├── articlePage.ts
│       ├── homePage.ts
│       └── navPage.ts
├── test-data/           # Test data files
│   ├── articleData.json
│   └── invalidLoginData.json
├── tests/               # Test suites
│   ├── api/            # API tests
│   │   ├── article.spec.ts
│   │   └── authentication.spec.ts
│   ├── clientSite/     # UI tests
│   │   ├── article.spec.ts
│   │   └── failingTest.spec.ts
│   └── auth.setup.ts   # Authentication setup
└── playwright.config.ts # Playwright configuration
```

## Features

- **Page Object Model (POM)**: Implements the POM design pattern for maintainable and reusable UI test code
- **API Testing**: Dedicated API testing suite with fixtures and type validation
- **Data-Driven Testing**: External test data management using JSON files
- **Multiple Test Suites**:
  - Smoke Tests (`@Smoke`)
  - Sanity Tests (`@Sanity`)
  - Regression Tests (`@Regression`)
  - API Tests (`@Api`)
- **Type Safety**: Written in TypeScript with proper type definitions
- **Schema Validation**: Uses Zod for API response validation
- **Fixtures**: Custom fixtures for both UI and API testing
- **Environment Management**: Support for different environment configurations

## Prerequisites

- Node.js (Latest LTS version recommended)
- npm or yarn

## Installation

```bash
# Clone the repository
git clone https://github.com/klmshrk/playwright-framework-step-by-step.git

# Install dependencies
npm install
```

## Available Scripts

- `npm test` - Run tests in Chromium
- `npm run ci` - Run tests in CI mode (1 worker)
- `npm run flaky` - Run tests 20 times to detect flaky tests
- `npm run debug` - Run tests in debug mode
- `npm run ui` - Run tests with Playwright UI mode
- `npm run smoke` - Run smoke tests
- `npm run sanity` - Run sanity tests
- `npm run api` - Run API tests
- `npm run regression` - Run regression tests
- `npm run fullTest` - Run all tests in all configured browsers

## Tech Stack

- [Playwright](https://playwright.dev/) - Core testing framework
- [TypeScript](https://www.typescriptlang.org/) - Programming language
- [Zod](https://zod.dev/) - Schema validation
- [Faker.js](https://fakerjs.dev/) - Test data generation
- [dotenv](https://www.npmjs.com/package/dotenv) - Environment management

## Best Practices

1. **Page Object Pattern**: UI elements and their interactions are encapsulated in page objects
2. **Data-Driven Testing**: Test data is separated from test logic
3. **API Testing**: Dedicated fixtures and type validation for API testing
4. **Test Organization**: Tests are organized by type (API/UI) and functionality
5. **Environment Configuration**: Separate environment configurations for different environments
