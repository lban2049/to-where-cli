# Project Structure

This document provides an overview of the `to-where-cli` source code layout. Understanding the structure is key for developers who want to contribute to the project or understand its internal workings.

The codebase is organized to separate concerns, with distinct directories for the command-line interface, core business logic, data contracts (protocols), and data models (meta).

### Architecture Overview

The following diagram illustrates the high-level structure and the relationships between the main components of the application.

```d2
direction: down

"src": {
  shape: package

  "cli/": {
    label: "CLI Layer"
    tooltip: "Handles command-line interaction"
    "index.ts": "CLI Entry Point"
  }

  "classes/": {
    label: "Business Logic Layer"
    tooltip: "Implements core functionalities"
    "create-program.ts": "Builds the command structure"
    "simple-config.ts": "Manages configuration"
    "simple-worker.ts": "Executes alias tasks"
  }

  "protocol/": {
    label: "Contract Layer"
    tooltip: "Defines interfaces for services"
    "config.protocol.ts": "IConfig interface"
    "worker.protocol.ts": "IWorker interface"
  }

  "meta/": {
    label: "Data Model Layer"
    tooltip: "Defines core data structures"
    "config.meta.ts": "Config type"
    "point.meta.ts": "Point type"
  }
}

"src.cli/" -> "src.classes/": "Initializes & runs program"
"src.classes/" -> "src.protocol/": "Implements Contracts"
"src.protocol/" -> "src.meta/": "Uses Data Models"

```

### Key Directories and Files

Here is a detailed breakdown of the purpose of each major directory and file within the `src` folder.

| Path | Description |
|---|---|
| `src/cli/index.ts` | The main entry point for the executable CLI. It uses the `#! /usr/bin/env node` shebang to be runnable from the command line. Its primary role is to instantiate and run the program defined in `create-program.ts`. |
| `src/classes/` | This directory contains the concrete implementations of the application's core logic. For example, `SimpleConfig` handles reading and writing to the configuration file, and `SimpleWorker` performs the actions like adding or opening an alias. |
| `src/protocol/` | Contains TypeScript interfaces that define the contracts for different parts of the system. For instance, `ConfigProtocol` defines all the methods that any configuration manager must implement. This approach allows for decoupling the implementation from the interface. |
| `src/meta/` | This directory holds the core data structures and type definitions used throughout the application, such as `Point` and `Config`. Centralizing these models ensures data consistency. |
| `src/index.ts` | This is the main entry point for the module if it were to be used as a library in another project. It exports the primary classes and functionalities. |

By organizing the code in this manner, the project maintains a clear separation between the user-facing CLI, the underlying business logic, and the data it operates on.

Now that you have an understanding of the project's layout, you can explore the available development scripts to build, test, and run the application. See the [Available Scripts](./development-scripts.md) guide for more details.