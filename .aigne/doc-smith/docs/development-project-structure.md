# Project Structure

This document provides an overview of the `to-where-cli` source code layout. Understanding the structure is key for developers looking to contribute to the project or understand its internal workings.

The project follows a modular structure, separating concerns into distinct directories for the command-line interface, core business logic, data protocols, and metadata definitions.

### High-Level Overview

The following diagram illustrates the main directories within the `src` folder and their primary relationships.

```d2
direction: down

src-cli: {
  label: "src/cli\n(Entry Point)"
  shape: rectangle
}

src-classes: {
  label: "src/classes\n(Core Logic & Implementations)"
  shape: rectangle
}

src-protocol: {
  label: "src/protocol\n(Data Contracts / Interfaces)"
  shape: rectangle
}

src-meta: {
  label: "src/meta\n(Data Structures)"
  shape: rectangle
}

src-cli -> src-classes: "Initializes Program"
src-classes -> src-protocol: "Implements Protocols"
src-protocol -> src-meta: "Uses Data Structures"
```

### Directory Breakdown

Below is a detailed explanation of each key directory and its purpose.

| Directory      | Description                                                                                                                                                                                                                                                        |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `src/cli`      | This is the executable entry point for the CLI. The `index.ts` file is responsible for initializing and parsing the commands defined in the `classes` directory.                                                                                             |
| `src/classes`  | Contains the core application logic. This directory holds the concrete implementations for command creation (`create-program`), configuration handling (`simple-config`), and alias operations (`simple-worker`).                                                  |
| `src/protocol` | Defines the TypeScript interfaces that act as contracts for the core components. For example, `ConfigProtocol` specifies all the methods required for managing configuration data, and `WorkerProtocol` defines the methods for alias-related actions. This separation allows for easier testing and maintenance. |
| `src/meta`     | Holds the definitions for the primary data structures used throughout the application, such as `Point` (representing an alias) and `Config`. These files ensure data consistency across different modules.                                                 |

By organizing the code this way, the CLI's user-facing parts are decoupled from the underlying business logic and data management, making the codebase cleaner and more scalable.

### Next Steps

Now that you have an understanding of the project's layout, you can learn how to build, test, and run the application by reading the [Available Scripts](./development-scripts.md) documentation.