# Overview

`to-where-cli` is a command-line tool designed to simplify your workflow by using an alias mechanism to open obscure or hard-to-remember URLs. It helps you quickly access various addresses, from GitHub repositories to the search pages of npm, Google, and other sites, directly from your terminal.

### Core Concept

The tool works by mapping a simple, memorable alias to a complex URL. Once an alias is set, you can use it with the `tw` command to open the corresponding address in your default browser.

```d2
direction: right

User: {
  shape: person
}

"CLI: to-where-cli": {
  shape: rectangle
}

"URL: Website / Search Page": {
  shape: cloud
}

User -> "CLI: to-where-cli": "Executes command (e.g., 'tw home')"
"CLI: to-where-cli" -> "URL: Website / Search Page": "Resolves alias and opens URL in browser"
```

### Key Features

`to-where-cli` provides several features to streamline your command-line navigation.

<x-cards data-columns="3">
  <x-card data-title="Alias Management" data-icon="lucide:link">
    Create, list, update, and remove custom aliases for any URL, making long and complex addresses easily accessible.
  </x-card>
  <x-card data-title="Git Integration" data-icon="lucide:github">
    Directly open specific pages of a Git repository, such as issues, pull requests, or the project homepage.
  </x-card>
  <x-card data-title="Quick Search" data-icon="lucide:search">
    Jump straight to search results on platforms like npm, GitHub, Google, Bing, and Baidu without opening a browser first.
  </x-card>
</x-cards>

### Supported Platforms

Currently, `to-where-cli` officially supports the following operating systems:

- macOS
- Windows

### Next Steps

Ready to simplify your URL management? Follow the installation guide to get started.

<x-card data-title="Getting Started" data-icon="lucide:rocket" data-href="/getting-started/installation" data-cta="Install the CLI">
  A step-by-step guide for new users to install the CLI and learn the basic commands for alias management.
</x-card>