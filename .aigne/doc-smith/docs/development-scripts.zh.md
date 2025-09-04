# 可用脚本

`package.json` 文件包含一系列脚本，用于辅助开发工作流程，涵盖从本地运行应用程序到构建、测试和部署的各个环节。你可以使用 `npm run <script-name>` 从项目根目录执行这些脚本。

以下是所有可用脚本及其功能的完整列表。

### 开发与工作流

| Script | Description |
|---|---|
| `reinstall` | 删除 `node_modules` 目录并重新安装所有依赖项，以实现全新设置。 |
| `debug` | 直接使用 Node.js 运行已编译的应用程序。此脚本用于调试构建后的输出，并会自动在其之前执行构建步骤。 |
| `build:watch` | 以监视模式运行构建过程，每当源文件发生更改时，都会自动重新编译代码。 |

### 代码质量与测试

| Script | Description |
|---|---|
| `lint` | 使用 ESLint 分析 `src` 目录中的 TypeScript 源代码，检查代码风格和质量问题。 |
| `lint:fix` | 运行 linter 并自动修复所有可修复的问题。 |
| `test` | 使用 Jest 执行测试套件。 |
| `coverage` | 运行测试套件并生成代码覆盖率报告。 |
| `verify` | 一个质量检查脚本，会运行 linter 和整个测试套件。 |

### 构建与部署

| Script | Description |
|---|---|
| `clean` | 移除 `dist` 目录，清除所有已编译的文件。 |
| `build` | 使用 esbuild 将 TypeScript 源代码编译为 JavaScript，并将其输出到 `dist` 目录。该步骤会自动在其之前执行 `clean` 步骤。 |
| `deploy` | 执行本地部署。它会构建项目，卸载任何已存在的全局版本，然后在全局范围内安装当前的本地版本。这对于 CLI 的端到端测试非常有用。 |
| `deploy:remote` | 卸载当前的全局版本，并从官方 npm 仓库重新安装最新版本。 |

### 版本控制

| Script | Description |
|---|---|
| `bump-version` | 使用 `ver-bump` 工具增加 `package.json` 文件中的包版本号。 |
| `show:version` | 获取并显示在 npm 上发布的 `to-where-cli` 包的最新版本号。 |

---

熟悉这些脚本后，你可能希望通过阅读 [项目结构](./development-project-structure.md) 文档来了解更多关于项目布局的信息。