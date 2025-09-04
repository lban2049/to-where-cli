# Project Structure

This guide provides an overview of the `to-where-cli` source code layout. Understanding the structure will help you navigate the codebase, make contributions, and understand how different components interact.

The project is organized to separate concerns, making it easier to maintain and extend.

## High-Level Overview

The following diagram illustrates the main components of the project and their relationships.

```d2
direction: down

"CLI Entry Point": {
  label: "src/cli"
  shape: package
}

"Core Logic": {
  label: "src/classes"
  shape: package
}

"Protocols": {
  label: "src/protocol (Interfaces)"
  shape: package
}

"Meta": {
  label: "src/meta (Data Structures)"
  shape: package
}

"CLI Entry Point" -> "Core Logic": "Initializes and runs commands"
"Core Logic" -> "Protocols": "Implements contracts"
"Core Logic" -> "Meta": "Uses shared types"

```

## Key Directories and Files

Here is a breakdown of the most important directories and their roles within the project.

| Path            | Description                                                                                                                                                                     |
| --------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `src/`          | The root directory for all TypeScript source code.                                                                                                                              |
| `src/cli/`      | Contains the executable entry point for the command-line interface. The `index.ts` file is responsible for setting up the command parser and executing the program.                     |
| `src/classes/`  | This directory holds the core logic of the application. It contains classes that handle command implementation, configuration management (`SimpleConfig`), and worker processes (`SimpleWorker`). |
| `src/protocol/` | Defines the TypeScript interfaces that serve as contracts for different modules. For example, `ConfigProtocol` and `WorkerProtocol` specify the required methods for any class that handles configuration or worker tasks. |
| `src/meta/`     | Contains shared data structures and type definitions, such as `Point` and `Config`. These types are used consistently across the application to ensure data integrity.                |
| `src/index.ts`  | The main entry point for the `src` module, which aggregates and exports the necessary classes and types for external use or for bundling.                                             |

---

This structure promotes modularity and clear separation of concerns. With this understanding of the project's layout, you can more easily locate relevant code. To learn about the development workflows, proceed to the [Available Scripts](./development-scripts.md) guide.