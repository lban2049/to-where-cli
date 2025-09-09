# 命令参考

`to-where-cli` 提供了一套功能强大的命令，用于管理 URL 别名、浏览 Git 仓库，以及直接从终端执行快速搜索。本节是所有可用命令及其选项的全面参考。

浏览下方的不同命令组，查看详细用法、参数和示例。

<x-cards data-columns="3">
  <x-card data-title="核心命令" data-icon="lucide:archive" data-href="/command-reference/core" data-cta="查看详情">
    使用 add、rm、ls 和 clean 等核心命令管理 URL 别名。
  </x-card>
  <x-card data-title="Git 命令" data-icon="lucide:git-branch" data-href="/command-reference/git" data-cta="查看详情">
    快速打开 Git 仓库的特定页面，例如 issues、pull requests 和 branches。
  </x-card>
  <x-card data-title="搜索命令" data-icon="lucide:search" data-href="/command-reference/search" data-cta="查看详情">
    无需离开终端，即可在 npm、GitHub、Google、Bing 和百度等常用平台上执行搜索。
  </x-card>
</x-cards>

## 基本命令

`tw` 最主要和最直接的用途是使用预先配置的别名打开 URL。如果运行该命令时不带任何参数，它将显示主帮助信息。

### `tw [alias]`

运行 `tw` 命令并附带一个别名时，它将在你的默认浏览器中打开相应的 URL。

```shell
# 假设 'home' 是 'https://github.com/skypesky' 的别名
tw home
```

## 全局选项

这些选项可用于 `tw` 基本命令。

| 选项 | 描述 |
|---|---|
| `-h`, `--help` | 显示命令的帮助信息。 |
| `-V`, `--version` | 输出 `to-where-cli` 的当前版本号。 |
