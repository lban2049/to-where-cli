# Available Scripts

The `package.json` file includes a set of npm scripts to assist with the development workflow, from building and testing to deploying the application. These scripts can be executed from the root of the project using the `npm run <script-name>` command.

Below is a comprehensive list of the available scripts and their functions.

## Core Development Scripts

These scripts are central to the daily development and testing cycle.

| Script | Description |
|---|---|
| `build` | Compiles the TypeScript source code from the `src` folder into JavaScript, outputting the result to the `dist` directory. It uses `esbuild` for fast builds. |
| `build:watch` | Runs the build process in watch mode. It automatically recompiles the code whenever a source file is changed, which is useful during active development. |
| `debug` | Executes the compiled application directly using Node. This is helpful for testing the CLI's behavior after a build. It automatically runs the `build` script first. |
| `deploy` | Performs a local global installation. This script builds the project, uninstalls any globally installed version of `to-where-cli`, and then installs the current local version globally. This is ideal for testing the end-to-end installation and execution flow on your machine. |

## Code Quality and Testing

These scripts help maintain code quality and ensure the application is working as expected.

| Script | Description |
|---|---|
| `lint` | Lints all TypeScript files in the `src` directory using ESLint to check for code quality and style issues. |
| `lint:fix` | Runs the linter and automatically fixes any rules that are autofixable. |
| `test` | Executes the entire test suite using Jest. |
| `coverage` | Runs the test suite and generates a code coverage report to identify untested parts of the codebase. |
| `verify` | A utility script that runs both `lint` and `test` to ensure code quality and correctness before committing changes. |

## Housekeeping and Versioning

These scripts handle project maintenance, dependencies, and version management.

| Script | Description |
|---|---|
| `clean` | Deletes the `dist` directory, removing all previously compiled files. This is automatically run before each `build`. |
| `reinstall` | Deletes the `node_modules` directory and reinstalls all project dependencies using `pnpm`. Useful for resolving dependency conflicts or starting with a clean slate. |
| `deploy:remote` | Uninstalls the existing global `to-where-cli` package and reinstalls the latest version from the official npm registry. |
| `bump-version` | Bumps the package version in `package.json` automatically. |
| `show:version` | Queries the npm registry and displays the latest published version number for `to-where-cli`. |

---

With an understanding of the development scripts, you can explore the project's evolution in the [Changelog](./changelog.md).