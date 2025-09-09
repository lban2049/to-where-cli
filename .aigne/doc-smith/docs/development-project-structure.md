# Project Structure

Welcome to the `to-where-cli` development guide! A clear understanding of the project's structure is crucial for anyone looking to contribute or simply understand how it works. This document provides a high-level overview of the source code layout, explaining the purpose of each key directory and file.

The project is organized to separate concerns, making the codebase modular and easier to maintain. The core logic is divided into data structures (`meta`), contracts (`protocol`), and their concrete implementations (`classes`), which are then consumed by the command-line interface (`cli`).

## High-Level Overview

The following diagram illustrates the main directories within the `src` folder and their dependencies. The flow generally moves from the command-line entry point down to the core data definitions.

```d2
direction: down

cli: {
  label: "cli\n(Entry Point)"
  shape: rectangle
}

classes: {
  label: "classes\n(Implementations)"
  shape: rectangle
}

protocol: {
  label: "protocol\n(Interfaces)"
  shape: rectangle
}

meta: {
  label: "meta\n(Data Structures)"
  shape: rectangle
}

cli -> classes: "Uses"
classes -> protocol: "Implements"
protocol -> meta: "Uses"
classes -> meta: "Uses"
```

## Directory Breakdown

Here is a detailed breakdown of the primary directories within the `src` folder.

### `src/cli`

This is the main entry point for the command-line interface. It is responsible for parsing command-line arguments and executing the corresponding actions.

| File | Description |
|---|---|
| `index.ts` | The executable script that bootstraps and runs the CLI program. It initializes the command structure using the `createProgram` factory from the `classes` directory. |

### `src/classes`

This directory contains the concrete implementations of the application's core logic and protocols. These classes handle the actual work of managing aliases and configuration.

| File | Description |
|---|---|
| `create-program.ts` | A factory function responsible for setting up the command structure, defining all available commands, their options, and arguments. |
| `simple-worker.ts` | Implements the `WorkerProtocol` to handle core business logic like adding, removing, and listing aliases. |
| `simple-config.ts` | Implements the `ConfigProtocol` for all interactions with the configuration file, such as reading, writing, and updating alias data. |
| `open.ts` | Contains the logic for opening a URL or path associated with a given alias. |

### `src/protocol`

This directory defines the contracts or interfaces for different parts of the system. Using protocols allows for loose coupling between components and makes the codebase easier to test and extend.

| File | Description |
|---|---|
| `worker.protocol.ts` | Defines the `WorkerProtocol` interface, which specifies the methods for all core alias operations (`open`, `add`, `delete`, `list`, `clean`). |
| `config.protocol.ts` | Defines the `ConfigProtocol` interface for interacting with the configuration store, including methods like `get`, `set`, `add`, and `find`. |

### `src/meta`

This directory contains the core data structures and TypeScript type definitions used throughout the application. These files ensure data consistency across different modules.

| File | Description |
|---|---|
| `point.meta.ts` | Defines the `Point` type, which represents a single alias record containing its alias and path. |
| `config.meta.ts` | Defines the `Config` type, which represents the overall structure of the main configuration file. |

---

Now that you have an understanding of the project's layout, the next step is to learn about the development scripts used to build, test, and run the application. Please proceed to the [Available Scripts](./development-scripts.md) section.