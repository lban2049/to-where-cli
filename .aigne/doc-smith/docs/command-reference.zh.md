# 命令参考

`to-where-cli` 工具（别名为 `tw`）提供了一套命令，可用于直接在终端中管理 URL 别名和执行快速搜索。使用该 CLI 的通用结构是 `tw [subcommand] [arguments]`。

本节是所有可用命令的综合指南。下面是命令结构的概览。

```d2
direction: down

"tw": {
  shape: cloud
  "核心别名命令": {
    "add": "添加或更新别名"
    "rm": "移除别名"
    "ls": "列出所有别名"
    "clean": "移除无效别名"
  }

  "Git 集成": {
    "git": "打开仓库页面（issues、PR 等）"
  }

  "网页搜索": {
    "npm": "在 npmjs.com 上搜索"
    "github": "在 GitHub 上搜索"
    "google": "在 Google 上搜索"
    "bing": "在 Bing 上搜索"
    "baidu": "在百度上搜索"
  }
}
```

要获取每个命令的详细信息（包括所有可用选项和使用示例），请浏览下方的相关章节。

<x-cards data-columns="3">
  <x-card data-title="核心命令" data-icon="lucide:box" data-href="/command-reference/core">
    管理您的 URL 别名。包括 `add`、`rm`、`ls` 和 `clean` 等命令，用于创建、删除和列出您的快捷方式。
  </x-card>
  <x-card data-title="Git 命令" data-icon="lucide:git-branch" data-href="/command-reference/git">
    使用 `git` 子命令快速访问 Git 仓库的各个页面，例如 issues、pull requests 和 actions。
  </x-card>
  <x-card data-title="搜索命令" data-icon="lucide:search" data-href="/command-reference/search">
    直接在终端中对热门网站进行搜索。支持的命令包括 `npm`、`github`、`google`、`bing` 和 `baidu`。
  </x-card>
</x-cards>

每个子命令都有其特定的选项和参数。点击上方的卡片即可导航至每个命令组的详细文档。