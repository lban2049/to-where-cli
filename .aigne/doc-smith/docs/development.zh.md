# 开发指南

本指南为希望参与 `to-where-cli` 项目贡献的开发者提供了所有必要信息。内容涵盖了开发环境的搭建、项目架构的理解，以及如何使用可用的脚本来构建、测试和部署该工具。

该项目使用 TypeScript 编写，并采用 esbuild 进行打包、Jest 进行测试、ESLint 保证代码质量等现代化工具。我们欢迎社区贡献，并希望本指南能让整个过程简单明了。

### 快速入门

首先，请从 GitHub 克隆代码仓库并安装所需的依赖项。我们推荐使用 `pnpm` 进行包管理。

```bash
git clone https://github.com/skypesky/to-where-cli.git
cd to-where-cli
npm run reinstall # 使用 pnpm 安装依赖
```

### 核心部分

本指南分为两个主要部分，以帮助你更好地进行开发。通过浏览这些部分，你可以了解代码库和开发工作流程。

<x-cards data-columns="2">
  <x-card data-title="Project Structure" data-icon="lucide:folder-tree" data-href="/development/project-structure">
    概述了项目的源代码布局，解释了 `src`、`dist` 等关键目录和文件的用途，以及各种配置文件的作用。
  </x-card>
  <x-card data-title="Available Scripts" data-icon="lucide:terminal" data-href="/development/scripts">
    `package.json` 中定义的 npm 脚本参考，说明了如何构建、测试、进行代码检查和部署应用程序。
  </x-card>
</x-cards>

### 测试

项目使用 Jest进行测试。相关配置位于 `jest.config.js` 文件中。所有测试文件都存放在 `<rootDir>/tests` 目录下，并遵循 `**/*.spec.ts` 的命名模式。你可以使用以下命令来运行测试套件并生成覆盖率报告：

```bash
# 运行所有测试
npm run test

# 生成覆盖率报告
npm run coverage
```

### 版本控制

版本号的更新由 `ver-bump` 包处理。你可以使用一个专用脚本轻松地递增软件包版本。

```bash
# 更新 package.json 中的版本号
npm run bump-version
```

如需更高级的版本管理功能，请参阅 [`bump` 工具的文档](https://github.com/fabiospampinato/bump)。

---

现在你已经对开发设置有了大致了解，下一步可以深入探究代码库的组织结构。

继续阅读[项目结构](./development-project-structure.md)以了解更多信息。