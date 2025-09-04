# 项目结构

本文档概述了 `to-where-cli` 源代码的布局。对于希望为项目做出贡献或了解其内部工作原理的开发者来说，理解该结构至关重要。

该项目遵循模块化结构，将命令行界面、核心业务逻辑、数据协议和元数据定义等不同职责的内容分离到独立的目录中。

### 宏观概览

下图展示了 `src` 文件夹内的主要目录及其主要关系。

```d2
direction: down

src-cli: {
  label: "src/cli\n(入口点)"
  shape: rectangle
}

src-classes: {
  label: "src/classes\n(核心逻辑与实现)"
  shape: rectangle
}

src-protocol: {
  label: "src/protocol\n(数据契约/接口)"
  shape: rectangle
}

src-meta: {
  label: "src/meta\n(数据结构)"
  shape: rectangle
}

src-cli -> src-classes: "初始化程序"
src-classes -> src-protocol: "实现协议"
src-protocol -> src-meta: "使用数据结构"
```

### 目录详解

以下是每个关键目录及其用途的详细说明。

| Directory      | Description                                                                                                                                                                                                                                                        |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `src/cli`      | 这是 CLI 的可执行入口点。`index.ts` 文件负责初始化和解析在 `classes` 目录中定义的命令。                                                                                             | 
| `src/classes`  | 包含核心应用程序逻辑。该目录存放了用于命令创建 (`create-program`)、配置处理 (`simple-config`) 和别名操作 (`simple-worker`) 的具体实现。                                                  |
| `src/protocol` | 定义作为核心组件契约的 TypeScript 接口。例如，`ConfigProtocol` 指定了管理配置数据所需的所有方法，而 `WorkerProtocol` 定义了与别名相关的操作方法。这种分离使得测试和维护更加容易。 |
| `src/meta`     | 存放了整个应用程序中使用的主要数据结构的定义，例如 `Point`（表示一个别名）和 `Config`。这些文件确保了不同模块之间的数据一致性。                                                 |

通过以这种方式组织代码，CLI 的面向用户的部分与底层的业务逻辑和数据管理解耦，使得代码库更清晰、更具可扩展性。

### 后续步骤

了解项目布局后，您可以通过阅读 [Available Scripts](./development-scripts.md) 文档来学习如何构建、测试和运行该应用程序。