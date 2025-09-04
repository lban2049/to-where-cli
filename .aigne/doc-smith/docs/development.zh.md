# 开发指南

欢迎阅读 `to-where-cli` 的开发指南。本文档为任何希望为该项目做出贡献的人提供了必要信息。在这里，你将找到有关项目架构以及构建、测试和管理应用程序所需脚本的详细信息。

首先，请克隆本仓库并安装所需依赖：

```bash
git clone https://github.com/skypesky/to-where-cli.git
cd to-where-cli
pnpm install
```

本指南分为以下几个部分，以帮助你更好地了解开发流程：

<x-cards>
  <x-card data-title="项目结构" data-icon="lucide:folder-tree" data-href="/development/project-structure">
    了解源代码的布局概览，其中解释了关键目录和配置文件（如 tsconfig.json 和 jest.config.js）的用途。
  </x-card>
  <x-card data-title="可用脚本" data-icon="lucide:terminal" data-href="/development/scripts">
    在此可找到用于代码检查、测试、构建和部署应用程序的 npm 脚本的完整参考，这些脚本均定义在 package.json 中。
  </x-card>
</x-cards>

### 版本控制

本项目的版本管理通过 `ver-bump` 进行。你可以使用 `bump-version` 脚本来增加软件包版本：

```bash
npm run bump-version
```

该命令简化了根据语义化版本规范在 `package.json` 中更新版本号的流程。

---

熟悉项目设置后，下一步可以探索现有功能。请前往[命令参考](./command-reference.md)查看完整的命令及其选项列表。