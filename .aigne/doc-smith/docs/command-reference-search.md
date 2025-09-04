# Search Commands

The `to-where` CLI integrates several popular search engines, allowing you to quickly perform searches directly from your terminal. These commands will open the corresponding search results page in your default web browser.

<x-cards data-columns="3">
  <x-card data-title="npm" data-icon="cib:npm">Search for packages on the npm registry.</x-card>
  <x-card data-title="github" data-icon="cib:github">Search for repositories, code, and users on GitHub.</x-card>
  <x-card data-title="google" data-icon="cib:google">Perform a web search using Google.</x-card>
  <x-card data-title="bing" data-icon="cib:bing">Perform a web search using Bing.</x-card>
  <x-card data-title="baidu" data-icon="cib:baidu">Perform a web search using Baidu.</x-card>
</x-cards>

## npm

The `npm` command allows you to search for packages on [npmjs.com](https://www.npmjs.com) and quickly access specific package pages like versions, dependencies, and code repositories.

### Usage

```bash
tw npm [keyword] [options]
```

### Arguments

-   `[keyword]`: The name of the package or search term. If omitted, the command opens the npm homepage.

### Options

| Option | Long Form      | Description                        |
| :----- | :------------- | :--------------------------------- |
| `-c`   | `--code`       | Open the package's code page.      |
| `-d`   | `--dependencies` | Open the package's dependencies page. |
| `-v`   | `--version`    | Open the package's versions page.  |
| `-r`   | `--run-kit`    | Open the package's RunKit page.    |

### Examples

-   **Search for a package:**

    ```bash
    tw npm react
    ```

-   **Open the versions page for a specific package:**

    ```bash
    tw npm express -v
    ```

-   **View dependencies for a package:**

    ```bash
    tw npm commander -d
    ```

-   **Jump to the RunKit page:**

    ```bash
    tw npm lodash -r
    ```

-   **Open the npm homepage:**

    ```bash
    tw npm
    ```

## github

Performs a search on [github.com](https://github.com).

### Usage

```bash
tw github [keyword]
```

### Arguments

-   `[keyword]`: The search term. If omitted, it opens the GitHub search page.

### Examples

-   **Search for a repository:**

    ```bash
    tw github to-where-cli
    ```

-   **Search for a user or topic:**

    ```bash
    tw github nodejs
    ```

-   **Open GitHub's main search page:**

    ```bash
    tw github
    ```

## google

Performs a standard web search using [google.com](https://www.google.com).

### Usage

```bash
tw google [keyword]
```

### Arguments

-   `[keyword]`: The search term. If omitted, it opens the Google homepage.

### Examples

-   **Search for a topic:**

    ```bash
    tw google "how to use commander.js"
    ```

## bing

Performs a web search using [bing.com](https://www.bing.com).

### Usage

```bash
tw bing [keyword]
```

### Arguments

-   `[keyword]`: The search term. If omitted, it opens the Bing homepage.

### Examples

-   **Search for a topic:**

    ```bash
    tw bing "latest typescript features"
    ```

## baidu

Performs a web search using [baidu.com](https://www.baidu.com).

### Usage

```bash
tw baidu [keyword]
```

### Arguments

-   `[keyword]`: The search term. If omitted, it opens the Baidu homepage.

### Examples

-   **Search for a topic:**

    ```bash
    tw baidu "Vue 3 教程"
    ```
