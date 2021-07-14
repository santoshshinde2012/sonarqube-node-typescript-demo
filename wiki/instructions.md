### 1. Why is my git pre-commit hook not executable by default?

- Because files are not executable by default; they must be set to be executable.

```
chmod ug+x .husky/*
chmod ug+x .git/hooks/*
```

### 2. [Production Best Practices: Security](https://expressjs.com/en/advanced/best-practice-security.html)

- Don’t use deprecated or vulnerable versions of Express
- Use TLS
- Use Helmet
- Use cookies securely
- Prevent brute-force attacks against authorization
- Ensure your dependencies are secure
- Avoid other known vulnerabilities
- Additional considerations

### 3. How to fix `“parserOptions.project” has been set for @typescript-eslint/parser` ?

- Simply instruct `eslint` to ignore them by adding the `ignorePatterns` option to your `.eslintrc`: `"ignorePatterns": ["sonar.js"]`

```
{
  "parser": "@typescript-eslint/parser",
  "extends": [
    "airbnb/base",
    "plugin:@typescript-eslint/recommended",
    "plugin:import/errors",
    "plugin:import/warnings",
    "plugin:import/typescript",
    "prettier"
  ],
  "parserOptions": {
    "ecmaVersion": 2018,
    "project": "./tsconfig.json"
  },
  "ignorePatterns": ["sonar.js"], // This line should be add in configuration
  "plugins": ["prettier"],
  "rules": {}
}
```