# 项目结构

欢迎阅读 `to-where-cli` 开发指南！对于任何希望参与贡献或仅仅想了解其工作原理的人来说，清晰地理解项目结构至关重要。本文档对源代码布局进行了高层次的概述，解释了每个关键目录和文件的用途。

该项目通过分离关注点进行组织，使代码库模块化且更易于维护。核心逻辑分为数据结构 (`meta`)、合约 (`protocol`) 及其具体实现 (`classes`)，然后由命令行界面 (`cli`) 使用。

## 高层次概述

下图展示了 `src` 文件夹内的主要目录及其依赖关系。流程通常从命令行入口点向下延伸至核心数据定义。

```d2
direction: down

cli: {
  label: "cli\n（入口点）"
  shape: rectangle
}

classes: {
  label: "classes\n（实现）"
  shape: rectangle
}

protocol: {
  label: "protocol\n（接口）"
  shape: rectangle
}

meta: {
  label: "meta\n（数据结构）"
  shape: rectangle
}

cli -> classes: "使用"
classes -> protocol: "实现"
protocol -> meta: "使用"
classes -> meta: "使用"
```

## 目录详解

以下是 `src` 文件夹内主要目录的详细说明。

### `src/cli`

这是命令行界面的主入口点。它负责解析命令行参数并执行相应的操作。

| 文件 | 描述 |
|---|---|
| `index.ts` | 启动并运行 CLI 程序的可执行脚本。它使用 `classes` 目录中的 `createProgram` 工厂来初始化命令结构。 |

### `src/classes`

该目录包含应用程序核心逻辑和协议的具体实现。这些类处理管理别名和配置的实际工作。

| 文件 | 描述 |
|---|---|
| `create-program.ts` | 一个工厂函数，负责设置命令结构，定义所有可用命令及其选项和参数。 |
| `simple-worker.ts` | 实现 `WorkerProtocol`，用于处理核心业务逻辑，如添加、删除和列出别名。 |
| `simple-config.ts` | 实现 `ConfigProtocol`，用于与配置文件进行所有交互，例如读取、写入和更新别名数据。 |
| `open.ts` | 包含用于打开与给定别名关联的 URL 或路径的逻辑。 |

### `src/protocol`

该目录定义了系统不同部分的合约或接口。使用协议可以实现组件之间的松耦合，并使代码库更易于测试和扩展。

| 文件 | 描述 |
|---|---|
| `worker.protocol.ts` | 定义 `WorkerProtocol` 接口，该接口指定了所有核心别名操作（`open`、`add`、`delete`、`list`、`clean`）的方法。 |
| `config.protocol.ts` | 定义 `ConfigProtocol` 接口，用于与配置存储进行交互，包括 `get`、`set`、`add` 和 `find` 等方法。 |

### `src/meta`

该目录包含整个应用程序中使用的核心数据结构和 TypeScript 类型定义。这些文件确保了不同模块之间的数据一致性。

| 文件 | 描述 |
|---|---|
| `point.meta.ts` | 定义 `Point` 类型，它代表一个包含别名及其路径的单一别名记录。 |
| `config.meta.ts` | 定义 `Config` 类型，它代表主配置文件的整体结构。 |

---

现在您已经了解了项目的布局，下一步是学习用于构建、测试和运行应用程序的开发脚本。请继续阅读 [可用脚本](./development-scripts.md) 部分。