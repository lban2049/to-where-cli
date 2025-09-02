# 安装

在开始使用 `to-where-cli` 之前，您需要先在系统上安装它。该工具以 npm 包的形式分发，安装过程简单直接。

## 前提条件

请确保您的电脑上已安装 Node.js 和 npm (Node Package Manager)。`to-where-cli` 目前支持以下操作系统：

- macOS
- Windows

## 通过 npm 安装

要使 `tw` 命令在终端的任何目录中都可用，您应该使用 `-g` 标志进行全局安装。

打开终端并运行以下命令：

```shell
npm install -g to-where-cli
```

该命令会从 npm 仓库获取该软件包，并将其全局安装到您的系统中。

## 验证安装

安装完成后，您可以运行帮助命令来验证 `to-where-cli` 是否已准备就绪：

```shell
tw -h
```

如果安装成功，该命令将显示帮助菜单，其中列出了所有可用的命令和选项。

---

既然您已经安装了 `to-where-cli`，就可以开始了解其核心功能。请继续阅读 [基本用法](./getting-started-basic-usage.md) 指南来创建您的第一个别名。