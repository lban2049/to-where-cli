# 核心命令

核心命令是 `to-where-cli` 的基础，提供了管理目录别名所需的所有工具。你可以使用这些命令来添加、删除、列出和清除快捷方式。

---

## add

`add` 命令为指定的目录路径创建一个新别名。如果未提供路径，则默认为当前工作目录。

### 用法

```bash
tw add [alias] [address]
```

### 参数和选项

| 参数 | 描述 | 是否必需 |
|---|---|---|
| `alias` | 你想创建的别名的名称。如果省略，则使用当前目录的名称。 | 否 |
| `address` | 你想与别名关联的目录路径。如果省略，则使用当前工作目录。 | 否 |
| `-f`, `--force` | 如果存在同名别名，则覆盖现有别名。 | 否 |

### 示例

**1. 为当前目录创建别名**

如果你位于 `/Users/dev/my-project` 目录，此命令将创建一个名为 `my-project` 的别名指向该目录。

```bash
tw add
```

**2. 为特定目录创建命名别名**

```bash
tw add my-app /Users/dev/my-application
```

**3. 覆盖现有别名**

如果别名 `my-app` 已存在，你必须使用 `--force` 标志来更新它。

```bash
tw add my-app /Users/dev/new-path --force
```

如果不使用 `--force` 标志，你将收到一条错误信息：

```
Alias my-app already exists, you can use '-f' or '--force' to overwrite it
```

---

## rm

`rm` 命令用于删除一个或多个别名。

### 用法

```bash
tw rm [alias]
```

### 参数

| 参数 | 描述 | 是否必需 |
|---|---|---|
| `alias` | 要删除的别名的名称。 | 否 |

### 行为

- **带别名：** 如果你提供一个别名，该命令将删除指定的别名。
- **不带别名：** 如果你在不带别名的情况下运行该命令，它将启动一个交互式提示，允许你选择多个别名进行删除。

### 示例

**1. 删除特定别名**

```bash
tw rm my-app
```

预期输出：

```
Alias my-app has been removed
my-app => /Users/dev/new-path => 0
```

**2. 使用交互模式删除别名**

不带任何参数运行该命令以进入选择提示。

```bash
tw rm
```

这将显示一个列表，你可以使用箭头键和空格键选择要删除的别名：

```
? Select the alias to be deleted233
  Instructions: 
    ↑/↓: Highlight option
    ←/→/[space]: Toggle selection
    a: Toggle all
    [enter]: Done
❯ ◯ project-a => /path/to/project-a => 10
  ◯ project-b => /path/to/project-b => 5
  ◯ project-c => /path/to/project-c => 2
```

---

## ls

`ls` 命令（别名为 `list`）显示你已保存的别名、它们对应的路径以及它们的访问次数。

### 用法

```bash
tw ls [alias]
tw list [alias]
```

### 参数

| 参数 | 描述 | 是否必需 |
|---|---|---|
| `alias` | 要显示的特定别名的名称。如果省略，将列出所有别名。 | 否 |

### 示例

**1. 列出所有已保存的别名**

列表按访问次数降序排列。

```bash
tw ls
```

预期输出：

```
project-a => /path/to/project-a => 10
project-b => /path/to/project-b => 5
project-c => /path/to/project-c => 2
```

**2. 显示特定别名**

```bash
tw ls project-b
```

预期输出：

```
project-b => /path/to/project-b => 5
```

---

## clean

`clean` 命令删除所有已保存的别名。此操作不可逆，需要确认标志。

### 用法

```bash
tw clean
```

### 选项

| 参数 | 描述 | 是否必需 |
|---|---|---|
| `-f`, `--force` | 确认删除所有别名的操作。这是一个必需的安全措施。 | 是 |

### 示例

**1. 尝试在不带强制标志的情况下进行清理**

在不带 `--force` 的情况下运行 `clean` 将导致错误，以防止意外数据丢失。

```bash
tw clean
```

预期输出：

```
To make sure you know what you're doing, you must use '-f' or '--force' to empty
```

**2. 清除所有别名**

使用 `--force` 标志继续删除操作。

```bash
tw clean --force
```

执行后，所有别名将被永久删除。