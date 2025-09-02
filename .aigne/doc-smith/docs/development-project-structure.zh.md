# 项目结构

本文档概述了 `to-where-cli` 的源代码布局。对于希望为项目做贡献或了解其内部工作原理的开发者而言，理解项目结构至关重要。

该代码库的组织旨在实现关注点分离，为命令行界面、核心业务逻辑、数据契约（协议）和数据模型（元）设立了不同的目录。

### 架构概述

下图展示了应用程序主要组件的高层结构及其相互关系。

```d2
direction: down

"src": {
  shape: package

  "cli/": {
    label: "CLI 层"
    tooltip: "处理命令行交互"
    "index.ts": "CLI 入口点"
  }

  "classes/": {
    label: "业务逻辑层"
    tooltip: "实现核心功能"
    "create-program.ts": "构建命令结构"
    "simple-config.ts": "管理配置"
    "simple-worker.ts": "执行别名任务"
  }

  "protocol/": {
    label: "契约层"
    tooltip: "为服务定义接口"
    "config.protocol.ts": "IConfig 接口"
    "worker.protocol.ts": "IWorker 接口"
  }

  "meta/": {
    label: "数据模型层"
    tooltip: "定义核心数据结构"
    "config.meta.ts": "Config 类型"
    "point.meta.ts": "Point 类型"
  }
}

"src.cli/" -> "src.classes/": "初始化并运行程序"
"src.classes/" -> "src.protocol/": "实现契约"
"src.protocol/" -> "src.meta/": "使用数据模型"

```

### 关键目录和文件

以下是 `src` 文件夹中每个主要目录和文件的用途详解。

| Path | Description |
|---|---|
| `src/cli/index.ts` | 可执行 CLI 的主入口点。它使用 `#! /usr/bin/env node` shebang，使其可以从命令行运行。其主要作用是实例化并运行 `create-program.ts` 中定义的程序。 |
| `src/classes/` | 此目录包含应用程序核心逻辑的具体实现。例如，`SimpleConfig` 负责读写配置文件，`SimpleWorker` 负责执行添加或打开别名等操作。 |
| `src/protocol/` | 包含为系统不同部分定义契约的 TypeScript 接口。例如，`ConfigProtocol` 定义了任何配置管理器都必须实现的所有方法。这种方法实现了实现与接口的解耦。 |
| `src/meta/` | 此目录存放整个应用程序使用的核心数据结构和类型定义，例如 `Point` 和 `Config`。集中管理这些模型可确保数据一致性。 |
| `src/index.ts` | 如果该模块要用作另一个项目中的库，此文件是其主入口点。它导出了主要的类和功能。 |

通过这种代码组织方式，项目在面向用户的 CLI、底层业务逻辑及其操作的数据之间保持了清晰的分离。

既然您已了解项目布局，便可以探索可用的开发脚本来构建、测试和运行应用程序。更多详情请参阅 [可用脚本](./development-scripts.md) 指南。