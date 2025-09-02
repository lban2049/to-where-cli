# 搜索集成

`to-where-cli` 工具提供从终端直接快速访问流行的搜索引擎和平台的功能。此功能使您无需手动打开网页浏览器并导航到相应网站，即可在 npm、Google、百度、必应和 GitHub 上执行搜索。本节详细介绍了每个搜索集成的用法和可用选项。

有关 `to-where-cli` 中命令工作方式的通用信息，请参阅[命令参考](./command-reference.md)部分。

## npm 搜索

`npm` 命令允许您在 npmjs.com 上快速搜索软件包，或直接打开与特定软件包相关的页面，例如代码、依赖项或版本。

**用法**

```bash
tw npm [keyword]
# or
tw npm search [keyword]
```

当未提供特定选项而提供了 `keyword` 时，`to-where-cli` 将打开该关键词的 npm 搜索结果页面。如果未提供 `keyword`，它将打开 npm 主页。`search` 子命令是默认且隐藏的，这意味着 `tw npm [keyword]` 等同于 `tw npm search [keyword]`。

**选项**

| 选项 | 别名 | 描述 | 打开的示例 URL | 是否需要关键词 |
|---|---|---|---|---|
| `--code` | `-c` | 在 npmjs.com 上打开软件包的代码页面。 | `https://www.npmjs.com/package/webpack?activeTab=code` | 是 |
| `--dependencies` | `-d` | 在 npmjs.com 上打开软件包的依赖项页面。 | `https://www.npmjs.com/package/react?activeTab=dependencies` | 是 |
| `--version` | `-v` | 在 npmjs.com 上打开软件包的版本页面。 | `https://www.npmjs.com/package/vue?activeTab=versions` | 是 |
| `--run-kit` | `-r` | 在 npm.runkit.com 上打开软件包页面。 | `https://npm.runkit.com/express` | 是 |

**示例**

在 npm 上搜索软件包：

```bash
tw npm react
# 打开：https://www.npmjs.com/search?q=react
```

打开特定 npm 软件包的代码页面：

```bash
tw npm webpack -c
# 打开：https://www.npmjs.com/package/webpack?activeTab=code
```

查看软件包的依赖项：

```bash
tw npm lodash --dependencies
# 打开：https://www.npmjs.com/package/lodash?activeTab=dependencies
```

检查 npm 软件包的版本：

```bash
tw npm vue -v
# 打开：https://www.npmjs.com/package/vue?activeTab=versions
```

在 RunKit 上探索软件包：

```bash
tw npm express -r
# 打开：https://npm.runkit.com/express
```

## Google 搜索

`google` 命令使您能够直接在 Google 上执行快速搜索。

**用法**

```bash
tw google [keyword]
# or
tw google search [keyword]
```

如果提供了 `keyword`，`to-where-cli` 将打开 Google 搜索结果页面。如果未提供 `keyword`，它将打开 Google 主页。`search` 子命令是默认且隐藏的。

**示例**

在 Google 上搜索主题：

```bash
tw google command line interface
# 打开：https://www.google.com/search?q=command%20line%20interface
```

打开 Google 主页：

```bash
tw google
# 打开：https://www.google.com
```

## 百度搜索

`baidu` 命令使您能够直接在百度上执行快速搜索。

**用法**

```bash
tw baidu [keyword]
# or
tw baidu search [keyword]
```

如果提供了 `keyword`，`to-where-cli` 将打开百度搜索结果页面。如果未提供 `keyword`，它将打开百度主页。`search` 子命令是默认且隐藏的。

**示例**

在百度上搜索主题：

```bash
tw baidu 命令行工具
# 打开：https://www.baidu.com/s?wd=%E5%91%BD%E4%BB%A4%E8%A1%8C%E5%B7%A5%E5%85%B7
```

打开百度主页：

```bash
tw baidu
# 打开：https://www.baidu.com
```

## 必应搜索

`bing` 命令使您能够直接在必应上执行快速搜索。

**用法**

```bash
tw bing [keyword]
# or
tw bing search [keyword]
```

如果提供了 `keyword`，`to-where-cli` 将打开必应搜索结果页面。如果未提供 `keyword`，它将打开必应主页。`search` 子命令是默认且隐藏的。

**示例**

在必应上搜索主题：

```bash
tw bing desktop applications
# 打开：https://www.bing.com/search?q=desktop%20applications
```

打开必应主页：

```bash
tw bing
# 打开：https://www.bing.com
```

## GitHub 搜索

`github` 命令使您能够直接在 GitHub 上快速搜索仓库、代码或议题。

**用法**

```bash
tw github [keyword]
# or
tw github search [keyword]
```

如果提供了 `keyword`，`to-where-cli` 将打开 GitHub 搜索结果页面。如果未提供 `keyword`，它将打开 GitHub 主页。`search` 子命令是默认且隐藏的。

**示例**

在 GitHub 上搜索仓库：

```bash
tw github to-where-cli
# 打开：https://github.com/search?q=to-where-cli
```

打开 GitHub 主页：

```bash
tw github
# 打开：https://github.com
```

---

本节介绍了如何利用 `to-where-cli` 在流行平台进行集成搜索。此功能通过提供对搜索结果的直接访问，无需手动浏览器导航，从而简化了您的工作流程。继续阅读[开发指南](./development-guide.md)，了解如何为 `to-where-cli` 贡献。
