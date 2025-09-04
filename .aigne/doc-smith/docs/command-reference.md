# Command Reference

The `to-where-cli` provides a suite of commands to manage URL aliases and quickly access web resources directly from your terminal. This section serves as a comprehensive reference for all available commands, their subcommands, and options.

## Command Structure Overview

The CLI is organized around a main `tw` command followed by subcommands for specific actions. Here is a visual breakdown of the available commands:

```d2
direction: down

"tw": {
  shape: hexagon
  label: "tw (CLI Entry)"
}

"Commands": {
  shape: package
  grid-columns: 3

  "Core Commands": {
    shape: package
    "add"
    "rm"
    "ls"
    "clean"
  }

  "Git Command": {
    shape: package
    "git"
  }

  "Search Commands": {
    shape: package
    "npm"
    "github"
    "google"
    "bing"
    "baidu"
  }
}

"Default Action": {
  label: "tw [alias]"
  shape: rectangle
}

"Global Options": {
    shape: package
    "-h, --help"
    "-V, --version"
}

"tw" -> "Default Action": "Default"
"tw" -> "Commands": "Subcommands"
"tw" -> "Global Options": "Options"
```

## Main Command (`tw`)

The most basic usage of `to-where-cli` is to open a stored alias. If you run `tw` followed by a string, it will treat that string as an alias and attempt to open its corresponding URL.

```shell
# Opens the URL associated with the 'home' alias
tw home
```

If you run `tw` with no arguments, it will display the main help menu.

```shell
# Displays the main help menu
tw
```

## Command Categories

Commands are grouped into logical categories. Select a category below to view detailed documentation for each command.

<x-cards data-columns="3">
  <x-card data-title="Core Commands" data-icon="lucide:archive" data-href="/command-reference/core">
    Manage your aliases with fundamental commands like add, remove, list, and clean.
  </x-card>
  <x-card data-title="Git Command" data-icon="lucide:git-branch" data-href="/command-reference/git">
    Quickly navigate to various pages of a Git repository, such as issues, pull requests, and actions.
  </x-card>
  <x-card data-title="Search Commands" data-icon="lucide:search" data-href="/command-reference/search">
    Perform searches directly from your terminal on platforms like NPM, GitHub, Google, and more.
  </x-card>
</x-cards>

## Global Options

These options can be used with the main `tw` command and most subcommands.

| Option              | Description                  |
| ------------------- | ---------------------------- |
| `-h`, `--help`      | Display help for a command.  |
| `-V`, `--version`   | Output the version number.   |

**Example:**

```shell
# Get help for the 'add' subcommand
tw add --help

# Check your installed version
tw --version
```

---

Now that you have an overview of the command structure, dive into the specifics by exploring the [Core Commands](./command-reference-core.md) documentation.