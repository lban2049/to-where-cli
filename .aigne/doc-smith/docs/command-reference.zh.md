# 命令参考

`to-where-cli` 工具（别名为 `tw`）提供了一组用于管理 URL 快捷方式和执行快速搜索的命令。本节是每个命令、其子命令和可用选项的完整参考。通用语法为 `tw [command] [arguments]`。

下方是命令结构的可视化概览。

```d2
direction: down

tw: {
  shape: rectangle
  label: "tw"

  "Core Commands": {
    shape: package
    grid-columns: 2
    add: "add <alias> <url>"
    rm: "rm <alias>"
    ls: "ls [alias]"
    clean: "clean"
  }

  "Git Command": {
    shape: package
    git: "git [subcommand]"
  }

  "Search Commands": {
    shape: package
    grid-columns: 3
    npm: "npm <query>"
    github: "github <query>"
    google: "google <query>"
    bing: "bing <query>"
    baidu: "baidu <query>"
  }

  tw -> "Core Commands"
  tw -> "Git Command"
  tw -> "Search Commands"
}
```

## 核心命令

这些命令是 `to-where-cli` 的基础，用于添加、删除、列出和管理 URL 别名。它们是该工具核心功能的关键。

<x-cards data-columns="2">
  <x-card data-title="add" data-icon="lucide:plus-circle" data-href="/command-reference/core">添加或更新 URL 别名。</x-card>
  <x-card data-title="rm" data-icon="lucide:trash-2" data-href="/command-reference/core">删除现有别名。</x-card>
  <x-card data-title="ls" data-icon="lucide:list" data-href="/command-reference/core">列出所有或特定别名。</x-card>
  <x-card data-title="clean" data-icon="lucide:shield-x" data-href="/command-reference/core">删除所有已保存的别名。</x-card>
</x-cards>

若要了解每个命令的详细信息（包括所有选项和示例），请参阅[核心命令](./command-reference-core.md)参考文档。

## Git 命令

`git` 命令是一个实用工具，可用于快速导航至 Git 仓库的各个页面，例如 issues、pull requests 或主页。

<x-card data-title="git" data-icon="lucide:git-branch" data-href="/command-reference/git" data-horizontal="true">一个可从命令行直接打开 Git 仓库特定页面的实用工具。</x-card>

在[Git 命令](./command-reference-git.md)参考文档中了解更多信息。

## 搜索命令

通过在终端中直接搜索热门平台来加快工作流程。这些命令会使用默认浏览器打开查询的搜索结果页面。

<x-cards data-columns="3">
  <x-card data-title="npm" data-icon="lucide:package-search" data-href="/command-reference/search">在 npm 上搜索包。</x-card>
  <x-card data-title="github" data-icon="lucide:github" data-href="/command-reference/search">在 GitHub 上搜索仓库或代码。</x-card>
  <x-card data-title="google" data-icon="lucide:search" data-href="/command-reference/search">执行 Google 搜索。</x-card>
  <x-card data-title="bing" data-icon="lucide:search-check" data-href="/command-reference/search">执行 Bing 搜索。</x-card>
  <x-card data-title="baidu" data-icon="lucide:search-code" data-href="/command-reference/search">执行百度搜索。</x-card>
</x-cards>

有关更多详细信息，请访问[搜索命令](./command-reference-search.md)参考文档。

## 默认操作：打开别名

如果运行 `tw` 时所跟的参数不是一个已识别的命令，该参数将被视为一个别名。工具会查找该别名，并在默认浏览器中打开对应的 URL。

```shell
tw <alias>
```

### 示例

```shell
# 首先，添加一个别名
tw add home https://github.com/skypesky

# 现在，通过别名打开它
tw home
```
这将在浏览器中打开 `https://github.com/skypesky`。

## 全局选项

以下选项适用于主 `tw` 命令。

| 选项 | 描述 |
|---|---|
| `-h`, `--help` | 显示任何命令的帮助信息。 |
| `-V`, `--version` | 显示 `to-where-cli` 的当前版本。 |

---

本页对可用命令进行了高级概述。要了解每个命令的全部功能（包括具体参数和选项），请继续阅读详细的参考页面。

接下来，请浏览[核心命令](./command-reference-core.md)以了解别名管理。