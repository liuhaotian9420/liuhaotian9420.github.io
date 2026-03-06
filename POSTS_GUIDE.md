# Jekyll 文章不显示排查（Minimal Mistakes）

如果你把文章放在 `_post/` 目录，Jekyll **不会**把它当成博客文章。

## 必须满足的条件

1. 目录名必须是：`_posts/`（注意有 `s`）。
2. 文件名必须是：`YYYY-MM-DD-title.md`。
3. 文件顶部必须有 Front Matter，例如：

```yaml
---
title: "我的第一篇文章"
date: 2026-03-06 10:00:00 +0800
categories: [blog]
tags: [jekyll, minimal-mistakes]
---
```

## 这个仓库里容易踩坑的点

- 根目录 `_config.yml` 中排除了 `/docs` 和 `/test`，因此放在 `docs/_posts` 或 `test/_posts` 的文章不会出现在主站构建结果里。
- 首页 `index.html` 使用 `layout: home`，只会读取 `site.posts`，也就是根目录 `_posts/` 下符合规则的文章。

## 建议

- 把文章统一放在仓库根目录 `_posts/`。
- 新建文章时按上述命名 + Front Matter 模板创建。
