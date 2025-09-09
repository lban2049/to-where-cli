# 基本用法

安装 `to-where-cli` 后，你就可以通过几个简单的命令来管理你的地址别名。本指南将引导你完成核心工作流程：添加、打开、列出、更新和删除别名。

### 添加别名

要保存新地址，请使用 `tw add` 命令。你需要提供一个简短、易记的 `alias` 和你想要保存的完整 `address`。

```shell
tw add home https://github.com/skypesky
```

**专业提示：** 如果你运行 `tw add` 时未提供地址，它将使用你当前的工作目录。如果你同时也省略了别名，它将使用目录名作为别名。

```shell
# 在 /Users/dev/my-project 文件夹中
tw add my-proj # 为当前目录创建别名 'my-proj'

# 在 /Users/dev/my-project 文件夹中
tw add # 为当前目录创建别名 'my-project'
```

### 通过别名打开地址

要在默认浏览器中打开已保存的地址，只需输入 `tw` 并后跟别名即可。

```shell
tw home
```

该命令将打开 `https://github.com/skypesky`。

### 列出别名

如果你忘记了某个别名，可以使用 `tw ls` 命令（或其完整版本 `tw list`）列出所有已保存的别名及其对应的地址。

```shell
# 列出所有已保存的别名
tw ls
```

你也可以查询特定别名的地址。

```shell
# 显示 'home' 别名的地址
tw ls home
```

### 更新别名

要更新与现有别名关联的地址，只需使用相同的别名和新地址再次运行 `tw add` 命令即可。这将覆盖之前的条目。

```shell
tw add home https://github.com/skypesky/to-where-cli
```

如果你想明确表示要进行覆盖操作，可以使用 `--force` 或 `-f` 标志。

### 删除别名

要删除不再需要的别名，请使用 `tw rm` 命令并后跟别名。

```shell
tw rm home
```

如果你在运行 `tw rm` 时未指定别名，该工具将进入交互模式，允许你从所有已保存的条目列表中选择多个别名进行删除。

### 获取帮助

要获取完整的命令和选项列表，可以随时使用帮助标志。

```shell
tw -h
```

既然你已掌握了基础知识，就可以在 [命令参考](./command-reference.md) 中探索所有可用的命令及其选项了。