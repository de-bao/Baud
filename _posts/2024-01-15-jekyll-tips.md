---
layout: post
title: "Jekyll 使用技巧和最佳实践"
date: 2024-01-15
tags: [Jekyll, 博客, 教程]
categories: [技术]
excerpt: "分享一些 Jekyll 博客的使用技巧和最佳实践，帮助你更好地管理你的博客。"
read_time: 5
---

# Jekyll 使用技巧和最佳实践

Jekyll 是一个强大的静态网站生成器，特别适合搭建博客。本文将分享一些实用的技巧和最佳实践。

## 1. 文章组织结构

### Front Matter 规范

每篇文章都应该包含完整的 Front Matter：

```yaml
---
layout: post
title: "文章标题"
date: 2024-01-15
tags: [标签1, 标签2]
categories: [分类]
excerpt: "文章摘要"
read_time: 5
---
```

### 文件命名规范

- 使用日期前缀：`YYYY-MM-DD-title.md`
- 使用小写字母和连字符
- 避免使用特殊字符

## 2. 代码高亮

Jekyll 默认使用 Rouge 进行代码高亮：

````markdown
```python
def hello_world():
    print("Hello, World!")
```
````

## 3. 图片管理

建议将图片放在 `assets/images` 目录下：

```markdown
![图片描述]({{ '/assets/images/example.jpg' | relative_url }})
```

## 4. 分页功能

在 `_config.yml` 中配置分页：

```yaml
paginate: 5
paginate_path: "/page:num/"
```

## 5. 标签和分类

使用标签和分类来组织文章：

```yaml
tags: [JavaScript, React, 教程]
categories: [前端开发]
```

## 6. SEO 优化

- 使用 `jekyll-seo-tag` 插件
- 为每篇文章添加描述
- 使用语义化的 HTML 标签

## 7. 本地开发

使用以下命令进行本地开发：

```bash
bundle exec jekyll serve
```

访问 `http://localhost:4000` 查看效果。

## 总结

这些技巧可以帮助你更好地使用 Jekyll 管理博客。记住保持内容更新，定期备份，享受写作的乐趣！

