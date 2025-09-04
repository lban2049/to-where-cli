# Available Scripts

The `package.json` file includes a set of scripts to assist with the development workflow, from running the application locally to building, testing, and deploying it. You can execute these scripts from the root of the project using `npm run <script-name>`.

Below is a comprehensive list of all available scripts and their functions.

### Development & Workflow

| Script | Description |
|---|---|
| `reinstall` | Deletes the `node_modules` directory and reinstalls all dependencies for a clean setup. |
| `debug` | Runs the compiled application directly using Node.js. This script is intended for debugging the built output and is automatically preceded by a build step. |
| `build:watch` | Runs the build process in watch mode, automatically recompiling the code whenever a source file is changed. |

### Code Quality & Testing

| Script | Description |
|---|---|
| `lint` | Analyzes the TypeScript source code in the `src` directory for style and quality issues using ESLint. |
| `lint:fix` | Runs the linter and automatically corrects any fixable issues. |
| `test` | Executes the test suite using Jest. |
| `coverage` | Runs the test suite and generates a code coverage report. |
| `verify` | A quality check script that runs both the linter and the entire test suite. |

### Build & Deployment

| Script | Description |
|---|---|
| `clean` | Removes the `dist` directory, clearing all compiled files. |
| `build` | Compiles the TypeScript source code into JavaScript using esbuild and outputs it to the `dist` directory. It is automatically preceded by a `clean` step. |
| `deploy` | Performs a local deployment. It builds the project, uninstalls any existing global version, and then installs the current local version globally. This is useful for end-to-end testing of the CLI. |
| `deploy:remote` | Uninstalls the current global version and reinstalls the latest version from the official npm registry. |

### Versioning

| Script | Description |
|---|---|
| `bump-version` | Increments the package version number in `package.json` using the `ver-bump` utility. |
| `show:version` | Fetches and displays the latest version number of the `to-where-cli` package published on npm. |

---

After familiarizing yourself with these scripts, you might want to learn more about the project's layout by reading the [Project Structure](./development-project-structure.md) documentation.