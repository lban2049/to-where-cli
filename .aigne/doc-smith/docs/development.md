# Development Guide

Welcome to the development guide for `to-where-cli`. This document provides essential information for anyone looking to contribute to the project. Here you will find details on the project's architecture and the scripts needed to build, test, and manage the application.

To get started, clone the repository and install the necessary dependencies:

```bash
git clone https://github.com/skypesky/to-where-cli.git
cd to-where-cli
pnpm install
```

This guide is divided into the following sections to help you navigate the development process:

<x-cards>
  <x-card data-title="Project Structure" data-icon="lucide:folder-tree" data-href="/development/project-structure">
    Get an overview of the source code layout, explaining the purpose of key directories and configuration files like tsconfig.json and jest.config.js.
  </x-card>
  <x-card data-title="Available Scripts" data-icon="lucide:terminal" data-href="/development/scripts">
    Find a comprehensive reference for the npm scripts used to lint, test, build, and deploy the application, as defined in package.json.
  </x-card>
</x-cards>

### Versioning

Version management for this project is handled using `ver-bump`. To increment the package version, you can use the `bump-version` script:

```bash
npm run bump-version
```

This command simplifies the process of updating the version number in `package.json` according to semantic versioning.

---

Once you are familiar with the project setup, a great next step is to explore the existing functionalities. Head over to the [Command Reference](./command-reference.md) for a complete list of commands and their options.