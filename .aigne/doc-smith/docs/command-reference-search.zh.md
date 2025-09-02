# 搜索命令

`to-where-cli` 提供了一组方便的子命令，可直接从终端在热门的开发者平台上执行搜索。这些命令会在默认的网络浏览器中打开一个新标签页，并显示搜索结果。通用语法为 `tw <platform> [keyword]`。

## `npm`

`npm` 命令允许你在 npm 注册表上搜索软件包，并快速访问特定软件包页面，如版本、依赖项或源代码。

### 用法

```bash
tw npm [keyword] [options]
```

### 参数

| 参数 | 描述 |
|---|---|
| `[keyword]` | 搜索词或软件包名称。如果省略，将打开 [npm 主页](https://www.npmjs.com)。 |

### 选项

| 选项 | 别名 | 描述 |
|---|---|---|
| `--code` | `-c` | 打开软件包的代码页面。 |
| `--dependencies` | `-d` | 打开软件包的依赖项页面。 |
| `--version` | `-v` | 打开软件包的版本页面。 |
| `--run-kit` | `-r` | 在 [RunKit](https://runkit.com) 上打开该软件包以进行交互式测试。 |

### 示例

```bash
# 在 npm 上搜索 'react'
tw npm react

# 打开 'commander' 软件包的版本页面
tw npm commander -v

# 打开 'express' 软件包的依赖项页面
tw npm express --dependencies

# 打开 'lodash' 软件包的代码页面
tw npm lodash -c

# 在 RunKit 上打开 'axios'
tw npm axios -r

# 打开 npm 主页
tw npm
```

## `github`

在 GitHub 上执行搜索。

### 用法

```bash
tw github [keyword]
```

### 参数

| 参数 | 描述 |
|---|---|
| `[keyword]` | 搜索词。如果省略，将打开 [GitHub 搜索页面](https://github.com/search)。 |

### 示例

```bash
# 搜索与 'd3' 相关的仓库或代码
tw github d3

# 打开 GitHub 主搜索页面
tw github
```

## `google`

在 Google 上执行搜索。

### 用法

```bash
tw google [keyword]
```

### 示例

```bash
# 在 Google 上搜索 'how to use git'
tw google "how to use git"
```

## `bing`

在 Bing 上执行搜索。

### 用法

```bash
tw bing [keyword]
```

### 示例

```bash
# 在 Bing 上搜索 'typescript tutorial'
tw bing "typescript tutorial"
```

## `baidu`

在百度上执行搜索。

### 用法

```bash
tw baidu [keyword]
```

### 示例

```bash
# 在百度上搜索 'Vue.js'
tw baidu Vue.js
```

---

既然你已经掌握了搜索功能，你可能会对为该项目做出贡献感兴趣。请前往 [开发指南](./development.md) 查看有关项目结构和设置的详细信息。