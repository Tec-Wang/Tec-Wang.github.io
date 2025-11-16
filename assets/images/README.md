# 图片目录说明

这个目录用于存放网站的所有图片资源。

## 目录结构建议

```
assets/images/
├── avatar.jpg        # 头像（推荐尺寸：200x200 或 300x300）
├── avatar.png        # 头像（PNG格式，支持透明背景）
├── posts/            # 文章中的图片
│   ├── 2024/
│   │   └── post-title-1.jpg
│   └── 2025/
│       └── post-title-2.png
└── README.md         # 本说明文件
```

## 如何在文章中使用图片

### 方法一：Markdown 语法（推荐）
```markdown
![图片描述](/assets/images/posts/2025/your-image.jpg)

![图片描述](/assets/images/posts/2025/your-image.jpg "可选标题")
```

### 方法二：HTML 语法（可以控制大小）
```html
<img src="/assets/images/posts/2025/your-image.jpg" alt="图片描述" width="600">

<img src="/assets/images/posts/2025/your-image.jpg" alt="图片描述" style="max-width: 100%; height: auto;">
```

## 设置头像

1. 将头像图片（推荐 JPG 或 PNG 格式）放到 `assets/images/` 目录
2. 命名为 `avatar.jpg` 或 `avatar.png`
3. 推荐尺寸：200x200 像素或 300x300 像素
4. 在 `_config.yml` 中已配置头像路径（如果文件名不同，请修改配置）

## 图片优化建议

- 图片格式：优先使用 JPG（照片）、PNG（图标/透明背景）、WebP（现代浏览器）
- 图片大小：建议单张图片不超过 1MB，可以使用工具压缩
- 推荐工具：
  - [TinyPNG](https://tinypng.com/) - 在线压缩图片
  - [Squoosh](https://squoosh.app/) - Google 的图片压缩工具

