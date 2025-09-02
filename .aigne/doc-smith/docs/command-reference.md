# Command Reference

The `to-where-cli` tool, aliased as `tw`, provides a suite of commands to manage URL aliases and perform quick searches directly from your terminal. The general structure for using the CLI is `tw [subcommand] [arguments]`.

This section serves as a comprehensive guide to all available commands. Below is a high-level overview of the command structure.

```d2
direction: down

"tw": {
  shape: cloud
  "Core Alias Commands": {
    "add": "Add or update an alias"
    "rm": "Remove an alias"
    "ls": "List all aliases"
    "clean": "Remove invalid aliases"
  }

  "Git Integration": {
    "git": "Open repository pages (issues, PRs, etc.)"
  }

  "Web Search": {
    "npm": "Search on npmjs.com"
    "github": "Search on GitHub"
    "google": "Search on Google"
    "bing": "Search on Bing"
    "baidu": "Search on Baidu"
  }
}
```

For detailed information on each command, including all available options and usage examples, explore the relevant sections below.

<x-cards data-columns="3">
  <x-card data-title="Core Commands" data-icon="lucide:box" data-href="/command-reference/core">
    Manage your URL aliases. Includes commands like `add`, `rm`, `ls`, and `clean` for creating, deleting, and listing your shortcuts.
  </x-card>
  <x-card data-title="Git Command" data-icon="lucide:git-branch" data-href="/command-reference/git">
    Quickly access various pages of a Git repository, such as issues, pull requests, and actions, using the `git` subcommand.
  </x-card>
  <x-card data-title="Search Commands" data-icon="lucide:search" data-href="/command-reference/search">
    Perform searches on popular websites directly from your terminal. Supported commands include `npm`, `github`, `google`, `bing`, and `baidu`.
  </x-card>
</x-cards>

Each subcommand has its own specific options and arguments. Click on the cards above to navigate to the detailed documentation for each command group.