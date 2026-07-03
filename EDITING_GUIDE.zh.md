# Team Mariana 网站编辑指南

<a id="brief-introduction"></a>

## 1. Brief Introduction

网站链接：<https://mbelgiu.github.io/Team_Mariana/>

<span style="color:#0b6f6a"><strong>重点：</strong></span>这个项目是一个基于 Jekyll 和 al-folio 的静态网站。修改网页时，主要编辑 Markdown、YAML、BibTeX、图片和少量 SCSS 文件。

<span style="color:#b54708"><strong>注意：</strong></span>本地预览时用 `/`，线上网站才使用 `/Team_Mariana/`。不要直接编辑 `_site/`，它是自动生成目录。

当前页面源文件已经按导航名称整理：

| 页面 | 源文件 | 线上 URL |
| --- | --- | --- |
| Home | `_pages/Home.md` | `/` |
| Research | `_pages/Research.md` | `/research/` |
| Publications | `_pages/Publications.md` | `/publications/` |
| Teams | `_pages/Teams.md` | `/teams/` |
| News | `_pages/News.md` | `/news/` |
| Teaching | `_pages/Teaching.md` | `/teaching/` |

图片已经按页面分类存放：

```text
assets/img/home/       Home 页面头像、ITC logo、首页相关图片
assets/img/research/   Research 页面项目图片
assets/img/teams/      Teams 页面成员头像
```

发布到线上：

```bash
git status
git add .
git commit -m "Update website content"
git push
```

推送到 `main` 分支后，GitHub Actions 会自动重新部署。

<a id="content"></a>

## 2. Content / 目录

- [1. Brief Introduction](#brief-introduction)
- [2. Content / 目录](#content)
- [3. Home 页面编辑方法](#home)
- [4. Research 页面编辑方法](#research)
- [5. Publication 页面编辑方法](#publication)
- [6. Teams 页面编辑方法](#teams)
- [7. News 页面编辑方法](#news)
- [8. Teaching 页面编辑方法](#teaching)
- [9. 修改后检查与发布](#check-and-publish)

<a id="home"></a>

## 3. Home 页面编辑方法

Home 页面地址：

```text
https://mbelgiu.github.io/Team_Mariana/
```

主要文件：

| 内容 | 文件 |
| --- | --- |
| 页面主体 | `_pages/Home.md` |
| 底部 ORCID、Google Scholar、Email、RSS、ITC 图标 | `_data/socials.yml` |
| Home 图片 | `assets/img/home/` |
| Home 样式 | `_sass/_site.scss` |

### 3.1 修改页面标题、导航名称、页面 URL

文件：`_pages/Home.md`

代码块：

```yaml
---
layout: about
title: Home
permalink: /
subtitle: Associate Professor in GeoAI & multi-temporal remote sensing, <a href="https://www.itc.nl/">Faculty ITC, University of Twente</a>
---
```

Update：

- 修改 `title: Home` 可以改变导航栏显示名称。
- 修改 `subtitle` 可以改变首页副标题。
- `permalink: /` 表示首页地址，通常不要改。

Add：

```yaml
description: Research group website for Mariana Belgiu.
```

Delete：

- 不建议删除 `layout`、`title`、`permalink`。
- 删除 `subtitle` 后首页副标题会消失。

### 3.2 修改头像和联系信息

文件：`_pages/Home.md`

代码块：

```yaml
profile:
  align: right
  image: home/mariana-belgiu.jpg
  image_circular: false
  more_info: >
    <p>ITC-SCI-TECH</p>
    <p>Department of Earth Observation Science</p>
    <p>Faculty ITC, University of Twente</p>
    <p>Langezijds 1326, Enschede</p>
    <p><a href="mailto:m.belgiu@utwente.nl">m.belgiu@utwente.nl</a></p>
```

Update：

- 头像图片放在 `assets/img/home/`。
- 当前头像路径是 `assets/img/home/mariana-belgiu.jpg`。
- 修改 `more_info` 中的 `<p>...</p>` 可以更新地址、邮箱、电话和外部链接。

Add：

```html
<p><a href="https://example.com">New profile link</a></p>
```

Delete：

- 删除某一行 `<p>...</p>` 即可删除对应联系信息。

### 3.3 修改首页简介文字

文件：`_pages/Home.md`

代码块：

```markdown
<div class="about-overview" markdown="1">

Dr. Mariana Belgiu is an Associate Professor ...

The group develops data-centric AI methods ...

</div>
```

Update：

- 直接修改中间段落即可。

Add：

```markdown
The group also collaborates with international partners on applied GeoAI projects.
```

Delete：

- 删除不需要的段落。
- 不建议删除外层 `<div class="about-overview" markdown="1">`。

### 3.4 修改 Research themes

文件：`_pages/Home.md`

代码块：

```markdown
## Research themes

- **Data-centric AI for Earth Observation:** methods for multi-temporal optical, hyperspectral, and radar imagery.
- **Learning with scarce labels:** robust and transferable algorithms for mapping crops, land cover, and urban environments.

<div class="expertise-tags" aria-label="Expertise keywords">
  <span>GeoAI</span>
  <span>Remote sensing</span>
</div>
```

Update：

- 修改列表项可以更新研究方向。
- 修改 `<span>...</span>` 可以更新关键词标签。

Add：

```markdown
- **New research theme:** short description here.
```

```html
<span>New keyword</span>
```

Delete：

- 删除某一行 `- **...:** ...` 即可删除一个主题。
- 删除某个 `<span>...</span>` 即可删除一个标签。

### 3.5 修改 Teaching and community

文件：`_pages/Home.md`

代码块：

```markdown
## Teaching and community

Mariana teaches optical remote sensing ...

She is active in EO4all ...
```

Update：

- 修改标题和段落即可。

Add：

- 在该 section 结束前增加新的段落。

Delete：

- 删除不需要的段落。

### 3.6 修改 Home 底部 ORCID、Google Scholar、Email、RSS 和 ITC 图标

文件：`_data/socials.yml`

代码块：

```yaml
orcid_id: 0000-0002-2147-1894
scholar_userid: GBi_DcgAAAAJ
email: m.belgiu@utwente.nl
rss_icon: true

custom_social:
  logo: /assets/img/home/itc-logo.png
  title: UTwente Research Profile
  url: https://research.utwente.nl/en/persons/mariana-belgiu/
```

Update：

- `orcid_id` 控制 ORCID 图标链接。
- `scholar_userid` 控制 Google Scholar 图标链接。
- `email` 控制邮件图标链接。
- `rss_icon: true` 表示显示 RSS 图标。
- `custom_social.logo` 控制最后一个自定义图片图标。当前已经换成 ITC logo。
- `custom_social.url` 控制点击 ITC logo 后跳转到哪里。

Add：

- 如需更换 ITC logo，把新图片放到 `assets/img/home/`，然后改：

```yaml
custom_social:
  logo: /assets/img/home/new-logo.png
```

Delete：

- 不想显示 RSS，改成：

```yaml
rss_icon: false
```

- 不想显示最后一个 ITC 图标，删除整个 `custom_social:` 代码块。

<span style="color:#0b6f6a"><strong>重点：</strong></span>底部图标不是在 `_pages/Home.md` 中改，而是在 `_data/socials.yml` 中改。

<a id="research"></a>

## 4. Research 页面编辑方法

Research 页面地址：

```text
https://mbelgiu.github.io/Team_Mariana/research/
```

主要文件：

| 内容 | 文件 |
| --- | --- |
| 页面介绍和高亮项目 | `_pages/Research.md` |
| Research 卡片 | `_projects/*.md` |
| Research 图片 | `assets/img/research/` |

### 4.1 修改页面标题和导航

文件：`_pages/Research.md`

代码块：

```yaml
---
layout: page
title: Research
permalink: /research/
description: Earth Observation, data-centric AI, food security, and urban vulnerability research.
nav: true
nav_order: 2
display_categories: [research]
horizontal: false
---
```

Update：

- `title` 控制导航名称。
- `description` 控制页面描述。
- `nav_order` 控制导航顺序。

Add：

```yaml
display_categories: [research, new-category]
```

Delete：

- 不想显示在导航栏中，改成：

```yaml
nav: false
```

### 4.2 修改 Research overview 和关键词

文件：`_pages/Research.md`

代码块：

```markdown
## Research overview

Mariana Belgiu's research develops GeoAI ...

<div class="expertise-tags" aria-label="Research expertise">
  <span>Remote sensing</span>
  <span>GeoAI</span>
</div>
```

Update：

- 修改段落更新研究概述。
- 修改 `<span>...</span>` 更新关键词。

Add：

```html
<span>New expertise</span>
```

Delete：

- 删除不需要的 `<span>...</span>`。

### 4.3 修改 Selected funded projects and networks

文件：`_pages/Research.md`

代码块：

```html
<article class="project-highlight">
  <h3>EO4Nutri</h3>
  <p>ESA-funded work using Earth Observation and spatial data ...</p>
  <span>2023-2025</span>
</article>
```

Update：

- `<h3>` 是项目名。
- `<p>` 是项目简介。
- `<span>` 是项目时间。

Add：

```html
<article class="project-highlight">
  <h3>New Project</h3>
  <p>Short project description.</p>
  <span>2026-2028</span>
</article>
```

Delete：

- 删除完整的 `<article class="project-highlight"> ... </article>`。

### 4.4 修改 Research 卡片

文件夹：`_projects/`

示例文件：`_projects/data-centric-eo.md`

代码块：

```yaml
---
layout: page
title: Data-Centric AI for Earth Observation
description: Multi-temporal remote sensing, scarce-label learning, transferability, and environmental mapping.
img: assets/img/research/group-placeholder.png
importance: 1
category: research
related_publications: true
---
```

Update：

- `title` 更新卡片标题。
- `description` 更新卡片摘要。
- `img` 更新卡片图片，Research 图片建议放在 `assets/img/research/`。
- `importance` 控制排序，数字越小越靠前。

Add：

```markdown
---
layout: page
title: New Research Direction
description: One-sentence summary.
img: assets/img/research/group-placeholder.png
importance: 5
category: research
---

Full description here.
```

Delete：

- 删除 `_projects/` 中对应 `.md` 文件即可删除卡片。

<a id="publication"></a>

## 5. Publication 页面编辑方法

Publication 页面地址：

```text
https://mbelgiu.github.io/Team_Mariana/publications/
```

主要文件：

| 内容 | 文件 |
| --- | --- |
| 页面结构、Google Scholar 摘要、柱状图 | `_pages/Publications.md` |
| 论文列表 | `_bibliography/papers.bib` |
| 期刊缩写 | `_data/venues.yml` |
| Scholar 区块样式 | `_sass/_site.scss` |

### 5.1 修改页面标题和导航

文件：`_pages/Publications.md`

代码块：

```yaml
---
layout: page
permalink: /publications/
title: Publications
description: selected papers, preprints, and group outputs.
nav: true
nav_order: 3
---
```

Update：

- 修改 `title` 更新导航显示名称。
- 修改 `description` 更新页面描述。

Delete：

- 不想显示在导航栏中，改成 `nav: false`。

### 5.2 修改 Google Scholar citation summary

文件：`_pages/Publications.md`

代码块：

```html
<table class="scholar-citations" aria-label="Citation metrics">
  <tbody>
    <tr>
      <th scope="row">Citations</th>
      <td>12304</td>
      <td>9615</td>
    </tr>
  </tbody>
</table>
```

Update：

- 修改 `Citations`、`h-index`、`i10-index` 对应数字。

Add：

```html
<tr>
  <th scope="row">New metric</th>
  <td>100</td>
  <td>80</td>
</tr>
```

Delete：

- 删除对应的 `<tr> ... </tr>`。

### 5.3 修改 Citation 柱状图

文件：`_pages/Publications.md`

代码块：

```html
<div class="scholar-chart__bar" style="--height: 32%">
  <span class="scholar-chart__year">2019</span>
  <span class="scholar-chart__value">704</span>
</div>
```

Update：

- `--height` 控制柱子高度。
- `scholar-chart__year` 控制年份。
- `scholar-chart__value` 控制鼠标悬停时显示的数值。
- 预览图和弹窗图各有一份数据，通常要同时修改。

Add：

```html
<div class="scholar-chart__bar" style="--height: 60%">
  <span class="scholar-chart__year">2027</span>
  <span class="scholar-chart__value">1320</span>
</div>
```

Delete：

- 删除一个完整的 `scholar-chart__bar`。

### 5.4 修改 Public access

文件：`_pages/Publications.md`

代码块：

```html
<span class="scholar-access__closed">2 articles not available</span>
<span class="scholar-access__open">29 articles available</span>
```

Update：

- 修改文章数量即可。

Delete：

- 删除整个 `<div class="scholar-access"> ... </div>` 可以移除 Public access。

### 5.5 修改论文列表

文件：`_bibliography/papers.bib`

代码块：

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

Update：

- 修改 `title`、`author`、`journal`、`year` 等字段。
- `selected = {true}` 会让论文出现在 Home 页 selected publications。

Add：

- 在 `papers.bib` 末尾添加新的 BibTeX 条目。

Delete：

- 删除完整的 `@article{...}` 或 `@misc{...}` 条目。

<a id="teams"></a>

## 6. Teams 页面编辑方法

Teams 页面地址：

```text
https://mbelgiu.github.io/Team_Mariana/teams/
```

主要文件：

| 内容 | 文件 |
| --- | --- |
| Teams 页面入口 | `_pages/Teams.md` |
| PI 介绍 | `_pages/people_director.md` |
| 学生和 alumni 列表 | `_pages/people_students.md` |
| 成员头像 | `assets/img/teams/` |

### 6.1 修改 Teams 页面入口

文件：`_pages/Teams.md`

代码块：

```yaml
profiles:
  - align: right
    image: home/mariana-belgiu.jpg
    content: people_director.md
    image_circular: false
    more_info: >
      <p>Associate Professor in GeoAI & multi-temporal remote sensing</p>
  - content: people_students.md
```

Update：

- `image` 控制 PI 图片。
- `content: people_director.md` 表示 PI 文字来自 `_pages/people_director.md`。
- `content: people_students.md` 表示学生列表来自 `_pages/people_students.md`。

Delete：

- 删除 `- content: people_students.md` 会隐藏学生列表。

### 6.2 修改 PI 介绍

文件：`_pages/people_director.md`

代码块：

```markdown
### Dr. Mariana Belgiu

Mariana Belgiu is an Associate Professor ...

<dl class="profile-contact">
  <dt>Email</dt>
  <dd><a href="mailto:m.belgiu@utwente.nl">m.belgiu@utwente.nl</a></dd>
</dl>
```

Update：

- 修改标题、段落、`<dt>` 和 `<dd>`。

Add：

```html
<dt>Office</dt>
<dd>Langezijds 1326, University of Twente</dd>
```

Delete：

- 删除一组 `<dt>...</dt>` 和 `<dd>...</dd>`。

### 6.3 修改 Current PhD Researchers

文件：`_pages/people_students.md`

代码块：

```html
<article class="team-member">
  <div class="team-member__photo">
    <img src="{{ '/assets/img/teams/Anonymous_Photo.jpg' | relative_url }}" alt="Portrait placeholder for Yangyang Cao">
  </div>
  <div class="team-member__content">
    <h5 class="team-member__name">Yangyang Cao</h5>
    <dl class="team-member__details">
      <dt>Period</dt>
      <dd>2023-present</dd>
      <dt>Research interests</dt>
      <dd>Grain protein prediction using deep learning with UAV and spaceborne hyperspectral imagery.</dd>
      <dt>Email</dt>
      <dd>To be added</dd>
    </dl>
  </div>
</article>
```

Update：

- 修改姓名、在读时间、研究兴趣和邮箱。
- 成员头像建议放在 `assets/img/teams/`。

Add：

```html
<article class="team-member">
  <div class="team-member__photo">
    <img src="{{ '/assets/img/teams/student-photo.jpg' | relative_url }}" alt="Portrait of Student Name">
  </div>
  <div class="team-member__content">
    <h5 class="team-member__name">Student Name</h5>
    <dl class="team-member__details">
      <dt>Period</dt>
      <dd>2026-present</dd>
      <dt>Research interests</dt>
      <dd>Short research interest description.</dd>
      <dt>Email</dt>
      <dd><a href="mailto:name@example.com">name@example.com</a></dd>
    </dl>
  </div>
</article>
```

Delete：

- 删除完整的 `<article class="team-member"> ... </article>`。

### 6.4 修改 Alumni

文件：`_pages/people_students.md`

Update：

- Alumni 和 Current PhD Researchers 的结构一样。
- 修改 Alumni 区块中的 `<article class="team-member">` 即可。

Add：

- 在 Alumni 的 `<section>` 中增加新的 `<article>`。

Delete：

- 删除对应 alumni 的完整 `<article>`。

<a id="news"></a>

## 7. News 页面编辑方法

News 页面地址：

```text
https://mbelgiu.github.io/Team_Mariana/news/
```

主要文件：

| 内容 | 文件 |
| --- | --- |
| News 页面入口 | `_pages/News.md` |
| News 条目 | `_news/*.md` |
| Home 页 News 数量 | `_pages/Home.md` |

### 7.1 修改 News 页面入口

文件：`_pages/News.md`

代码块：

```markdown
---
layout: page
title: News
permalink: /news/
nav: true
nav_order: 5
---

{% include news.liquid %}
```

Update：

- 修改 `title` 和 `nav_order`。

Delete：

- 不要删除 `{% include news.liquid %}`，否则新闻列表不会显示。

### 7.2 新增 News

文件夹：`_news/`

Add：

```markdown
---
layout: post
title: New announcement title
date: 2026-07-03 09:00:00+0200
inline: false
related_posts: false
---

News content here.
```

Update：

- 修改 `title`、`date`、`inline` 和正文。

Delete：

- 删除对应 `_news/*.md` 文件即可。

### 7.3 修改 Home 页 News 数量

文件：`_pages/Home.md`

代码块：

```yaml
announcements:
  enabled: true
  scrollable: true
  limit: 5
```

Update：

- 修改 `limit` 控制 Home 页最多显示几条 News。

Delete：

```yaml
announcements:
  enabled: false
```

<a id="teaching"></a>

## 8. Teaching 页面编辑方法

Teaching 页面地址：

```text
https://mbelgiu.github.io/Team_Mariana/teaching/
```

主要文件：

| 内容 | 文件 |
| --- | --- |
| Teaching 页面介绍 | `_pages/Teaching.md` |
| 课程条目 | `_teachings/*.md` |

### 8.1 修改 Teaching 页面标题和简介

文件：`_pages/Teaching.md`

代码块：

```markdown
---
layout: page
permalink: /teaching/
title: Teaching
description: Courses, supervision, and teaching activities in Earth Observation and geospatial AI.
nav: true
nav_order: 6
---

Mariana teaches and supervises students in Earth Observation ...
```

Update：

- 修改 `title`、`description` 和正文简介。

Delete：

- 不想显示在导航栏中，改成 `nav: false`。

### 8.2 修改 Teaching areas

文件：`_pages/Teaching.md`

代码块：

```markdown
## Teaching areas

- Optical remote sensing and image analysis.
- Machine learning and deep learning for geospatial sciences.
```

Update：

- 修改列表项。

Add：

```markdown
- New teaching area.
```

Delete：

- 删除不需要的列表项。

### 8.3 修改课程列表

文件夹：`_teachings/`

示例：

```markdown
---
layout: course
title: Advanced Image Analysis
description: Advanced methods for analyzing remote sensing imagery.
instructor: Mariana Belgiu
year: 2025
term: 2025/2026
location: Faculty ITC, University of Twente
course_id: advanced-image-analysis
---

This recurring ITC course focuses on advanced analysis of Earth Observation imagery.
```

Update：

- 修改 `title`、`description`、`year`、`term`、`location` 和正文。

Add：

```markdown
---
layout: course
title: New Course
description: Short course description.
instructor: Mariana Belgiu
year: 2026
term: 2026/2027
location: Faculty ITC, University of Twente
course_id: new-course
---

Full course description here.
```

Delete：

- 删除 `_teachings/` 中对应课程文件。

<a id="check-and-publish"></a>

## 9. 修改后检查与发布

本地检查：

```bash
../conda-ruby/bin/bundle exec jekyll build
```

本地预览：

```bash
../conda-ruby/bin/bundle exec jekyll serve --host 127.0.0.1 --port 4001 --baseurl '' --livereload --livereload-port 35731
```

浏览器打开：

```text
http://127.0.0.1:4001/
```

发布到线上：

```bash
git status
git add .
git commit -m "Update website content"
git push
```

<span style="color:#b54708"><strong>不要改：</strong></span>

- `_site/`
- `.jekyll-cache/`
- `vendor/`

这些目录是构建输出或依赖目录，不是日常内容编辑入口。
