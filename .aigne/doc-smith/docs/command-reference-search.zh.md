# 搜索命令

`to-where` CLI 集成了多个流行的搜索引擎，让你可以直接从终端快速执行搜索。这些命令将在你的默认网络浏览器中打开相应的搜索结果页面。

<x-cards data-columns="3">
  <x-card data-title="npm" data-icon="cib:npm">在 npm 注册表上搜索包。</x-card>
  <x-card data-title="github" data-icon="cib:github">在 GitHub 上搜索仓库、代码和用户。</x-card>
  <x-card data-title="google" data-icon="cib:google">使用 Google 进行网络搜索。</x-card>
  <x-card data-title="bing" data-icon="cib:bing">使用 Bing 进行网络搜索。</x-card>
  <x-card data-title="baidu" data-icon="cib:baidu">使用百度进行网络搜索。</x-card>
</x-cards>

## npm

`npm` 命令允许你在 [npmjs.com](https://www.npmjs.com) 上搜索包，并快速访问特定的包页面，如版本、依赖项和代码仓库。

### 用法

```bash
tw npm [keyword] [options]
```

### 参数

-   `[keyword]`：包的名称或搜索词。如果省略，该命令将打开 npm 主页。

### 选项

| 选项 | 长格式      | 描述                        |
| :----- | :------------- | :--------------------------------- |
| `-c`   | `--code`       | 打开包的代码页面。      |
| `-d`   | `--dependencies` | 打开包的依赖项页面。 |
| `-v`   | `--version`    | 打开包的版本页面。  |
| `-r`   | `--run-kit`    | 打开包的 RunKit 页面。    |

### 示例

-   **搜索一个包：**

    ```bash
    tw npm react
    ```

-   **打开特定包的版本页面：**

    ```bash
    tw npm express -v
    ```

-   **查看包的依赖项：**

    ```bash
    tw npm commander -d
    ```

-   **跳转到 RunKit 页面：**

    ```bash
    tw npm lodash -r
    ```

-   **打开 npm 主页：**

    ```bash
    tw npm
    ```

## github

在 [github.com](https://github.com) 上执行搜索。

### 用法

```bash
tw github [keyword]
```

### 参数

-   `[keyword]`：搜索词。如果省略，将打开 GitHub 搜索页面。

### 示例

-   **搜索仓库：**

    ```bash
    tw github to-where-cli
    ```

-   **搜索用户或主题：**

    ```bash
    tw github nodejs
    ```

-   **打开 GitHub 的主搜索页面：**

    ```bash
    tw github
    ```

## google

使用 [google.com](https://www.google.com) 执行标准的网络搜索。

### 用法

```bash
tw google [keyword]
```

### 参数

-   `[keyword]`：搜索词。如果省略，将打开 Google 主页。

### 示例

-   **搜索主题：**

    ```bash
    tw google "how to use commander.js"
    ```

## bing

使用 [bing.com](https://www.bing.com) 执行网络搜索。

### 用法

```bash
tw bing [keyword]
```

### 参数

-   `[keyword]`：搜索词。如果省略，将打开 Bing 主页。

### 示例

-   **搜索主题：**

    ```bash
    tw bing "latest typescript features"
    ```

## baidu

使用 [baidu.com](https://www.baidu.com) 执行网络搜索。

### 用法

```bash
tw baidu [keyword]
```

### 参数

-   `[keyword]`：搜索词。如果省略，将打开百度主页。

### 示例

-   **搜索主题：**

    ```bash
    tw baidu "Vue 3 教程"
    ```
