# Minimal Mistakes 主题使用说明

## 📖 目录

1. [快速开始](#快速开始)
2. [主题配置](#主题配置)
3. [写作指南](#写作指南)
4. [页面布局](#页面布局)
5. [功能特性](#功能特性)
6. [自定义样式](#自定义样式)
7. [常见问题](#常见问题)

---

## 🚀 快速开始

### 已配置的内容

✅ 主题已安装：`remote_theme: "mmistakes/minimal-mistakes@4.27.3"`  
✅ 插件已配置：`jekyll-feed` 和 `jekyll-include-cache`  
✅ 作者信息已设置  
✅ 导航菜单已配置  

### 下一步

1. **设置头像**
   ```
   将头像图片放到：assets/images/avatar.jpg
   推荐尺寸：150x150 或 200x200 像素
   ```

2. **安装依赖**
   ```bash
   bundle install
   ```

3. **本地预览**
   ```bash
   bundle exec jekyll serve
   ```
   访问：http://localhost:4000

---

## ⚙️ 主题配置

### 基础配置（_config.yml）

#### 作者信息

```yaml
author:
  name: "你的名字"
  avatar: /assets/images/avatar.jpg
  bio: "个人简介"
  location: "位置"
  email: "your-email@example.com"
  links:
    - label: "GitHub"
      icon: "fab fa-github"
      url: "https://github.com/username"
    - label: "Twitter"
      icon: "fab fa-twitter"
      url: "https://twitter.com/username"
```

#### 主题皮肤

修改 `minimal_mistakes_skin` 可切换主题皮肤：

```yaml
minimal_mistakes_skin: "default"  # 可选值：
# - default (默认浅色)
# - air (简洁空气感)
# - dark (暗色模式)
# - dirt (泥土色)
# - mint (薄荷绿)
# - neon (霓虹色)
# - aqua (水蓝色)
# - contrast (高对比度)
# - forest (森林绿)
# - ocean (海洋蓝)
```

#### 导航菜单

```yaml
navigation:
  main:
    - title: "主页"
      url: /
    - title: "关于"
      url: /about/
    - title: "分类"
      url: /categories/
    - title: "标签"
      url: /tags/
    - title: "归档"
      url: /posts/
```

---

## ✍️ 写作指南

### 创建新文章

1. **文件命名规则**
   ```
   _posts/YYYY-MM-DD-文章标题.md
   例如：_posts/2025-01-16-my-article.md
   ```

2. **Front Matter 配置**

```yaml
---
layout: post
title: "文章标题"
date: 2025-01-16 10:00:00 +0800
categories: 技术 教程
tags: [Jekyll, 博客]
excerpt: "文章摘要（可选）"
author: Tec-Wang  # 可选，默认使用全局作者
last_modified_at: 2025-01-17  # 最后修改时间（可选）
---
```

### Front Matter 字段说明

| 字段 | 必需 | 说明 |
|------|:----:|------|
| `layout` | ✅ | 布局类型，文章使用 `post` |
| `title` | ✅ | 文章标题 |
| `date` | ✅ | 发布日期 |
| `categories` | ❌ | 分类（空格分隔） |
| `tags` | ❌ | 标签（数组格式） |
| `excerpt` | ❌ | 文章摘要 |
| `author` | ❌ | 作者（覆盖全局设置） |

### 文章头部图片

```yaml
header:
  image: /assets/images/posts/2025/header.jpg  # 头部图片
  overlay_image: /assets/images/posts/2025/overlay.jpg  # 叠加图片
  overlay_filter: 0.5  # 透明度（0-1）
  caption: "图片说明"  # 图片说明
  actions:
    - label: "了解更多"
      url: "/about/"
```

### 插入图片

```markdown
# 基本语法
![图片描述](/assets/images/posts/2025/image.jpg)

# 控制大小
<img src="/assets/images/posts/2025/image.jpg" alt="描述" width="600">

# 带链接的图片
[![图片](/assets/images/posts/2025/image.jpg)](https://example.com)
```

**图片存放建议**：
```
assets/images/
├── avatar.jpg              # 头像
└── posts/                  # 文章图片
    ├── 2025/
    │   └── article-1.jpg
    └── 2024/
        └── article-2.png
```

### 代码块

```markdown
# 基本语法（自动高亮）
```python
def hello():
    print("Hello, World!")
```

# 带行号的代码块
{% highlight python linenos %}
def hello():
    print("Hello, World!")
{% endhighlight %}
```

### 提示框

```markdown
{: .notice}
普通提示

{: .notice--info}
信息提示

{: .notice--warning}
警告提示

{: .notice--success}
成功提示

{: .notice--danger}
危险提示
```

### 分类和标签

**分类（categories）**：
- 用于大范围的分类，如：技术、生活、工作
- 一篇文章可以有多个分类
- 格式：`categories: 技术 教程`（空格分隔）

**标签（tags）**：
- 用于更细粒度的标记
- 格式：`tags: [Jekyll, 博客, 教程]`（数组格式）

---

## 📄 页面布局

### 布局类型

| 布局 | 用途 | 说明 |
|------|------|------|
| `home` | 首页 | 显示文章列表 |
| `single` | 单页 | 单独页面（如 About） |
| `post` | 文章 | 博客文章 |
| `archive` | 归档 | 文章归档页面 |
| `category` | 分类 | 分类页面 |
| `tag` | 标签 | 标签页面 |

### 创建新页面

1. **About 页面**
   ```
   about.md
   ---
   layout: single
   title: "About"
   permalink: /about/
   author_profile: true
   ---
   ```

2. **自定义页面**
   ```
   contact.md
   ---
   layout: single
   title: "联系方式"
   permalink: /contact/
   ---
   页面内容...
   ```

---

## 🎨 功能特性

### 已启用的功能

✅ **RSS 订阅**：`/feed.xml`  
✅ **分类归档**：`/categories/`  
✅ **标签归档**：`/tags/`  
✅ **文章归档**：`/posts/`  
✅ **作者侧边栏**：显示头像和简介  

### 可选功能

#### 搜索功能

需要配置搜索引擎（Algolia 或 Lunr）

#### 评论系统

可以集成：
- Disqus
- Gitalk（基于 GitHub Issues）
- Utterances（基于 GitHub Discussions）

---

## 🎨 自定义样式

### 自定义 CSS

创建 `assets/css/main.scss`：

```scss
---
---

@import "minimal-mistakes";

// 自定义样式
.author__avatar {
  border-radius: 50%;
}
```

### 自定义字体

在 `_config.yml` 中配置：

```yaml
font:
  text: "Noto Sans SC"  # 中文字体
  code: "Fira Code"     # 代码字体
```

---

## 📱 响应式设计

Minimal Mistakes 主题完全响应式，自动适配：
- 🖥️ 桌面端
- 📱 手机端
- 📲 平板端

---

## ❓ 常见问题

### Q: 如何修改主题颜色？

A: 修改 `_config.yml` 中的 `minimal_mistakes_skin` 字段，或创建自定义 CSS。

### Q: 文章中的图片无法显示？

A: 检查图片路径是否正确，路径以 `/` 开头（如：`/assets/images/...`）

### Q: 如何添加文章摘要？

A: 在 Front Matter 中使用 `excerpt:` 字段，或在文章中添加 `<!--more-->` 标记。

### Q: 分类和标签有什么区别？

A: 分类用于大范围分类（如：技术、生活），标签用于细粒度标记（如：Python、Django）。

### Q: 如何添加导航菜单项？

A: 在 `_config.yml` 的 `navigation.main` 中添加项目。

### Q: 本地预览正常，但部署后样式丢失？

A: 检查 `baseurl` 配置是否正确，对于 `username.github.io` 仓库应为空字符串。

---

## 📚 相关资源

- [Minimal Mistakes 官方文档](https://mmistakes.github.io/minimal-mistakes/)
- [GitHub 仓库](https://github.com/mmistakes/minimal-mistakes)
- [Jekyll 官方文档](https://jekyllrb.com/docs/)
- [Markdown 语法指南](https://www.markdownguide.org/)

---

## 💡 使用技巧

### 1. 文章预览

在文章中添加 `<!--more-->` 标记，标记之前的内容会作为摘要显示在首页。

### 2. 相关文章

在文章末尾可以添加相关文章链接，提升用户体验。

### 3. 图片优化

- 使用 JPG 格式（照片）
- 使用 PNG 格式（图标、透明背景）
- 压缩图片大小（推荐使用 TinyPNG）

### 4. SEO 优化

- 设置 `description`（网站描述）
- 为文章添加 `excerpt`（文章摘要）
- 使用合理的分类和标签
- 为图片添加 `alt` 属性

---

## 🔄 更新主题

主题使用 `remote_theme` 方式安装，更新主题版本：

```yaml
# _config.yml
remote_theme: "mmistakes/minimal-mistakes@最新版本号"
```

查看最新版本：https://github.com/mmistakes/minimal-mistakes/releases

---

**祝使用愉快！** 🎉

如有问题，欢迎查看官方文档或提交 Issue。

