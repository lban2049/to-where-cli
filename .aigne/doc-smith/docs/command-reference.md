# Command Reference

The `to-where-cli` provides a powerful set of commands to manage your URL aliases, navigate Git repositories, and perform quick searches directly from your terminal. This section serves as a comprehensive reference for all available commands and their options.

Explore the different command groups below to see detailed usage, arguments, and examples.

<x-cards data-columns="3">
  <x-card data-title="Core Commands" data-icon="lucide:archive" data-href="/command-reference/core" data-cta="View Details">
    Manage your URL aliases with essential commands like add, rm, ls, and clean.
  </x-card>
  <x-card data-title="Git Command" data-icon="lucide:git-branch" data-href="/command-reference/git" data-cta="View Details">
    Quickly open specific pages of a Git repository, such as issues, pull requests, and branches.
  </x-card>
  <x-card data-title="Search Commands" data-icon="lucide:search" data-href="/command-reference/search" data-cta="View Details">
    Perform searches on popular platforms like npm, GitHub, Google, Bing, and Baidu without leaving your terminal.
  </x-card>
</x-cards>

## Base Command

The primary and most direct use of `tw` is to open a URL using a pre-configured alias. If you run the command without any arguments, it will display the main help message.

### `tw [alias]`

When you run `tw` followed by an alias, it will open the corresponding URL in your default browser.

```shell
# Assuming 'home' is an alias for 'https://github.com/skypesky'
tw home
```

## Global Options

These options can be used with the base `tw` command.

| Option | Description |
|---|---|
| `-h`, `--help` | Display help information for the command. |
| `-V`, `--version` | Output the current version number of `to-where-cli`. |