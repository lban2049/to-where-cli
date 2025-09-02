# Search Integrations

The `to-where-cli` tool provides quick access to popular search engines and platforms directly from your terminal. This feature allows you to perform searches on npm, Google, Baidu, Bing, and GitHub without needing to open a web browser manually and navigate to the respective sites. This section details the usage and available options for each search integration.

For general information on how commands work in `to-where-cli`, refer to the [Command Reference](./command-reference.md) section.

## npm Search

The `npm` command allows you to quickly search for packages on npmjs.com or directly open specific package-related pages like code, dependencies, or versions.

**Usage**

```bash
tw npm [keyword]
# or
tw npm search [keyword]
```

When a `keyword` is provided without specific options, `to-where-cli` opens the npm search results page for that keyword. If no `keyword` is provided, it opens the npm homepage. The `search` subcommand is the default and hidden, meaning `tw npm [keyword]` is equivalent to `tw npm search [keyword]`.

**Options**

| Option | Alias | Description | Example URL opened | Valid with keyword |
|---|---|---|---|---|
| `--code` | `-c` | Opens the package's code page on npmjs.com. | `https://www.npmjs.com/package/webpack?activeTab=code` | Yes |
| `--dependencies` | `-d` | Opens the package's dependencies page on npmjs.com. | `https://www.npmjs.com/package/react?activeTab=dependencies` | Yes |
| `--version` | `-v` | Opens the package's versions page on npmjs.com. | `https://www.npmjs.com/package/vue?activeTab=versions` | Yes |
| `--run-kit` | `-r` | Opens the package's page on npm.runkit.com. | `https://npm.runkit.com/express` | Yes |

**Examples**

Search for packages on npm:

```bash
tw npm react
# Opens: https://www.npmjs.com/search?q=react
```

Open the code page for a specific npm package:

```bash
tw npm webpack -c
# Opens: https://www.npmjs.com/package/webpack?activeTab=code
```

View dependencies of a package:

```bash
tw npm lodash --dependencies
# Opens: https://www.npmjs.com/package/lodash?activeTab=dependencies
```

Check versions of an npm package:

```bash
tw npm vue -v
# Opens: https://www.npmjs.com/package/vue?activeTab=versions
```

Explore a package on RunKit:

```bash
tw npm express -r
# Opens: https://npm.runkit.com/express
```

## Google Search

The `google` command enables you to perform quick searches directly on Google.

**Usage**

```bash
tw google [keyword]
# or
tw google search [keyword]
```

If a `keyword` is provided, `to-where-cli` opens the Google search results page. If no `keyword` is provided, it opens the Google homepage. The `search` subcommand is the default and hidden.

**Examples**

Search for a topic on Google:

```bash
tw google command line interface
# Opens: https://www.google.com/search?q=command%20line%20interface
```

Open the Google homepage:

```bash
tw google
# Opens: https://www.google.com
```

## Baidu Search

The `baidu` command enables you to perform quick searches directly on Baidu.

**Usage**

```bash
tw baidu [keyword]
# or
tw baidu search [keyword]
```

If a `keyword` is provided, `to-where-cli` opens the Baidu search results page. If no `keyword` is provided, it opens the Baidu homepage. The `search` subcommand is the default and hidden.

**Examples**

Search for a topic on Baidu:

```bash
tw baidu 命令行工具
# Opens: https://www.baidu.com/s?wd=%E5%91%BD%E4%BB%A4%E8%A1%8C%E5%B7%A5%E5%85%B7
```

Open the Baidu homepage:

```bash
tw baidu
# Opens: https://www.baidu.com
```

## Bing Search

The `bing` command enables you to perform quick searches directly on Bing.

**Usage**

```bash
tw bing [keyword]
# or
tw bing search [keyword]
```

If a `keyword` is provided, `to-where-cli` opens the Bing search results page. If no `keyword` is provided, it opens the Bing homepage. The `search` subcommand is the default and hidden.

**Examples**

Search for a topic on Bing:

```bash
tw bing desktop applications
# Opens: https://www.bing.com/search?q=desktop%20applications
```

Open the Bing homepage:

```bash
tw bing
# Opens: https://www.bing.com
```

## GitHub Search

The `github` command enables you to perform quick searches for repositories, code, or issues directly on GitHub.

**Usage**

```bash
tw github [keyword]
# or
tw github search [keyword]
```

If a `keyword` is provided, `to-where-cli` opens the GitHub search results page. If no `keyword` is provided, it opens the GitHub homepage. The `search` subcommand is the default and hidden.

**Examples**

Search for a repository on GitHub:

```bash
tw github to-where-cli
# Opens: https://github.com/search?q=to-where-cli
```

Open the GitHub homepage:

```bash
tw github
# Opens: https://github.com
```

---

This section covered how to leverage `to-where-cli` for integrated searching across popular platforms. This functionality streamlines your workflow by providing direct access to search results without manual browser navigation. Continue to the [Development Guide](./development-guide.md) to learn about contributing to `to-where-cli`.