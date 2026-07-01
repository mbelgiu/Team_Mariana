# 静态网页编辑指南

这个网站是一个基于 Jekyll 和 al-folio 的静态网站。日常修改基本都在 Markdown、YAML、BibTeX、图片和少量 SCSS 文件里完成；不要直接修改 `_site/`，因为它是 Jekyll 自动生成的输出目录。

## 项目位置

网站源码目录：

```bash
/Users/fiko/MacAir_Documents/UT/Website_Mariana/Mariana_Group/work/research-group-site
```

在 VS Code 中打开这个目录即可编辑网页。

## 本地预览

进入网站目录：

```bash
cd /Users/fiko/MacAir_Documents/UT/Website_Mariana/Mariana_Group/work/research-group-site
```

启动本地网站：

```bash
../conda-ruby/bin/bundle exec jekyll serve --host 127.0.0.1 --port 4001 --livereload --livereload-port 35731
```

浏览器打开：

```text
http://127.0.0.1:4001/
```

只构建、不启动服务：

```bash
../conda-ruby/bin/bundle exec jekyll build
```

## 常用文件结构

```text
_config.yml                 网站全局配置
_pages/                     主要页面
_projects/                  research 页面中的项目卡片
_teachings/                 teaching 页面中的课程条目
_news/                      news 页面和首页 announcement
_bibliography/papers.bib    publications 页面中的论文数据
_data/socials.yml           ORCID、Google Scholar、邮箱等社交链接
_data/venues.yml            publication 缩写/期刊颜色
_sass/_site.scss            自定义样式
assets/css/main.scss        样式入口文件
assets/img/                 图片资源
_site/                      自动生成的网页，不要手动编辑
vendor/                     本地 Ruby 依赖，不要手动编辑
```

## 修改首页 About

文件：

```text
_pages/about.md
```

可修改内容：

- `subtitle`：首页标题下方的职位描述。
- `profile.image`：右侧头像图片，图片文件放在 `assets/img/`。
- `profile.more_info`：联系方式、地址、邮箱、链接。
- 正文段落：主页介绍文字。
- `Research themes`：研究方向列表。
- `Teaching and community`：教学与服务介绍。

示例：

```yaml
profile:
  image: mariana-belgiu.jpg
```

表示头像使用：

```text
assets/img/mariana-belgiu.jpg
```

## 修改 Research 页面

主页面文件：

```text
_pages/projects.md
```

项目卡片文件：

```text
_projects/data-centric-eo.md
_projects/hidden-hunger.md
_projects/urban-vulnerability.md
_projects/eo-education-inclusion.md
```

如果要新增一个 research project，可以在 `_projects/` 中新建一个 `.md` 文件。常见 front matter：

```yaml
---
layout: page
title: Project title
description: Short description
img: assets/img/group-placeholder.png
importance: 1
category: research
---
```

`importance` 数字越小，排序越靠前。

## 修改 Publications 页面

页面文件：

```text
_pages/publications.md
```

这里包含：

- Google Scholar 风格的 citation summary。
- `VIEW ALL` 弹窗柱状图。
- Public access 区块。
- bibliography 搜索框和论文列表。

论文数据文件：

```text
_bibliography/papers.bib
```

新增论文时，在 `papers.bib` 中加入 BibTeX 条目。例如：

```bibtex
@article{example2026paper,
  bibtex_show = {true},
  abbr        = {Journal},
  title       = {Paper title},
  author      = {Belgiu, Mariana and Other, Author},
  journal     = {Journal Name},
  year        = {2026},
  selected    = {true}
}
```

`selected = {true}` 会让论文也出现在首页 selected papers 区域。

期刊缩写颜色可以在这里改：

```text
_data/venues.yml
```

## 修改 Teams 页面

Teams 页面入口：

```text
_pages/profiles.md
```

PI 信息：

```text
_pages/people_director.md
```

学生和毕业生列表：

```text
_pages/people_students.md
```

常见修改：

- 修改成员姓名。
- 修改在读时间或毕业时间。
- 修改研究兴趣。
- 添加邮箱。
- 替换头像图片。

头像图片放在：

```text
assets/img/
```

然后在 HTML 中引用：

```liquid
{{ '/assets/img/your-image.jpg' | relative_url }}
```

## 修改 Teaching 页面

主页面：

```text
_pages/teaching.md
```

课程条目：

```text
_teachings/advanced-image-analysis.md
_teachings/machine-learning-geospatial-sciences.md
_teachings/optical-remote-sensing-image-analysis.md
_teachings/space-time.md
```

新增课程时，在 `_teachings/` 中添加新的 `.md` 文件。注意 front matter 中的 `title`、`semester`、`year`、`description` 等字段。

## 修改 News

News 页面：

```text
_pages/news.md
```

新闻条目：

```text
_news/announcement_1.md
_news/announcement_2.md
_news/announcement_3.md
```

新增新闻时，在 `_news/` 中添加 `.md` 文件。示例：

```yaml
---
layout: post
title: News title
date: 2026-06-29 09:00:00+0200
inline: false
related_posts: false
---

News content here.
```

如果 `inline: true`，通常会以简短公告形式显示。

## 修改导航栏

导航栏由每个页面 front matter 中的字段控制：

```yaml
nav: true
nav_order: 3
```

含义：

- `nav: true`：显示在导航栏。
- `nav_order`：导航顺序，数字越小越靠前。
- `title`：导航栏显示名称。

主要页面：

```text
_pages/about.md          /
_pages/projects.md       /research/
_pages/publications.md   /publications/
_pages/profiles.md       /teams/
_pages/news.md           /news/
_pages/teaching.md       /teaching/
```

## 修改样式

主要自定义样式文件：

```text
_sass/_site.scss
```

样式入口文件：

```text
assets/css/main.scss
```

通常只需要改 `_sass/_site.scss`。例如：

- 首页分隔线和内容宽度。
- Research project 卡片样式。
- Teams 成员卡片样式。
- Publications 的 citation summary 和弹窗样式。
- Teaching 页面样式。

不建议直接修改 theme gem 或 `vendor/` 里的文件。

## 修改全局配置

文件：

```text
_config.yml
```

常见字段：

```yaml
title: Mariana Belgiu
description: ...
keywords: ...
max_width: 1080px
url: http://localhost:4000
baseurl:
```

如果发布到 GitHub Pages，需要根据仓库类型修改：

个人主页仓库：

```yaml
url: https://your-username.github.io
baseurl:
```

普通项目仓库：

```yaml
url: https://your-username.github.io
baseurl: /repository-name
```

## 哪些文件不要手动编辑

不要手动编辑：

```text
_site/
vendor/
.jekyll-cache/
```

原因：

- `_site/` 是自动生成结果，每次构建都会覆盖。
- `vendor/` 是 Ruby 依赖。
- `.jekyll-cache/` 是 Jekyll 缓存。

## 发布前检查

发布前建议运行：

```bash
../conda-ruby/bin/bundle exec jekyll build
```

然后本地预览：

```bash
../conda-ruby/bin/bundle exec jekyll serve --host 127.0.0.1 --port 4001 --livereload --livereload-port 35731
```

检查这些页面：

```text
/
/research/
/publications/
/teams/
/news/
/teaching/
```

## GitHub 发布提醒

如果上传到 GitHub，建议上传源码文件，不上传本地运行环境：

不要上传：

```text
vendor/
_site/
.jekyll-cache/
../conda-ruby/
```

建议使用 GitHub Actions 构建并发布 GitHub Pages。

