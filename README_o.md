# Linling Bai — 个人学术主页

这是 Linling Bai 的个人学术主页，用 [Hugo](https://gohugo.io/) 构建，主题为
[PaperMod](https://github.com/adityatelange/hugo-PaperMod)。
项目源自 Pascal Michaillat 的极简学术主页模板
([hugo-website](https://github.com/pmichaillat/hugo-website)，MIT License)，已改写为原创内容。

## 本地预览

1. 安装 Hugo 扩展版（**≥ 0.147.2**，低于此版本模板会直接报错）。macOS 可用 `brew install hugo`，
   Windows 可用 `winget install Hugo.Hugo.Extended`。
2. 在项目目录运行：

```bash
hugo server
```

浏览器打开 http://localhost:1313 即可预览。编辑文件后页面会自动重建。

## 目录结构

```
config.yml     全站配置：站名、导航菜单、首页简历区、联系方式、社交图标
archetypes/    `hugo new` 新建页面时使用的模板
content/       所有页面与文章（Markdown）
  research.md    研究兴趣
  cv.md          简历：教育经历、技能、语言、联系方式
  patents.md     专利与软件著作权
  papers/        论文栏目（列表页 + 每篇论文一个目录）
  tags/          标签索引页
  archive.md     按年份归档全部内容的页面
layouts/       覆盖主题的模板；本项目只放了学术化精简过的少部分模板
assets/css/    覆盖主题的样式
static/        直接复制到网站根目录的文件（头像、favicon、PDF 等）
themes/PaperMod/  内嵌的 PaperMod 主题（完整拷贝，非 git submodule）
```

## 常用修改位置

| 想改什么 | 改哪里 |
|:---|:---|
| 网站标题、域名、导航菜单 | `config.yml` 顶部 |
| 首页头像、姓名、简介、按钮 | `config.yml` 的 `params.profileMode` |
| 首页社交图标（LinkedIn / GitHub / 小红书） | `config.yml` 的 `params.socialIcons` |
| 研究兴趣 | `content/research.md` |
| 教育经历、技能、语言 | `content/cv.md` |
| 专利与软件著作权 | `content/patents.md` |
| 论文 | `content/papers/` 下新建目录，参考 `papers/ci-cd-security-risk/index.md` |
| 头像图片 | 替换 `static/picture.jpeg` |
| 网站图标 | 替换 `static/favicon.ico`、`favicon-16x16.png`、`favicon-32x32.png`、`apple-touch-icon.png` |

### 新增一篇论文

新建 `content/papers/<短名>/index.md`，front matter 需要 `title`、`date`、`tags`、`author`、
`description`、`summary` 六项。若论文有配图，把图片放在同一目录并在 front matter 里写：

```yaml
cover:
    image: "figure.png"
    alt: "图片说明"
    relative: true
```

## 部署

推送到 `main` 分支后，GitHub Actions（`.github/workflows/hugo.yml`）会自动构建并发布到
GitHub Pages。首次部署需要在仓库的 **Settings → Pages** 里把发布来源设为 **GitHub Actions**。

部署前请把 `config.yml` 里的 `baseURL` 改成实际网址。

## 已知待补充

- `static/picture.jpeg` 目前是占位插画，请替换为本人头像。
- 专利与软件著作权的部分标题仍标注为 `[withheld]`。
- 论文页的完整标题、目标平台与作者列表待发表后补齐。
- 如需提供 PDF 版简历，把文件放到 `static/` 下，再把 `config.yml` 中的 `CV` 图标
  从 `cv/` 改为该 PDF 路径。

## 许可

模板部分沿用原作者 MIT License（见 `LICENSE.md`）。
