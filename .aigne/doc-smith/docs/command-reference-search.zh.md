# 搜索命令

`to-where-cli` 提供了一系列子命令，可直接在终端上快速搜索热门开发者平台。这些命令会在默认网页浏览器中打开相应的搜索结果页面，从而简化您的工作流程。

## npm

在 npm 注册表中搜索软件包。该命令包含多个选项，可直接导航至 npm 软件包的特定页面。

### 用法

```bash
tw npm [keyword] [options]
```

### 参数

| 参数  | 描述                                                 |
| :-------- | :---------------------------------------------------------- |
| `keyword` | 可选。软件包名称或搜索词。如果省略，将打开 npm 主页。 |

### 选项

| 简写 | 全称           | 描述                                                 |
| :---- | :------------- | :---------------------------------------------------------- |
| `-c`  | `--code`         | 在 npm 上打开软件包的代码选项卡。                        |
| `-d`  | `--dependencies` | 打开软件包的依赖项选项卡。                       |
| `-v`  | `--version`      | 打开软件包的版本选项卡。                           |
| `-r`  | `--run-kit`      | 在 RunKit 上打开软件包以进行交互式测试。        |

### 示例

- **搜索与 'react' 相关的软件包：**
  ```bash
  tw npm react
  ```

- **打开 npm 主页：**
  ```bash
  tw npm
  ```

- **查看 'lodash' 软件包的所有版本：**
  ```bash
  tw npm lodash -v
  ```

- **浏览 'express' 软件包的源代码：**
  ```bash
  tw npm express --code
  ```

- **使用 RunKit 直接在浏览器中试用 'commander'：**
  ```bash
  tw npm commander -r
  ```

## github

在 GitHub 上执行搜索。

### 用法

```bash
tw github [keyword]
```

### 参数

| 参数  | 描述                               |
| :-------- | :---------------------------------------- |
| `keyword` | 可选。要在 GitHub 上搜索的词语。 |

### 示例

- **搜索与 'to-where-cli' 相关的仓库或代码：**
  ```bash
  tw github to-where-cli
  ```

## google

在 Google 上执行搜索。

### 用法

```bash
tw google [keyword]
```

### 参数

| 参数  | 描述                               |
| :-------- | :---------------------------------------- |
| `keyword` | 可选。要在 Google 上搜索的词语。 |

### 示例

- **搜索 'how to use commander.js'：**
  ```bash
  tw google "how to use commander.js"
  ```

## bing

在 Bing 上执行搜索。

### 用法

```bash
tw bing [keyword]
```

### 参数

| 参数  | 描述                             |
| :-------- | :-------------------------------------- |
| `keyword` | 可选。要在 Bing 上搜索的词语。 |

### 示例

- **搜索 'typescript best practices'：**
  ```bash
  tw bing "typescript best practices"
  ```

## baidu

在百度上执行搜索。

### 用法

```bash
tw baidu [keyword]
```

### 参数

| 参数  | 描述                              |
| :-------- | :--------------------------------------- |
| `keyword` | 可选。要在百度上搜索的词语。 |

### 示例

- **搜索 'Node.js 教程'：**
  ```bash
  tw baidu "Node.js 教程"
  ```
