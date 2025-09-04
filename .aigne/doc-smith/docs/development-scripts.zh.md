# 可用脚本

`package.json` 文件包含一系列脚本，用于简化常见的开发任务。这些脚本通过 `npm run <script_name>` 执行，涵盖了从构建项目、运行测试到部署应用的全部流程。下文将详细介绍每个可用脚本。

## 核心开发脚本

这些脚本是日常开发工作流的核心。

| 脚本 | 描述 |
|---|---|
| `npm run reinstall` | 删除 `node_modules` 目录并使用 `pnpm` 重新安装所有项目依赖。可用于解决依赖问题。 |
| `npm run clean` | 移除 `dist` 目录，清除上一次构建生成的所有编译文件。 |
| `npm run build` | 使用 `esbuild` 将 `src` 目录中的 TypeScript 源代码编译成 JavaScript 并输出到 `dist` 目录。该脚本会自动先运行 `clean` 脚本。 |
| `npm run build:watch` | 以观察模式启动构建过程。源文件发生变化时，它会自动重新编译项目。 |
| `npm run debug` | 构建项目，然后使用 Node.js 执行主入口文件（`dist/index.js`），以便直接测试 CLI 的行为。 |

## 代码质量与测试

这些脚本有助于维护代码质量，并确保应用程序按预期工作。

| 脚本 | 描述 |
|---|---|
| `npm run lint` | 使用 ESLint 对 `src` 目录下的所有 TypeScript 文件进行代码检查，以发现代码风格和潜在错误。 |
| `npm run lint:fix` | 对代码库进行检查，并自动修复所有可安全修正的问题。 |
| `npm run test` | 使用 Jest 执行完整的测试套件。 |
| `npm run coverage` | 运行测试套件并生成代码覆盖率报告，显示代码被测试覆盖的程度。 |
| `npm run verify` | 一个便捷脚本，同时运行 `lint` 和 `test`。在提交变更前运行此脚本有助于确保代码质量和功能正常。 |

## 部署与版本管理

这些脚本用于部署应用程序和管理其版本号。

| 脚本 | 描述 |
|---|---|
| `npm run deploy` | 执行本地全局部署。它会构建项目，卸载任何已存在的全局 `to-where-cli` 包，然后将当前的本地项目全局安装。这非常适合像用户一样测试最终的构建版本。 |
| `npm run deploy:remote` | 卸载当前的全局版本，并重新安装 npm 注册表上发布的最新版本。这有助于切换回官方发布版本。 |
| `npm run bump-version` | 使用 `ver-bump` 工具增加 `package.json` 中的版本号。 |
| `npm run show:version` | 查询 npm 注册表以显示 `to-where-cli` 的最新发布版本。 |

---

了解这些开发脚本后，你就可以构建、测试并为项目做出贡献。如需查看变更历史和新增功能，请前往 [Changelog](./changelog.md)。