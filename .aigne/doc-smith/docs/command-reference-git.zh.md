# Git 命令

`tw git` 命令提供了一种便捷的方式，可以直接从终端快速打开项目的远程仓库页面。它会自动检测您的远程 Git URL，并在默认的 Web 浏览器中打开相关页面。默认的子命令是 `open`，因此 `tw git` 是 `tw git open` 的别名。

此命令通过从本地 Git 配置中读取远程 origin URL 来工作。然后，它会根据提供的选项为各种仓库页面（例如议题、拉取请求或特定文件）构建相应的 URL。如果未指定任何选项，它会默认打开当前分支的主页面。

## 用法

```bash
tw git [options]
# 或
tw git open [options]
```

## 工作流程

下图说明了 `tw git` 命令如何处理请求并打开相应的仓库页面。

```d2
direction: down

终端: {
  shape: rectangle
  用户: {
    shape: person
  }
  CLI: {
    label: "tw git --issue"
  }
  用户 -> CLI: "执行命令"
}

"to-where-cli": {
  shape: package
  grid-columns: 1

  "Git-Command-Parser": {
    label: "Git 命令解析器"
    shape: rectangle
  }

  "Git-Util": {
    label: "Git 远程 URL 工具"
    shape: rectangle
  }

  "URL-Builder": {
    label: "URL 构建器"
    shape: rectangle
  }

  "System-Open": {
    label: "操作系统打开命令"
    shape: rectangle
  }

  "Git-Command-Parser" -> "Git-Util": "请求远程 URL"
  "Git-Util" -> "Git-Command-Parser": "返回基础 URL"
  "Git-Command-Parser" -> "URL-Builder": "提供基础 URL 和选项"
  "URL-Builder" -> "System-Open": "传递最终 URL"
}

"Local-Filesystem": {
  label: "本地文件系统"
  shape: cylinder
  "git-config": {
    label: ".git/config"
  }
}

浏览器: {
  shape: rectangle
  "GitHub-Issues-Page": {
    label: "GitHub Issues 页面"
  }
}

终端 -> "to-where-cli"."Git-Command-Parser"
"to-where-cli"."Git-Util" -> "Local-Filesystem": "读取配置"
"to-where-cli"."System-Open" -> 浏览器: "打开 URL"
```

## 选项

| 选项 | 别名 | 描述 |
|---|---|---|
| `--actions` | `-a` | 打开仓库的 Actions 页面。 |
| `--author` | | 打开上一次提交作者的个人资料页面。 |
| `--branch [branch]` | `-b` | 打开指定分支页面。如果未提供分支名称，则默认为当前分支。 |
| `--commit [hash]` | `-c` | 打开指定提交页面。如果未提供哈希值，则默认为最新提交。 |
| `--committer` | | 打开上一次提交的提交者的个人资料页面。 |
| `--file <filePath>` | `-f` | 打开仓库中特定文件的页面。 |
| `--find` | | 打开当前分支的文件搜索页面。 |
| `--first-commit` | | 打开仓库的首次提交页面。 |
| `--issue` | `-i` | 打开议题列表页面。 |
| `--main` | `-m` | 打开仓库主页面（根目录）。 |
| `--pull-request` | `-p` | 打开拉取请求列表页面。 |
| `--pull [branch]` | | 打开创建新拉取请求的页面。源分支默认为当前分支。 |
| `--release` | `-r` | 打开发布页面。 |
| `--settings` | `-s` | 打开仓库设置页面。 |
| `--star` | | 打开 stargazers 页面。 |

## 示例

### 打开当前分支页面

如果您在名为 `feature/new-ui` 的分支上，运行不带任何选项的命令将打开该分支的页面。

```bash
tw git
```

### 打开议题列表

快速导航到仓库的议题页面。

```bash
tw git --issue
# 或使用别名
tw git -i
```

### 创建新的拉取请求

此命令会在浏览器中打开“新建拉取请求”页面，并使用当前分支预填充源分支。

```bash
tw git --pull
```

为拉取请求指定一个不同的源分支：

```bash
tw git --pull my-feature-branch
```

### 打开特定文件

在仓库的默认分支上查看特定文件。

```bash
tw git -f "src/cli/git/open.ts"
```

### 查看特定提交

提供一个提交哈希值以直接打开其详情页面。

```bash
tw git -c a1b2c3d4e5f6
```

---

`git` 命令通过减少手动导航仓库网站的需要来简化您的开发工作流程。有关从终端执行的其他直接操作，请参阅 [搜索命令](./command-reference-search.md)。