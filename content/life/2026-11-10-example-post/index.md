---
title: "示例：如何写一篇 Life 文章"
date: 2026-11-10
tags: ["daily life"]
author: ["Linling Bai"]
description: "Life 板块的示例文章，演示封面图、正文图片和列表页的排版。"
summary: "这是一篇示例文章，演示 Life 板块的写法：标题、日期、标签、封面图和正文内嵌图片。可以直接编辑，也可以删掉后写自己的。"
cover:
    image: "picture.jpeg"
    alt: "示例图片"
---

这是一篇**示例文章**，用来演示 Life 板块的排版。你可以直接编辑它，也可以删掉它再写自己的日常。

## 图片的两种放法

**方式一（本文使用）：** 引用站点里已有的图片，比如 `static/picture.jpeg`，正文里写：

```markdown
![图片说明](/picture.jpeg)
```

**方式二（写真实照片时推荐）：** 把照片放进文章自己的文件夹，和 `index.md` 放在一起：

```
content/life/2026-11-10-example-post/
├── index.md
└── photo.jpg
```

正文里直接写文件名即可，不用写路径：

```markdown
![图片说明](photo.jpg)
```

下面这张就是本文引用的图片：

![正文插图](/picture.jpeg)

---

**关于两个图片位：**

+ `cover.image`（本文设为 `picture.jpeg`）：显示在 **Life 列表页**，作为封面；
+ 正文里的 `![正文插图](/picture.jpeg)`：显示在 **文章页** 正文中。

站点默认在文章页隐藏封面（`config.yml` 里的 `cover.hiddenInSingle: true`）。如果连列表页也不想显示大图，在 front matter 的 `cover` 下面加一行 `hiddenInList: true` 即可。
