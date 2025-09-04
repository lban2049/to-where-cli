# Overview

`to-where-cli` is a command-line utility designed to simplify accessing web addresses from your terminal. It uses a straightforward alias system to let you open long, complex, or frequently used URLs with short, memorable commands. This is particularly useful for developers who regularly navigate to specific GitHub repositories, search package registries, or use various search engines.

Instead of remembering and typing `https://github.com/skypesky/to-where-cli`, you can simply create an alias and run `tw to-where`.

```d2
direction: down

Terminal: {
  shape: rectangle

  User: {
    shape: person
  }

  CLI-Input: {
    label: "User types `tw home`"
    shape: rectangle
  }

  User -> CLI-Input
}

to-where-cli: {
  shape: package
  
  Alias-Lookup: {
    label: "1. Looks up alias 'home'"
    shape: rectangle
  }
  
  URL-Retrieval: {
    label: "2. Retrieves stored URL"
    shape: rectangle
  }
  
  Open-Command: {
    label: "3. Issues system 'open' command"
    shape: rectangle
  }

  Alias-Lookup -> URL-Retrieval -> Open-Command
}

Browser: {
  shape: rectangle
  label: "Default Web Browser"
}

Terminal -> to-where-cli: "Executes"
to-where-cli -> Browser: "Launches URL"
```

## Key Features

<x-cards data-columns="3">
  <x-card data-title="Alias Management" data-icon="lucide:bookmark-plus">
    Create, list, update, and remove short aliases for any URL. Open websites with a simple command instead of typing or pasting a full address.
  </x-card>
  <x-card data-title="Git Repository Shortcuts" data-icon="lucide:git-branch">
    Navigate directly to specific pages of a Git repository, such as issues, pull requests, or the main project page, without needing the full URL.
  </x-card>
  <x-card data-title="Direct Web Search" data-icon="lucide:search">
    Perform searches on popular sites like Google, Bing, Baidu, npm, and GitHub directly from your command line, opening the results page in your browser.
  </x-card>
</x-cards>

## Supported Platforms

The tool currently supports the following operating systems:

- macOS
- Windows

---

Ready to simplify your workflow? Head over to the [Getting Started](./getting-started.md) guide to install the CLI and create your first alias.