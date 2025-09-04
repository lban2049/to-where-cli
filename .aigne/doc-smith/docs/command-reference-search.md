# Search Commands

The `to-where-cli` provides a series of subcommands to quickly perform searches on popular developer platforms directly from your terminal. These commands open your default web browser to the corresponding search results page, streamlining your workflow.

## npm

Searches for packages on the npm registry. This command includes several options to navigate directly to specific pages of an npm package.

### Usage

```bash
tw npm [keyword] [options]
```

### Arguments

| Argument  | Description                                                 |
| :-------- | :---------------------------------------------------------- |
| `keyword` | Optional. The package name or search term. If omitted, it opens the npm homepage. |

### Options

| Short | Long           | Description                                                 |
| :---- | :------------- | :---------------------------------------------------------- |
| `-c`  | `--code`         | Opens the package's code tab on npm.                        |
| `-d`  | `--dependencies` | Opens the package's dependencies tab.                       |
| `-v`  | `--version`      | Opens the package's versions tab.                           |
| `-r`  | `--run-kit`      | Opens the package on RunKit for interactive testing.        |

### Examples

- **Search for packages related to 'react':**
  ```bash
  tw npm react
  ```

- **Open the npm homepage:**
  ```bash
  tw npm
  ```

- **View all versions of the 'lodash' package:**
  ```bash
  tw npm lodash -v
  ```

- **Explore the source code of the 'express' package:**
  ```bash
  tw npm express --code
  ```

- **Try 'commander' directly in your browser using RunKit:**
  ```bash
  tw npm commander -r
  ```

## github

Performs a search on GitHub.

### Usage

```bash
tw github [keyword]
```

### Arguments

| Argument  | Description                               |
| :-------- | :---------------------------------------- |
| `keyword` | Optional. The term to search for on GitHub. |

### Example

- **Search for repositories or code related to 'to-where-cli':**
  ```bash
  tw github to-where-cli
  ```

## google

Performs a search on Google.

### Usage

```bash
tw google [keyword]
```

### Arguments

| Argument  | Description                               |
| :-------- | :---------------------------------------- |
| `keyword` | Optional. The term to search for on Google. |

### Example

- **Search for 'how to use commander.js':**
  ```bash
  tw google "how to use commander.js"
  ```

## bing

Performs a search on Bing.

### Usage

```bash
tw bing [keyword]
```

### Arguments

| Argument  | Description                             |
| :-------- | :-------------------------------------- |
| `keyword` | Optional. The term to search for on Bing. |

### Example

- **Search for 'typescript best practices':**
  ```bash
  tw bing "typescript best practices"
  ```

## baidu

Performs a search on Baidu.

### Usage

```bash
tw baidu [keyword]
```

### Arguments

| Argument  | Description                              |
| :-------- | :--------------------------------------- |
| `keyword` | Optional. The term to search for on Baidu. |

### Example

- **Search for 'Node.js 教程' (Node.js tutorial):**
  ```bash
  tw baidu "Node.js 教程"
  ```
