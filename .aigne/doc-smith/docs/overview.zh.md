# 概述

`to-where-cli` 是一个命令行工具，旨在通过将冗长、难记的 URL 替换为简单、直观的别名来简化您的工作流程。它允许您直接从终端快速打开项目仓库、文档和搜索页面，从而节省您的时间和精力。

您无需再手动浏览浏览器书签或输入复杂的网址，只需使用一个简短的命令即可立即到达您需要去的地方。

```d2
direction: down

"Developer": {
  shape: person
}

"Terminal": {
  shape: rectangle
  "tw home": "用户输入一个简短的别名"
}

"to-where-cli": {
  shape: package
  "Alias Lookup": "将 'home' 解析为其完整的 URL"
}

"Default Browser": {
  shape: rectangle
  "打开解析后的 URL"
}

"Developer" -> "Terminal": "1. 执行命令"
"Terminal" -> "to-where-cli": "2. 调用 CLI"
"to-where-cli" -> "Default Browser": "3. 启动 URL"
```

## 主要特性

<x-cards data-columns="3">
  <x-card data-title="轻松管理别名" data-icon="lucide:bookmark-plus">
    直接从命令行创建、列出、更新和删除任何 URL 的简单别名。
  </x-card>
  <x-card data-title="快速 GitHub 导航" data-icon="lucide:github">
    即时打开 git 仓库的特定页面，例如 issues、pull requests 或项目主页。
  </x-card>
  <x-card data-title="集成搜索快捷方式" data-icon="lucide:search">
    无需先打开浏览器，即可直接在 npm、GitHub、Google、Bing 和 Baidu 上执行搜索。
  </x-card>
</x-cards>

## 支持的平台

该 CLI 目前在以下操作系统上得到支持和测试：

- macOS
- Windows

## 后续步骤

准备好开始了吗？请前往 [安装](./getting-started-installation.md) 指南，在您的系统上设置 `to-where-cli` 并创建您的第一个别名。