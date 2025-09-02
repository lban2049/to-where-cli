# Development Guide

Welcome to the `to-where-cli` development guide. This section provides all the information you need to set up your local environment, understand the project's architecture, and contribute effectively. The project is built with TypeScript and runs on Node.js.

## Setting Up Your Environment

Before you begin, ensure you have a recent version of Node.js and the pnpm package manager installed.

1.  **Clone the Repository**

    First, clone the project repository from GitHub to your local machine:

    ```bash
    git clone https://github.com/skypesky/to-where-cli.git
    cd to-where-cli
    ```

2.  **Install Dependencies**

    The project uses pnpm to manage dependencies. Run the following command in the project's root directory to install them:

    ```bash
    pnpm install
    ```

## Getting Started

Once your environment is set up, you can start exploring the codebase and the development scripts. The following guides provide detailed information to help you get started.

<x-cards data-columns="2">
  <x-card data-title="Project Structure" data-icon="lucide:folder-tree" data-href="/development/project-structure">
    An overview of the project's source code layout, explaining the purpose of key directories like `src`, `dist`, and configuration files.
  </x-card>
  <x-card data-title="Available Scripts" data-icon="lucide:terminal" data-href="/development/scripts">
    A complete reference for the npm scripts defined in `package.json`, explaining how to build, test, lint, and deploy the application.
  </x-card>
</x-cards>

## Common Development Workflow

The typical workflow involves making changes to the source code in the `src` directory, and then using the provided npm scripts to build and test your changes.

-   **Build:** Compile the TypeScript source code using `pnpm build`.
-   **Test:** Run the entire test suite with `pnpm test`.
-   **Lint:** Check for code quality and style issues using `pnpm lint`.

For a comprehensive list and detailed explanations of all commands, refer to the [Available Scripts](./development-scripts.md) documentation.

---

After setting up your environment, we recommend diving into the [Project Structure](./development-project-structure.md) to understand how the code is organized. Following that, the [Available Scripts](./development-scripts.md) guide will be your primary reference for day-to-day development.