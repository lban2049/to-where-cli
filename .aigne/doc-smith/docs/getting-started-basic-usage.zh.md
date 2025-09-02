# 基本用法

本指南将简要介绍 `to-where-cli` 的核心工作流程。你将通过实际示例学习如何添加、使用、列出、更新和移除别名。

### 添加别名

首先，你需要将别名与地址（如 URL 或本地文件路径）进行关联。`tw add` 命令用于执行此操作。

例如，为 GitHub 个人资料创建一个名为 `home` 的快捷方式：

```shell
tw add home https://github.com/skypesky
```

如果在运行 `tw add` 时未指定别名或地址，它将使用当前工作目录作为地址，并使用目录的名称作为别名。

```shell
# 在名为 'my-project' 的项目文件夹中
tw add
# 这会创建一个指向当前目录路径的别名 'my-project'。
```

### 通过别名打开地址

设置别名后，只需输入 `tw` 和别名即可打开对应的地址。

```shell
# 这将在你的默认浏览器中打开 https://github.com/skypesky
tw home
```

### 列出别名

要查看所有已保存别名及其对应地址的列表，请使用 `tw ls` 命令。

```shell
# 列出所有已保存的别名
tw ls
```

你也可以查询特定别名的地址：

```shell
# 显示与 'home' 别名关联的地址
tw ls home
```

### 更新别名

要更新别名，只需使用相同的别名和新地址再次运行 `add` 命令。此操作将覆盖之前的条目。

```shell
# 将 'home' 别名更新为指向另一个仓库
tw add home https://github.com/skypesky/leetcode-for-javascript
```

如果你需要覆盖现有别名且无需任何提示，可以使用 `--force` 或 `-f` 标志。

```shell
tw add home https://github.com/skypesky/new-repo --force
```

### 移除别名

当你不再需要某个别名时，可以使用 `tw rm` 命令将其移除。

```shell
# 移除 'home' 别名
tw rm home
```

如果在运行 `tw rm` 时未指定别名，程序将启动一个交互式菜单，你可以从中选择一个或多个要删除的别名。

```shell
# 以交互模式运行，选择要删除的别名
tw rm
```

以上涵盖了管理快捷方式的基本操作。如需查看完整的命令列表及其所有可用选项，请参阅 [命令参考](./command-reference.md)。