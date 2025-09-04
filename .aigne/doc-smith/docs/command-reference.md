# Command Reference

The `to-where-cli` tool, aliased as `tw`, provides a set of commands to manage URL shortcuts and perform quick searches. This section serves as a complete reference for every command, its subcommands, and available options. The general syntax is `tw [command] [arguments]`.

Below is a visual overview of the command structure.

```d2
direction: down

tw: {
  shape: rectangle
  label: "tw"

  "Core Commands": {
    shape: package
    grid-columns: 2
    add: "add <alias> <url>"
    rm: "rm <alias>"
    ls: "ls [alias]"
    clean: "clean"
  }

  "Git Command": {
    shape: package
    git: "git [subcommand]"
  }

  "Search Commands": {
    shape: package
    grid-columns: 3
    npm: "npm <query>"
    github: "github <query>"
    google: "google <query>"
    bing: "bing <query>"
    baidu: "baidu <query>"
  }

  tw -> "Core Commands"
  tw -> "Git Command"
  tw -> "Search Commands"
}
```

## Core Commands

These commands form the foundation of `to-where-cli`, allowing you to add, remove, list, and manage your URL aliases. They are essential for the primary functionality of the tool.

<x-cards data-columns="2">
  <x-card data-title="add" data-icon="lucide:plus-circle" data-href="/command-reference/core">Adds or updates a URL alias.</x-card>
  <x-card data-title="rm" data-icon="lucide:trash-2" data-href="/command-reference/core">Removes an existing alias.</x-card>
  <x-card data-title="ls" data-icon="lucide:list" data-href="/command-reference/core">Lists all or a specific alias.</x-card>
  <x-card data-title="clean" data-icon="lucide:shield-x" data-href="/command-reference/core">Removes all saved aliases.</x-card>
</x-cards>

For a detailed breakdown of each command, including all options and examples, please see the [Core Commands](./command-reference-core.md) reference.

## Git Command

The `git` command is a utility for quickly navigating to various pages of a Git repository, such as issues, pull requests, or the main page.

<x-card data-title="git" data-icon="lucide:git-branch" data-href="/command-reference/git" data-horizontal="true">A utility for opening specific pages of a Git repository directly from the command line.</x-card>

Learn more in the [Git Command](./command-reference-git.md) reference.

## Search Commands

Expedite your workflow by searching popular platforms directly from your terminal. These commands open your default browser with the search results for your query.

<x-cards data-columns="3">
  <x-card data-title="npm" data-icon="lucide:package-search" data-href="/command-reference/search">Search for packages on npm.</x-card>
  <x-card data-title="github" data-icon="lucide:github" data-href="/command-reference/search">Search for repositories or code on GitHub.</x-card>
  <x-card data-title="google" data-icon="lucide:search" data-href="/command-reference/search">Perform a Google search.</x-card>
  <x-card data-title="bing" data-icon="lucide:search-check" data-href="/command-reference/search">Perform a Bing search.</x-card>
  <x-card data-title="baidu" data-icon="lucide:search-code" data-href="/command-reference/search">Perform a Baidu search.</x-card>
</x-cards>

For more details, visit the [Search Commands](./command-reference-search.md) reference.

## Default Action: Open Alias

If you run `tw` followed by an argument that is not a recognized command, it is treated as an alias. The tool will look up the alias and open the corresponding URL in your default browser.

```shell
tw <alias>
```

### Example

```shell
# First, add an alias
tw add home https://github.com/skypesky

# Now, open it by its alias
tw home
```
This will open `https://github.com/skypesky` in your browser.

## Global Options

The following options are available for the main `tw` command.

| Option | Description |
|---|---|
| `-h`, `--help` | Display help for any command. |
| `-V`, `--version` | Display the current version of `to-where-cli`. |

---

This page provides a high-level overview of the available commands. To understand the full capabilities of each command, including specific arguments and options, proceed to the detailed reference pages.

Next, explore the [Core Commands](./command-reference-core.md) to learn about alias management.