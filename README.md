# 孟雨春学术主页维护指南

这是一个基于 [Hugo Blox](https://hugoblox.com/) 的中英双语学术主页：

- 英文站：`/`
- 中文站：`/zh/`
- 英文是默认语言
- 网站源文件以 YAML 和 Markdown 为主
- `public/` 是自动生成的构建产物，不要手工修改

## 1. 本地预览与构建

项目要求安装 Node.js、pnpm、Go 和 Hugo Extended。项目固定使用 Hugo `0.166.0`。

安装依赖：

```powershell
pnpm install
```

启动本地预览：

```powershell
pnpm dev
```

浏览器访问：

- 英文：http://localhost:1313/
- 中文：http://localhost:1313/zh/

生成正式网站：

```powershell
pnpm build
```

构建结果会写入 `public/`。该目录已加入 `.gitignore`，不需要提交。

修改内容后建议运行：

```powershell
pnpm build
```

只有构建成功后再提交到 Git。

## 2. 常用文件位置

| 要修改的内容 | 英文 | 中文或共用文件 |
|---|---|---|
| 个人资料、教育、经历、技能 | `data/authors/me.yaml` | `data/authors/me-zh.yaml` |
| 头像 | `assets/media/authors/me.jpg` | `assets/media/authors/me-zh.jpg` |
| 首页 | `content/en/_index.md` | `content/zh/_index.md` |
| 教育与经历页 | `content/en/experience.md` | `content/zh/experience.md` |
| 研究项目 | `content/en/projects/` | `content/zh/projects/` |
| 学术成果 | `content/en/publications/` | `content/zh/publications/` |
| 会议活动 | `content/en/events/` | `content/zh/events/` |
| 英文导航 | `config/_default/menus.yaml` | 中文导航位于 `config/_default/languages.yaml` |
| 网站名称、SEO、主题 | `config/_default/params.yaml` | 共用 |
| Hugo、语言及安全配置 | `config/_default/hugo.yaml` | 共用 |

中英文内容使用相同目录名，例如：

```text
content/en/projects/aigc-platform-agreements/index.md
content/zh/projects/aigc-platform-agreements/index.md
```

相同的相对路径会使 Hugo 自动建立中英文页面对应关系，并生成语言切换链接。

## 3. 更换头像

当前头像文件是本人报名照片：

```text
assets/media/authors/me.jpg
assets/media/authors/me-zh.jpg
```

如果需要更换，准备一张清晰、接近正方形的照片，建议：

- JPG 或 PNG
- 至少 `600 × 600` 像素
- 人脸位于画面中心
- 文件不要过大，通常 200 KB–1 MB 即可
- 确认照片适合公开，并尽量移除 GPS/设备等 EXIF 元数据

每个作者 slug 只能保留一个头像文件。Hugo 按 `media/authors/<slug>.*` 匹配头像；若同一 slug 同时存在 `.jpg` 和 `.png`，可能继续读取旧文件。

替换为 JPG：

```powershell
Copy-Item "D:\你的照片路径\头像.jpg" "assets\media\authors\me.jpg" -Force
Copy-Item "D:\你的照片路径\头像.jpg" "assets\media\authors\me-zh.jpg" -Force
Remove-Item "assets\media\authors\me.png", "assets\media\authors\me-zh.png" -ErrorAction SilentlyContinue
```

或替换为 PNG：

```powershell
Copy-Item "D:\你的照片路径\头像.png" "assets\media\authors\me.png" -Force
Copy-Item "D:\你的照片路径\头像.png" "assets\media\authors\me-zh.png" -Force
Remove-Item "assets\media\authors\me.jpg", "assets\media\authors\me-zh.jpg" -ErrorAction SilentlyContinue
```

替换后检查目录，确认每个 slug 只有一个文件：

```powershell
Get-ChildItem "assets\media\authors"
```

文件名必须分别与作者 slug 一致：

- 英文作者 `me` → `me.jpg` 或 `me.png`（二选一）
- 中文作者 `me-zh` → `me-zh.jpg` 或 `me-zh.png`（二选一）

替换后如果浏览器仍显示旧图：

1. 停止 `pnpm dev`；
2. 删除 `resources/` 和 `public/`；
3. 重新运行 `pnpm dev`；
4. 浏览器按 `Ctrl+F5` 强制刷新。

注意：头像是公开信息。不要把证件原图、身份证或含敏感背景的照片直接上传。

## 4. 修改个人资料

英文资料：

```text
data/authors/me.yaml
```

中文资料：

```text
data/authors/me-zh.yaml
```

主要字段：

```yaml
role: MA Candidate in Publishing at Nanjing University
bio: |
  English biography here.

interests:
  - Book History and Publishing Studies
  - Digital Publishing and Digital Humanities
```

教育、经历和奖励分别位于：

```yaml
education:
experience:
awards:
```

编辑 YAML 时注意：

- 使用空格缩进，不要用 Tab；
- 同级字段保持相同缩进；
- 英文字符串包含单引号时，外层使用双引号；
- 日期建议使用 `YYYY-MM-DD`；
- 修改英文资料后，同步修改中文资料。

隐私约定：网站只公开姓名、学校、学术邮箱，以及本人明确同意公开的学术信息。不要加入电话、生日、籍贯、政治面貌、微信、私人邮箱或详细地址。

## 5. 添加 GitHub 链接

本项目的 GitHub 仓库是：

```text
https://github.com/mengyuchun/academic-cv
```

如果公开的个人 GitHub 主页也是 `https://github.com/mengyuchun`，在两个作者文件的 `links:` 中加入：

英文 `data/authors/me.yaml`：

```yaml
links:
  - icon: at-symbol
    url: mailto:mengyuchun@smail.nju.edu.cn
    label: Academic email
  - icon: brands/github
    url: https://github.com/mengyuchun
    label: GitHub
```

中文 `data/authors/me-zh.yaml`：

```yaml
links:
  - icon: at-symbol
    url: mailto:mengyuchun@smail.nju.edu.cn
    label: 学术邮箱
  - icon: brands/github
    url: https://github.com/mengyuchun
    label: GitHub
```

这里应填写个人主页地址，而不是某一个仓库地址。若希望论文或项目链接到具体仓库，可在对应页面单独添加链接。

## 6. 放置论文 PDF

### 推荐方法：放进论文自己的目录

例如英文论文页面位于：

```text
content/en/publications/evahan2026-ancient-chinese/index.md
```

将 PDF 复制到同一目录，并统一命名为 `paper.pdf`：

```text
content/en/publications/evahan2026-ancient-chinese/paper.pdf
```

中文页面是独立页面，因此也复制一份到：

```text
content/zh/publications/evahan2026-ancient-chinese/paper.pdf
```

PowerShell 示例：

```powershell
Copy-Item "D:\论文路径\论文.pdf" `
  "content\en\publications\evahan2026-ancient-chinese\paper.pdf"

Copy-Item "D:\论文路径\论文.pdf" `
  "content\zh\publications\evahan2026-ancient-chinese\paper.pdf"
```

然后在中英文论文页面的 front matter 中加入：

```yaml
open_access: true

links:
  - type: pdf
    url: paper.pdf
```

只有 PDF 确实可以合法公开时才设置 `open_access: true`。若出版社或会议不允许公开正式版，可上传作者接受稿，或只链接 DOI/正式页面。

不要写空链接：

```yaml
# 错误：会生成假的 PDF 按钮
links:
  - type: pdf
    url: ''
```

### 添加 DOI

若论文有真实 DOI，可加入：

```yaml
hugoblox:
  ids:
    doi: 10.xxxx/xxxxx
```

不要填写 `https://doi.org/` 前缀，也不要保留空的 `doi: ''`。

### 链接到外部论文页面

如果不想在 Git 仓库中保存 PDF，可直接使用完整 URL：

```yaml
links:
  - type: pdf
    url: https://example.org/path/paper.pdf
```

或添加正式出版页：

```yaml
links:
  - type: source
    url: https://publisher.example.org/article/xxxxx
```

## 7. 新增一篇学术成果

先为英文和中文建立相同目录名：

```text
content/en/publications/new-paper/index.md
content/zh/publications/new-paper/index.md
```

英文最小模板：

```yaml
---
title: 'Paper Title'
authors:
  - me
date: '2026-09-01T00:00:00Z'
publication_types: ['paper-conference']
publication:
  name: 'Conference or Journal Name'
peer_reviewed: true
open_access: false
abstract: >-
  Abstract text.
summary: Short summary.
tags:
  - Publishing Studies
featured: false
projects: []
---
```

中文最小模板：

```yaml
---
title: '论文标题'
authors:
  - me-zh
date: '2026-09-01T00:00:00Z'
publication_types: ['paper-conference']
publication:
  name: '会议或期刊名称'
peer_reviewed: true
open_access: false
abstract: >-
  摘要内容。
summary: 简短摘要。
tags:
  - 出版学
featured: false
projects: []
---
```

常用成果类型：

- `paper-conference`：正式会议论文
- `article-journal`：正式期刊论文
- `manuscript`：工作论文或未正式发表稿
- `thesis`：学位论文

会议报告但未进入正式论文集时，不要标成正式会议论文；可用 `manuscript`，并在 `publication.name` 和摘要中明确写“工作论文/会议报告”。

`featured: true` 会把成果放到首页精选区。

## 8. 新增研究项目

建立成对目录：

```text
content/en/projects/new-project/index.md
content/zh/projects/new-project/index.md
```

示例：

```yaml
---
title: 'Project Title'
date: 2026-09-01
tags:
  - Digital Humanities
---

One-sentence introduction.

<!--more-->

Full project description.
```

`<!--more-->` 之前的文字作为列表摘要，之后是详情页内容。

## 9. 提交到 GitHub

先查看改动：

```powershell
git status
git diff
```

验证构建：

```powershell
pnpm build
```

按明确路径暂存，避免把未审阅的照片、PDF 或私人文件一起提交：

```powershell
git add README.md config content data assets i18n
git diff --cached --stat
git status
git commit -m "feat: update academic profile"
git push
```

暂存后务必查看 `git diff --cached --stat` 和 `git status`。照片和论文 PDF 一旦提交就会进入 Git 历史；提交前检查照片 EXIF 和 PDF 文档属性、附件是否含敏感信息。

不要提交 `public/`、`resources/`、`node_modules/` 或 `.hugo_build.lock`。

### 启用 GitHub Pages（一次性设置）

当前仓库尚未启用 GitHub Pages，直接推送后部署工作流会失败。首次部署前：

1. 确认仓库可见性：免费账户的 GitHub Pages 仅支持公开仓库；私有仓库需要 GitHub Pro/Team/Enterprise。若要公开主页，将仓库设为 Public。
2. 打开仓库 `Settings → Pages`。
3. `Source` 选择 `GitHub Actions`。
4. 推送或重新运行失败的 `Deploy website to GitHub Pages` 工作流。

`baseURL` 说明：

- GitHub Pages 与 Netlify 的构建命令会自动传入 base URL 并覆盖配置，无需手工修改；
- 本地生成最终产物或手动上传时，才需要把 `config/_default/hugo.yaml` 的 `baseURL` 改成最终域名或项目子路径。

GitHub Actions 会读取 `hugoblox.yaml` 中的 Hugo 版本并构建站点。

## 10. 常见问题

### 修改后网页没有变化

先保存文件，再确认 `pnpm dev` 正在运行。必要时：

```powershell
Remove-Item public, resources -Recurse -Force
pnpm dev
```

然后在浏览器按 `Ctrl+F5`。

### 页面构建失败

重点检查错误指出的文件和行号。常见原因：

- YAML 缩进错误；
- 英文单引号嵌套；
- 日期格式错误；
- 文件复制到错误目录；
- `security.exec.allow` 中缺少 `tailwindcss`。

### 中文页没有显示头像

确认同时存在：

```text
assets/media/authors/me.jpg
assets/media/authors/me-zh.jpg
```

也可以同时使用 `.png`，但文件名必须分别对应作者 slug。中文页作者 slug 是 `me-zh`，所以只放 `me.jpg` 或 `me.png` 不够。

### 论文 PDF 按钮回到首页

说明 PDF 的 `url` 是空字符串。删除该链接，或放入真实 PDF 并将 URL 改为 `paper.pdf`。
