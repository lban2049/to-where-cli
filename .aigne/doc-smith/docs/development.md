# Development Guide

This guide provides all the necessary information for developers looking to contribute to the `to-where-cli` project. It covers setting up the development environment, understanding the project's architecture, and utilizing the available scripts for building, testing, and deploying the tool.

The project is written in TypeScript and utilizes modern tools like esbuild for bundling, Jest for testing, and ESLint for code quality. We welcome contributions and hope this guide makes the process straightforward.

### Getting Started

To begin, clone the repository from GitHub and install the required dependencies. We recommend using `pnpm` for package management.

```bash
git clone https://github.com/skypesky/to-where-cli.git
cd to-where-cli
npm run reinstall # Installs dependencies using pnpm
```

### Core Sections

This guide is divided into two main sections to help you navigate the development process. Explore these sections to understand the codebase and the development workflow.

<x-cards data-columns="2">
  <x-card data-title="Project Structure" data-icon="lucide:folder-tree" data-href="/development/project-structure">
    An overview of the project's source code layout, explaining the purpose of key directories and files like `src`, `dist`, and various configuration files.
  </x-card>
  <x-card data-title="Available Scripts" data-icon="lucide:terminal" data-href="/development/scripts">
    A reference for the npm scripts defined in `package.json`, explaining how to build, test, lint, and deploy the application.
  </x-card>
</x-cards>

### Testing

The project uses Jest for testing. The configuration can be found in `jest.config.js`. All tests are located in the `<rootDir>/tests` directory and match the pattern `**/*.spec.ts`. You can run the test suite and generate coverage reports using the following commands:

```bash
# Run all tests
npm run test

# Generate a coverage report
npm run coverage
```

### Versioning

Version bumping is handled by the `ver-bump` package. You can easily increment the package version using a dedicated script.

```bash
# Bump the version in package.json
npm run bump-version
```

For more advanced versioning, refer to the [`bump` tool's documentation](https://github.com/fabiospampinato/bump).

---

Now that you have an overview of the development setup, a great next step is to dive into the codebase's organization. 

Proceed to the [Project Structure](./development-project-structure.md) to learn more.