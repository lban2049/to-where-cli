# 概述

`to-where-cli` 是一款命令行工具，旨在通过别名机制简化你的工作流程，让你能轻松打开那些晦涩难记的 URL。它能帮助你直接从终端快速访问各种地址，无论是 GitHub 仓库，还是 npm、Google 等网站的搜索页面。

### 核心概念

该工具的工作原理是将一个简单易记的别名映射到一个复杂的 URL。设置别名后，你便可以使用 `tw` 命令在默认浏览器中打开对应的地址。

```d2
direction: right

用户: {
  shape: person
}

"命令行工具：to-where-cli": {
  shape: rectangle
}

"URL：网站/搜索页面": {
  shape: cloud
}

用户 -> "命令行工具：to-where-cli": "执行命令 (例如 'tw home')"
"命令行工具：to-where-cli" -> "URL：网站/搜索页面": "解析别名并在浏览器中打开 URL"
```

### 主要功能

`to-where-cli` 提供了多种功能，可简化你的命令行导航操作。

<x-cards data-columns="3">
  <x-card data-title="别名管理" data-icon="lucide:link">
    为任意 URL 创建、列出、更新和删除自定义别名，让你能轻松访问冗长复杂的地址。
  </x-card>
  <x-card data-title="Git 集成" data-icon="lucide:github">
    直接打开 Git 仓库的特定页面，如 issues、pull requests 或项目主页。
  </x-card>
  <x-card data-title="快速搜索" data-icon="lucide:search">
    无需预先打开浏览器，直接跳转到 npm、GitHub、Google、Bing、Baidu 等平台的搜索结果页面。
  </x-card>
</x-cards>

### 支持平台

`to-where-cli` 目前官方支持以下操作系统：

- macOS
- Windows

### 下一步

准备好简化你的 URL 管理了吗？请根据安装指南开始使用。

<x-card data-title="开始使用" data-icon="lucide:rocket" data-href="/getting-started/installation" data-cta="安装命令行工具">
  面向新用户的分步指南，指导他们安装命令行工具并学习别名管理的基础命令。
</x-card>