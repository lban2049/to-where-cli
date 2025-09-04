# Overview

`to-where-cli` is a command-line tool designed to simplify your workflow by replacing long, hard-to-remember URLs with simple, intuitive aliases. It allows you to quickly open project repositories, documentation, and search pages directly from your terminal, saving you time and effort.

Instead of manually navigating through browser bookmarks or typing out complex web addresses, you can use a short command to get where you need to go instantly.

```d2
direction: down

"Developer": {
  shape: person
}

"Terminal": {
  shape: rectangle
  "tw home": "User types a short alias"
}

"to-where-cli": {
  shape: package
  "Alias Lookup": "Resolves 'home' to its full URL"
}

"Default Browser": {
  shape: rectangle
  "Opens the resolved URL"
}

"Developer" -> "Terminal": "1. Executes command"
"Terminal" -> "to-where-cli": "2. Invokes CLI"
"to-where-cli" -> "Default Browser": "3. Launches URL"
```

## Key Features

<x-cards data-columns="3">
  <x-card data-title="Effortless Alias Management" data-icon="lucide:bookmark-plus">
    Create, list, update, and remove simple aliases for any URL directly from your command line.
  </x-card>
  <x-card data-title="Quick GitHub Navigation" data-icon="lucide:github">
    Instantly open specific pages of a git repository, such as issues, pull requests, or the main project page.
  </x-card>
  <x-card data-title="Integrated Search Shortcuts" data-icon="lucide:search">
    Perform searches directly on npm, GitHub, Google, Bing, and Baidu without needing to open your browser first.
  </x-card>
</x-cards>

## Supported Platforms

The CLI is currently supported and tested on the following operating systems:

- macOS
- Windows

## Next Steps

Ready to get started? Head over to the [Installation](./getting-started-installation.md) guide to set up `to-where-cli` on your system and create your first alias.