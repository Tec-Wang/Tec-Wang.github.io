# Jekyll 使用指南

## 📚 什么是 Jekyll？

Jekyll 是一个静态网站生成器，可以将 Markdown 文件转换成完整的 HTML 网站。它非常适合：
- 个人博客
- 文档网站
- 项目展示页面
- GitHub Pages 网站

## 📁 你的仓库结构分析

### 核心文件说明

```
Tec-Wang.github.io/
├── _config.yml          # 网站配置文件（标题、描述、主题等）
├── Gemfile              # Ruby 依赖管理文件
├── index.markdown       # 网站首页
├── about.markdown       # 关于页面
├── 404.html            # 404 错误页面
└── _posts/             # 博客文章目录
    ├── 2024-08-05-welcome-to-jekyll.markdown
    └── 2025-11-16-test.md
```

### 关键配置解析

**`_config.yml`** - 网站全局配置：
- `title`: 网站标题
- `description`: 网站描述
- `baseurl` 和 `url`: 网站地址（GitHub Pages 通常需要修改）
- `theme`: 使用的主题（当前为 `minima`）

**`Gemfile`** - 依赖管理：
- 使用 `github-pages` gem（适合 GitHub Pages 部署）
- 已配置 Windows 平台支持

## 🚀 快速开始

### 第一步：安装 Ruby 和 Bundler

**Windows 系统：**
1. 下载并安装 Ruby：https://rubyinstaller.org/
   - 选择 Ruby+Devkit 版本
   - 安装时勾选 "Add Ruby executables to your PATH"
2. 打开 PowerShell，验证安装：
   ```bash
   ruby --version
   ```
3. 安装 Bundler：
   ```bash
   gem install bundler
   ```

### 第二步：安装依赖

在项目目录下运行：
```bash
bundle install
```

这会根据 `Gemfile` 安装所有需要的依赖包。

### 第三步：启动本地服务器

```bash
bundle exec jekyll serve
```

访问：http://localhost:4000

**常用参数：**
- `--livereload`: 自动刷新浏览器（推荐）
  ```bash
  bundle exec jekyll serve --livereload
  ```
- `--host 0.0.0.0`: 允许局域网访问
- `--port 4000`: 指定端口

## ✍️ 写博客文章

### 文章命名规则

文件名格式：`YEAR-MONTH-DAY-title.md`

例如：`2025-11-16-我的第一篇文章.md`

### 文章格式（必须包含 Front Matter）

每篇文章开头必须包含 YAML Front Matter（用 `---` 包围）：

```markdown
---
layout: post
title: "文章标题"
date: 2025-11-16 12:00:00 +0800
categories: 分类1 分类2
tags: [标签1, 标签2]
---

这里是文章内容，可以使用 Markdown 语法。
```

### Front Matter 字段说明

- `layout`: 布局类型（通常为 `post`）
- `title`: 文章标题
- `date`: 发布日期（格式：`YYYY-MM-DD HH:MM:SS +时区`）
- `categories`: 分类（空格分隔）
- `tags`: 标签（数组格式）

### 示例：创建新文章

1. 在 `_posts` 目录下创建文件：`2025-11-17-我的新文章.md`
2. 写入内容：

```markdown
---
layout: post
title: "我的新文章"
date: 2025-11-17 10:00:00 +0800
categories: 技术
tags: [Jekyll, 教程]
---

# 这是标题

这是一段内容，**可以加粗**，*可以斜体*。

## 代码示例

```python
def hello():
    print("Hello, Jekyll!")
```

[链接示例](https://jekyllrb.com)
```

## 🎨 自定义网站

### 修改网站信息

编辑 `_config.yml`：

```yaml
title: 你的网站标题
email: your-email@example.com
description: 网站描述
baseurl: ""  # GitHub Pages 仓库名为 username.github.io 时留空
url: "https://Tec-Wang.github.io"  # 你的 GitHub Pages 地址
github_username: Tec-Wang
```

**注意**：修改 `_config.yml` 后需要**重启服务器**才能生效！

### 修改主题

1. 查看可用主题：https://jekyllthemes.io/
2. 修改 `_config.yml` 中的 `theme` 字段
3. 运行 `bundle update` 更新依赖

### 自定义页面

创建新的 `.markdown` 或 `.md` 文件，例如 `contact.markdown`：

```markdown
---
layout: page
title: 联系我
permalink: /contact/
---

这是我的联系方式...
```

## 📤 部署到 GitHub Pages

### 方法一：自动部署（推荐）

1. 确保仓库名为 `Tec-Wang.github.io`
2. 将代码推送到 `gh-pages` 分支（你已经在这个分支）
3. 在 GitHub 仓库设置中启用 GitHub Pages
4. GitHub 会自动构建和部署你的网站

### 方法二：本地构建后推送

```bash
# 构建网站
bundle exec jekyll build

# 构建的文件在 _site 目录
# 将 _site 目录内容推送到 gh-pages 分支
```

## 🔧 常见问题

### 1. 文章不显示

- 检查文件名格式：必须是 `YYYY-MM-DD-title.md`
- 检查 Front Matter 格式是否正确
- 确保文件在 `_posts` 目录下

### 2. 修改不生效

- `_config.yml` 修改后需要重启服务器
- 清除缓存：删除 `.jekyll-cache` 和 `.sass-cache` 目录

### 3. 依赖安装失败

```bash
# 更新 Bundler
gem update bundler

# 清理并重新安装
bundle clean --force
bundle install
```

### 4. 端口被占用

```bash
# 使用不同端口
bundle exec jekyll serve --port 4001
```

## 📖 常用命令总结

```bash
# 安装依赖
bundle install

# 启动开发服务器（带自动刷新）
bundle exec jekyll serve --livereload

# 构建网站
bundle exec jekyll build

# 查看 Jekyll 版本
bundle exec jekyll --version

# 更新依赖
bundle update
```

## 🔗 有用资源

- [Jekyll 官方文档](https://jekyllrb.com/docs/)
- [Jekyll 主题](https://jekyllthemes.io/)
- [Markdown 语法](https://www.markdownguide.org/)
- [Liquid 模板语言](https://shopify.github.io/liquid/)（用于模板）

## 💡 提示

1. **使用 `bundle exec`**：确保使用正确的 Jekyll 版本
2. **Front Matter 很重要**：没有正确格式的文章不会被处理
3. **文件编码**：使用 UTF-8 编码保存文件
4. **实时预览**：使用 `--livereload` 参数，修改文件后浏览器自动刷新

---

现在你可以开始使用 Jekyll 创建你的博客了！🎉

