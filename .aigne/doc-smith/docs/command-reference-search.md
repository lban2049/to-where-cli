# Search Commands

The `to-where-cli` provides a set of convenient subcommands to perform searches on popular developer platforms directly from your terminal. These commands open a new tab in your default web browser with the search results. The general syntax is `tw <platform> [keyword]`.

## `npm`

The `npm` command allows you to search for packages on the npm registry and quickly access specific package pages like versions, dependencies, or source code.

### Usage

```bash
tw npm [keyword] [options]
```

### Arguments

| Argument    | Description                                                                    |
|-------------|--------------------------------------------------------------------------------|
| `[keyword]` | The search term or package name. If omitted, it opens the [npm homepage](https://www.npmjs.com). |

### Options

| Option           | Alias | Description                                                        |
|------------------|-------|--------------------------------------------------------------------|
| `--code`         | `-c`  | Opens the package's code page.                                     |
| `--dependencies` | `-d`  | Opens the package's dependencies page.                             |
| `--version`      | `-v`  | Opens the package's versions page.                                 |
| `--run-kit`      | `-r`  | Opens the package on [RunKit](https://runkit.com) for interactive testing. |

### Examples

```bash
# Search for 'react' on npm
tw npm react

# Open the versions page for the 'commander' package
tw npm commander -v

# Open the dependencies page for the 'express' package
tw npm express --dependencies

# Open the code page for the 'lodash' package
tw npm lodash -c

# Open 'axios' on RunKit
tw npm axios -r

# Open the npm homepage
tw npm
```

## `github`

Performs a search on GitHub.

### Usage

```bash
tw github [keyword]
```

### Arguments

| Argument    | Description                                                                  |
|-------------|------------------------------------------------------------------------------|
| `[keyword]` | The search term. If omitted, it opens the [GitHub search page](https://github.com/search). |

### Examples

```bash
# Search for repositories or code related to 'd3'
tw github d3

# Open the main GitHub search page
tw github
```

## `google`

Performs a search on Google.

### Usage

```bash
tw google [keyword]
```

### Examples

```bash
# Search for 'how to use git' on Google
tw google "how to use git"
```

## `bing`

Performs a search on Bing.

### Usage

```bash
tw bing [keyword]
```

### Examples

```bash
# Search for 'typescript tutorial' on Bing
tw bing "typescript tutorial"
```

## `baidu`

Performs a search on Baidu.

### Usage

```bash
tw baidu [keyword]
```

### Examples

```bash
# Search for 'Vue.js' on Baidu
tw baidu Vue.js
```

---

Now that you've mastered searching, you might be interested in contributing to the project. Head over to the [Development Guide](./development.md) for details on the project structure and setup.