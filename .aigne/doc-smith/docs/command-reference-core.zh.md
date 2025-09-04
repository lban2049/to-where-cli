# 核心命令

核心命令是 `to-where-cli` 的基础，为管理目录别名提供了必要的工具。本节为添加、删除、列出和清空别名提供了详细参考。

---

## add

`add` 命令用于为指定的目录路径创建一个新别名。如果未提供别名或地址，则默认使用当前工作目录。

### 用法

```bash
tw add [alias] [address] [options]
```

### 参数和选项

| Parameter | Description                                                                                    | Required |
| :-------- | :--------------------------------------------------------------------------------------------- | :------- |
| `[alias]`   | 为地址指定的名称。如果省略，则使用当前目录的名称。           | 否       |
| `[address]` | 要创建别名的目录路径。如果省略，则使用当前工作目录 (`cwd`)。     | 否       |
| `-f, --force` | 覆盖同名的现有别名。若不使用此标志，当别名已存在时，命令将会执行失败。 | 否       |

### 示例

**1. 为指定路径创建别名：**

该命令会创建一个名为 `docs` 的别名，指向 `~/documents/work`。

```bash
tw add docs ~/documents/work
```

**2. 为当前目录创建别名：**

如果你已在目标目录中，可以省略 `address` 参数。

```bash
cd ~/projects/my-app
tw add my-app
```

**3. 使用默认值创建别名：**

如果 `alias` 和 `address` 均被省略，命令将使用当前目录的名称作为别名，并使用其路径作为地址。

```bash
cd ~/projects/website
tw add
# 该操作会创建一个名为 'website' 的别名，指向当前路径。
```

**4. 覆盖现有别名：**

使用 `-f` 或 `--force` 标志更新现有别名，使其指向新地址。

```bash
tw add docs ~/documents/personal -f
```

---

## rm

`rm` 命令用于从配置中删除一个或多个别名。

### 用法

```bash
tw rm [alias]
```

### 参数

| Argument | Description                                                                                                                   | Required |
| :------- | :---------------------------------------------------------------------------------------------------------------------------- | :------- |
| `[alias]`  | 要删除的别名。如果省略，将出现一个交互式提示，允许你选择多个别名进行删除。 | 否       |

### 示例

**1. 删除特定别名：**

```bash
tw rm docs
```

**2. 以交互方式删除多个别名：**

在不带别名参数的情况下运行该命令，将启动一个交互式多选菜单。使用方向键导航，使用空格键选择，按回车键确认。

```bash
tw rm
```

执行后，你将看到类似如下的提示：

```
? Select the alias to be deleted233 (Press <space> to select, <a> to toggle all, <i> to invert selection)
❯ ◯ my-app => /Users/user/projects/my-app => 15
  ◯ website => /Users/user/projects/website => 10
  ◯ docs => /Users/user/documents/personal => 5
```

---

## ls (或 list)

`ls` 命令（别名为 `list`）会显示已保存的别名、其对应的路径以及使用频率计数。列表按访问次数降序排列。

### 用法

```bash
tw ls [alias]
```

### 参数

| Argument | Description                                                        | Required |
| :------- | :----------------------------------------------------------------- | :------- |
| `[alias]`  | 要显示的特定别名的名称。如果省略，则列出所有别名。 | 否       |

### 示例

**1. 列出所有别名：**

```bash
tw ls
```

输出示例：
```
my-app => /Users/user/projects/my-app => 15
website => /Users/user/projects/website => 10
docs => /Users/user/documents/personal => 5
```

**2. 显示特定别名的详细信息：**

```bash
tw ls my-app
```

输出示例：
```
my-app => /Users/user/projects/my-app => 15
```

---

## clean

`clean` 命令会永久删除所有已保存的别名。这是一个破坏性操作，需要确认标志以防止意外的数据丢失。

### 用法

```bash
tw clean [options]
```

### 选项

| Option        | Description                                       | Required |
| :------------ | :------------------------------------------------ | :------- |
| `-f, --force` | 确认删除所有别名的操作。此标志是执行该命令所必需的。 | 是      |

### 示例

**1. 在未确认的情况下尝试清空：**

在没有 `--force` 标志的情况下运行 `tw clean` 将会返回一条错误信息，以确保你了解此操作的后果。

```bash
tw clean
# 输出：为确保你知晓正在进行的操作，必须使用 '-f' 或 '--force' 才能清空
```

**2. 清空所有别名：**

要继续删除所有别名，请使用 `--force` 标志。

```bash
tw clean --force
# 所有别名都将被删除。
```