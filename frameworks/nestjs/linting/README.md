# GoApptiv Project Configuration

This readme provides comprehensive information about the standard ESLint and Prettier configurations for GoApptiv projects. These configurations are intended to be used across all GoApptiv projects to ensure a unified and high-quality codebase.

## ESLint Configuration

### `.eslintrc.js`

```javascript
// ESLint configuration for GoApptiv projects
module.exports = {
  parser: "@typescript-eslint/parser",
  parserOptions: {
    project: "tsconfig.json",
    tsconfigRootDir: __dirname,
    sourceType: "module",
  },
  plugins: ["@typescript-eslint/eslint-plugin", "prettier"],
  extends: ["plugin:@typescript-eslint/recommended", "prettier"],
  root: true,
  env: {
    node: true,
    jest: true,
  },
  ignorePatterns: [".eslintrc.js"],
  rules: {
    "@typescript-eslint/interface-name-prefix": "off",
    "@typescript-eslint/explicit-function-return-type": "error",
    "@typescript-eslint/explicit-module-boundary-types": "off",
    "@typescript-eslint/no-explicit-any": "off",
    "@typescript-eslint/no-floating-promises": "error",
    "@typescript-eslint/await-thenable": "warn",
    "@typescript-eslint/no-misused-promises": "error",
    camelcase: ["warn", { properties: "always" }],
    "capitalized-comments": ["error", "always"],
    "default-case": "error",
    "default-case-last": "error",
    "no-console": ["error", { allow: ["warn", "error", "info"] }],
    "no-lonely-if": "warn",
    "no-var": "warn",
    "prefer-const": [
      "error",
      {
        destructuring: "any",
        ignoreReadBeforeAssign: false,
      },
    ],
    "require-await": "error",
  },
};
```

This ESLint configuration is tailored for GoApptiv projects, using the `@typescript-eslint/parser` for TypeScript files and extending recommended TypeScript and Prettier configurations. It enforces various rules for code quality, readability, and maintainability.

## Prettier Configuration

### `.prettierrc`

```json
// Prettier configuration for GoApptiv projects
{
  "arrowParens": "always",
  "bracketSameLine": false,
  "bracketSpacing": true,
  "semi": true,
  "experimentalTernaries": false,
  "singleQuote": true,
  "jsxSingleQuote": true,
  "quoteProps": "as-needed",
  "trailingComma": "all",
  "singleAttributePerLine": false,
  "htmlWhitespaceSensitivity": "css",
  "vueIndentScriptAndStyle": false,
  "proseWrap": "preserve",
  "insertPragma": false,
  "printWidth": 80,
  "requirePragma": false,
  "useTabs": false,
  "embeddedLanguageFormatting": "auto",
  "tabWidth": 2
}
```

This Prettier configuration sets the code formatting rules for GoApptiv projects, covering settings for arrow functions, brackets, semicolons, quotes, trailing commas, and more.

## Linting

To fix linting issues in the project, run the following one-time command:

```bash
npx eslint --fix .
```

This command uses ESLint to automatically fix linting errors and enforce the configured rules throughout the project.

## GitHub Actions Workflow

### `.github/workflows/eslint-check.yml`

```yaml
name: ESLint Check

on:
  pull_request:
    branches:
      - main
      - master

jobs:
  eslint:
    name: Run ESLint
    runs-on: ubuntu-latest
    steps:
      - name: Checkout code
        uses: actions/checkout@v4

      - name: Set up Node.js
        uses: actions/setup-node@v4
        with:
          node-version: "16"

      - name: Install dependencies
        run: npm install

      - name: Run ESLint
        run: npx eslint .
```

This GitHub Actions workflow is designed to run ESLint on pull requests targeting the `main` or `master` branches of GoApptiv projects. It ensures that the code adheres to the ESLint configuration defined in the project.

Feel free to customize these configurations based on your project's specific needs. Maintain consistency across projects for a smooth and unified development experience.

Happy coding!
