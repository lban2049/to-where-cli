# Available Scripts

The `package.json` file includes a set of scripts to streamline common development tasks. These scripts, executed with `npm run <script_name>`, handle everything from building the project and running tests to deploying the application. Below is a detailed reference for each available script.

## Core Development Scripts

These scripts are central to the daily development workflow.

| Script | Description |
|---|---|
| `npm run reinstall` | Deletes the `node_modules` directory and reinstalls all project dependencies using `pnpm`. Useful for resolving dependency issues. |
| `npm run clean` | Removes the `dist` directory, cleaning out all compiled files from the previous build. |
| `npm run build` | Compiles the TypeScript source code from the `src` directory into JavaScript in the `dist` directory using `esbuild`. It automatically runs the `clean` script first. |
| `npm run build:watch` | Starts the build process in watch mode. It will automatically recompile the project whenever a source file is changed. |
| `npm run debug` | Builds the project and then executes the main entry point (`dist/index.js`) with Node.js, allowing you to test the CLI's behavior directly. |

## Code Quality and Testing

These scripts help maintain code quality and ensure the application is working as expected.

| Script | Description |
|---|---|
| `npm run lint` | Lints all TypeScript files within the `src` directory using ESLint to check for code style and potential errors. |
| `npm run lint:fix` | Lints the codebase and automatically fixes any issues that are safe to correct. |
| `npm run test` | Executes the entire test suite using Jest. |
| `npm run coverage` | Runs the test suite and generates a code coverage report, showing how much of the code is covered by tests. |
| `npm run verify` | A convenience script that runs both `lint` and `test`. This is useful to run before committing changes to ensure code quality and functionality. |

## Deployment and Versioning

These scripts are used for deploying the application and managing its version number.

| Script | Description |
|---|---|
| `npm run deploy` | Performs a local global deployment. It builds the project, uninstalls any existing global `to-where-cli` package, and then installs the current local project globally. This is ideal for testing the final build as a user would. |
| `npm run deploy:remote` | Uninstalls the current global version and reinstalls the latest version published on the npm registry. This is useful for switching back to the official release. |
| `npm run bump-version` | Increments the version number in `package.json` using the `ver-bump` utility. |
| `npm run show:version` | Queries the npm registry to display the latest published version of `to-where-cli`. |

---

With an understanding of these development scripts, you can build, test, and contribute to the project. To see a history of changes and new features, you can proceed to the [Changelog](./changelog.md).