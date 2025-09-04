# 命令参考

`to-where-cli` 提供了一套命令，用于管理 URL 别名并直接从终端快速访问网络资源。本节是所有可用命令、子命令和选项的全面参考。

## 命令结构概述

该 CLI 围绕主命令 `tw` 进行组织，后跟用于特定操作的子命令。以下是可用命令的可视化结构图：

```d2
direction: down

"tw": {
  shape: hexagon
  label: "tw (CLI 入口)"
}

"Commands": {
  shape: package
  grid-columns: 3

  "核心命令": {
    shape: package
    "add"
    "rm"
    "ls"
    "clean"
  }

  "Git 命令": {
    shape: package
    "git"
  }

  "搜索命令": {
    shape: package
    "npm"
    "github"
    "google"
    "bing"
    "baidu"
  }
}

"默认操作": {
  label: "tw [alias]"
  shape: rectangle
}

"全局选项": {
    shape: package
    "-h, --help"
    "-V, --version"
}

"tw" -> "默认操作": "默认"
"tw" -> "Commands": "子命令"
"tw" -> "全局选项": "选项"
```

## 主命令 (`tw`)

`to-where-cli` 最基本的用法是打开一个已存储的别名。如果您运行 `tw` 后跟一个字符串，它会将该字符串视为别名，并尝试打开其对应的 URL。

```shell
# 打开与 'home' 别名关联的 URL
tw home
```

如果您在不带任何参数的情况下运行 `tw`，它将显示主帮助菜单。

```shell
# 显示主帮助菜单
tw
```

## 命令类别

命令被分组成逻辑类别。选择下面的类别以查看每个命令的详细文档。

<x-cards data-columns="3">
  <x-card data-title="核心命令" data-icon="lucide:archive" data-href="/command-reference/core">
    使用 add、remove、list 和 clean 等基本命令管理您的别名。
  </x-card>
  <x-card data-title="Git 命令" data-icon="lucide:git-branch" data-href="/command-reference/git">
    快速导航到 Git 仓库的各个页面，例如 issues、pull requests 和 actions。
  </x-card>
  <x-card data-title="搜索命令" data-icon="lucide:search" data-href="/command-reference/search">
    直接从终端在 NPM、GitHub、Google 等平台上执行搜索。
  </x-card>
</x-cards>

## 全局选项

这些选项可用于主命令 `tw` 和大多数子命令。

| 选项 | 描述 |
| ------------------- | ---------------------------- |
| `-h`, `--help` | 显示命令的帮助信息。 |
| `-V`, `--version` | 输出版本号。 |

**示例：**

```shell
# 获取 'add' 子命令的帮助信息
tw add --help

# 查看您安装的版本
tw --version
```

---

现在您已经对命令结构有了大致了解，请通过查阅 [核心命令](./command-reference-core.md) 文档来深入了解具体细节。