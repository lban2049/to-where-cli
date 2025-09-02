# 开发指南

欢迎阅读 `to-where-cli` 开发指南。本节提供了搭建本地环境、理解项目架构以及有效贡献所需的所有信息。该项目使用 TypeScript 构建，并在 Node.js 上运行。

## 搭建环境

在开始之前，请确保已安装最新版本的 Node.js 和 pnpm 包管理器。

1.  **克隆仓库**

    首先，将项目仓库从 GitHub 克隆到本地计算机：

    ```bash
    git clone https://github.com/skypesky/to-where-cli.git
    cd to-where-cli
    ```

2.  **安装依赖**

    该项目使用 pnpm 管理依赖。在项目根目录中运行以下命令进行安装：

    ```bash
    pnpm install
    ```

## 快速入门

环境搭建完成后，您就可以开始探索代码库和开发脚本了。以下指南提供了详细信息，可帮助您快速入门。

<x-cards data-columns="2">
  <x-card data-title="项目结构" data-icon="lucide:folder-tree" data-href="/development/project-structure">
    项目源代码布局概览，解释了 `src`、`dist` 等关键目录以及配置文件的用途。
  </x-card>
  <x-card data-title="可用脚本" data-icon="lucide:terminal" data-href="/development/scripts">
    `package.json` 中定义的 npm 脚本的完整参考，解释了如何构建、测试、检查和部署应用程序。
  </x-card>
</x-cards>

## 通用开发工作流

典型的工作流包括在 `src` 目录中修改源代码，然后使用提供的 npm 脚本来构建和测试您的更改。

-   **构建：** 使用 `pnpm build` 编译 TypeScript 源代码。
-   **测试：** 使用 `pnpm test` 运行完整的测试套件。
-   **代码检查：** 使用 `pnpm lint` 检查代码质量和风格问题。

有关所有命令的完整列表和详细说明，请参阅[可用脚本](./development-scripts.md)文档。

---

搭建好环境后，我们建议您深入研究[项目结构](./development-project-structure.md)以了解代码的组织方式。之后，[可用脚本](./development-scripts.md)指南将成为您日常开发的主要参考。