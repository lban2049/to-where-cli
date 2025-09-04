# 基本用法

本指南提供了 `to-where-cli` 核心工作流程的快速教程。你将通过实际的命令行示例，学习如何添加、使用、列出、更新和删除别名。

## 添加别名

最基本的命令是 `add`。它能将一个易于记忆的别名与一个较长的地址（如 URL 或本地目录路径）关联起来。

例如，要为 GitHub 个人资料创建一个名为 `home` 的别名，请运行：

```shell
tw add home https://github.com/skypesky
```

如果运行 `tw add` 时未提供地址，它将默认使用当前工作目录。如果同时也省略了别名，它将使用目录的名称作为别名。

```shell
# 在 /Users/me/my-project 目录下
tw add
# 这等同于：tw add my-project /Users/me/my-project
```

## 通过别名打开地址

设置别名后，只需输入 `tw` 和别名即可打开对应的地址。这将在你的默认浏览器中打开 URL，或在文件浏览器中打开目录。

```shell
tw home
```

## 列出别名

要查看所有已保存别名及其对应地址的列表，请使用 `ls` 或 `list` 命令。

```shell
tw ls
```

你也可以查询特定别名的地址：

```shell
tw ls home
```

## 更新别名

要更新与现有别名关联的地址，只需使用相同的别名和新地址再次运行 `add` 命令。默认情况下，该工具将覆盖旧条目。你也可以使用 `--force` 或 `-f` 标志来显式执行此操作。

```shell
# 此命令将 'home' 别名更新为一个新的 URL
tw add home https://github.com/skypesky/leetcode-for-javascript
```

## 删除别名

你可以使用 `rm` 命令删除一个别名。

要删除一个特定的别名，请将其名称作为参数提供：

```shell
tw rm home
```

如果运行 `tw rm` 时不带任何参数，该工具将启动一个交互式菜单，允许你一次选择多个别名进行删除。

```shell
tw rm
# 这将打开一个交互式提示，让你选择要删除的别名
```

---

现在你已经了解了基本工作流程，可以在 [命令参考](./command-reference.md) 中探索所有可用的命令及其选项。