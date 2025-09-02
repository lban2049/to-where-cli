# Git 命令

`tw git` 命令提供了一种便捷的方式，让你可以直接在终端中快速打开项目托管的 Git 仓库（如 GitHub、GitLab 等）的各种页面。它会读取你本地仓库的远程 URL，并为 issues、pull requests 和特定分支等常见目标构建正确的地址。

这让你无需在浏览器中手动查找仓库并浏览其界面。

## 工作原理

该命令遵循一个简单的流程来打开正确的网页：

```d2
direction: down
shape: sequence_diagram

开发者
终端
"to-where-cli"
"Git 主机 (例如 GitHub)"

开发者 -> 终端: "运行 `tw git --issue`"
终端 -> "to-where-cli": "执行命令"
"to-where-cli" -> "to-where-cli": "读取 .git/config 查找远程 URL"
"to-where-cli" -> "to-where-cli": "构建 URL: https://github.com/user/repo/issues"
"to-where-cli" -> "Git 主机 (例如 GitHub)": "在默认浏览器中打开 URL"

```

## 用法

`git` 是默认子命令，因此你可以使用 `tw git [options]`。

```bash
tw git [options]
```

如果未提供任何选项，该命令将默认打开仓库当前分支的主页。

## 选项

以下是 `tw git` 命令所有可用选项的完整列表：

| 选项 | 别名 | 描述 |
|---|---|---|
| `--actions` | `-a` | 打开仓库的 Actions/CI 页面。 |
| `--author` | | 打开最后一次提交的作者的个人主页。 |
| `--branch [branch]` | `-b` | 打开指定分支的页面。如果省略 `[branch]`，则默认为当前分支。 |
| `--commit [hash]` | `-c` | 打开指定提交的页面。如果省略 `[hash]`，则默认为最新一次提交。 |
| `--committer` | | 打开最后一次提交的提交者的个人主页。 |
| `--file <filePath>` | `-f` | 在当前分支中打开指定文件的页面。 |
| `--find` | | 打开当前分支的文件搜索页面。 |
| `--first-commit` | | 打开仓库历史记录中第一次提交的页面。 |
| `--issue` | `-i` | 打开 issues 列表页面。 |
| `--main` | `-m` | 打开仓库默认分支的主页。 |
| `--pull-request` | `-p` | 打开 pull request 列表页面。 |
| `--pull [branch]` | | 打开创建新 pull request 的页面。如果未指定 `[branch]`，则默认为当前分支。 |
| `--release` | `-r` | 打开 releases 页面。 |
| `--settings` | `-s` | 打开仓库设置页面。 |
| `--star` | | 打开仓库的 stargazers 页面。 |

## 示例

### 打开当前分支

打开当前工作分支的仓库页面。如果未提供任何选项，则这是默认操作。

```bash
tw git
```

### 打开 Issues 页面

直接跳转到仓库的 issues 列表。

```bash
tw git -i
```

### 打开 Pull Requests

打开所有 pull request 的列表。

```bash
tw git -p
```

### 创建新的 Pull Request

打开创建新 pull request 的页面，并将当前分支作为头部分支。

```bash
tw git --pull
```

### 查看特定提交

打开特定提交哈希值的页面。

```bash
tw git -c a1b2c3d4
```

### 查看特定文件

跳转到仓库内的指定文件。

```bash
tw git -f "src/cli/git/index.ts"
```

---

掌握仓库导航后，可通过 [搜索命令](./command-reference-search.md) 学习如何直接从终端执行网页搜索。