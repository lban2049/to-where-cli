# 概述

`to-where-cli` 是一个命令行实用工具，旨在简化从终端访问网页地址的过程。它通过一个直观的别名系统，让你能够使用简短、易记的命令来打开冗长、复杂或常用的 URL。这对于需要定期访问特定 GitHub 仓库、搜索包注册中心或使用各种搜索引擎的开发者尤其有用。

你无需记住并输入 `https://github.com/skypesky/to-where-cli`，只需创建一个别名并运行 `tw to-where` 即可。

```d2
direction: down

Terminal: {
  shape: rectangle

  User: {
    shape: person
  }

  CLI-Input: {
    label: "用户输入 `tw home`"
    shape: rectangle
  }

  User -> CLI-Input
}

to-where-cli: {
  shape: package
  
  Alias-Lookup: {
    label: "1. 查找别名 'home'"
    shape: rectangle
  }
  
  URL-Retrieval: {
    label: "2. 检索存储的 URL"
    shape: rectangle
  }
  
  Open-Command: {
    label: "3. 发出系统 'open' 命令"
    shape: rectangle
  }

  Alias-Lookup -> URL-Retrieval -> Open-Command
}

Browser: {
  shape: rectangle
  label: "默认网络浏览器"
}

Terminal -> to-where-cli: "执行"
to-where-cli -> Browser: "启动 URL"
```

## 主要特性

<x-cards data-columns="3">
  <x-card data-title="别名管理" data-icon="lucide:bookmark-plus">
    为任意 URL 创建、列出、更新和移除短别名。使用简单的命令即可打开网站，无需输入或粘贴完整地址。
  </x-card>
  <x-card data-title="Git 仓库快捷方式" data-icon="lucide:git-branch">
    无需完整 URL，即可直接跳转到 Git 仓库的特定页面，如 issues、pull requests 或项目主页。
  </x-card>
  <x-card data-title="直接网页搜索" data-icon="lucide:search">
    直接从命令行在 Google、Bing、百度、npm 和 GitHub 等常用网站上进行搜索，并在浏览器中打开搜索结果页面。
  </x-card>
</x-cards>

## 支持的平台

该工具目前支持以下操作系统：

- macOS
- Windows

---

准备好简化你的工作流程了吗？请前往 [入门指南](./getting-started.md) 安装此命令行工具并创建你的第一个别名。