# Team Mariana Website Editing Guide

<a id="brief-introduction"></a>

## 1. Brief Introduction

Website link: <https://mbelgiu.github.io/Team_Mariana/>

<span style="color:#0b6f6a"><strong>Key point:</strong></span> This repository contains a static website built with Jekyll and the al-folio theme. Most day-to-day edits are made in Markdown, YAML, BibTeX, image files, and a small amount of SCSS.

Current page source files are named after the navigation labels:

| Page | Source File | Production URL |
| --- | --- | --- |
| Home | `_pages/Home.md` | `/` |
| Research | `_pages/Research.md` | `/research/` |
| Publications | `_pages/Publications.md` | `/publications/` |
| Teams | `_pages/Teams.md` | `/teams/` |
| News | `_pages/News.md` | `/news/` |
| Teaching | `_pages/Teaching.md` | `/teaching/` |

Images are grouped by page:

```text
assets/img/home/       Home profile photo, ITC logo, and Home-related images
assets/img/research/   Research project images
assets/img/teams/      Team member portraits
```

Publish workflow:

```bash
git status
git add .
git commit -m "Update website content"
git push
```

After pushing to the `main` branch, GitHub Actions automatically rebuilds and redeploys the website.

<a id="content"></a>

## 2. Content

- [1. Brief Introduction](#brief-introduction)
- [2. Content](#content)
- [3. Home Page Editing](#home)
- [4. Research Page Editing](#research)
- [5. Publication Page Editing](#publication)
- [6. Teams Page Editing](#teams)
- [7. News Page Editing](#news)
- [8. Teaching Page Editing](#teaching)
- [9. Check and Publish](#check-and-publish)

<a id="home"></a>

## 3. Home Page Editing

Home page URL:

```text
https://mbelgiu.github.io/Team_Mariana/
```

Main files:

| Content | File |
| --- | --- |
| Page body | `_pages/Home.md` |
| ORCID, Google Scholar, email, RSS, and ITC icon | `_data/socials.yml` |
| Home images | `assets/img/home/` |
| Home styles | `_sass/_site.scss` |

### 3.1 Edit Page Title, Navigation Label, and URL

File: `_pages/Home.md`

Code block:

```yaml
---
layout: about
title: Home
permalink: /
subtitle: Associate Professor in GeoAI & multi-temporal remote sensing, <a href="https://www.itc.nl/">Faculty ITC, University of Twente</a>
---
```

Update:

- Change `title: Home` to change the navigation label.
- Change `subtitle` to update the subtitle on the Home page.
- Keep `permalink: /` unless you intentionally want to change the Home page URL.

Add:

```yaml
description: Research group website for Mariana Belgiu.
```

Delete:

- Do not delete `layout`, `title`, or `permalink`.
- If you delete `subtitle`, the Home page subtitle will disappear.

### 3.2 Edit Profile Photo and Contact Information

File: `_pages/Home.md`

Code block:

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

Update:

- Home profile images are stored in `assets/img/home/`.
- The current profile photo path is `assets/img/home/mariana-belgiu.jpg`.
- Edit the `<p>...</p>` lines inside `more_info` to update address, email, phone, or profile links.

Add:

```html
<p><a href="https://example.com">New profile link</a></p>
```

Delete:

- Delete one full `<p>...</p>` line to remove that item.

### 3.3 Edit the Home Introduction Text

File: `_pages/Home.md`

Code block:

```markdown
<div class="about-overview" markdown="1">

Dr. Mariana Belgiu is an Associate Professor ...

The group develops data-centric AI methods ...

</div>
```

Update:

- Edit the paragraphs between the opening and closing `div`.

Add:

```markdown
The group also collaborates with international partners on applied GeoAI projects.
```

Delete:

- Delete paragraphs that are no longer needed.
- Do not delete the outer `<div class="about-overview" markdown="1">` unless you also plan to change the styling.

### 3.4 Edit Research Themes

File: `_pages/Home.md`

Code block:

```markdown
## Research themes

- **Data-centric AI for Earth Observation:** methods for multi-temporal optical, hyperspectral, and radar imagery.
- **Learning with scarce labels:** robust and transferable algorithms for mapping crops, land cover, and urban environments.

<div class="expertise-tags" aria-label="Expertise keywords">
  <span>GeoAI</span>
  <span>Remote sensing</span>
</div>
```

Update:

- Edit list items to update research themes.
- Edit `<span>...</span>` items to update keyword tags.

Add:

```markdown
- **New research theme:** short description here.
```

```html
<span>New keyword</span>
```

Delete:

- Delete one `- **...:** ...` line to remove a research theme.
- Delete one `<span>...</span>` line to remove a keyword tag.

### 3.5 Edit Teaching and Community

File: `_pages/Home.md`

Code block:

```markdown
## Teaching and community

Mariana teaches optical remote sensing ...

She is active in EO4all ...
```

Update:

- Edit the heading or paragraphs directly.

Add:

- Add a new paragraph before the end of the section.

Delete:

- Delete any paragraph that is no longer needed.

### 3.6 Edit Home Footer Icons: ORCID, Google Scholar, Email, RSS, and ITC

File: `_data/socials.yml`

Code block:

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

Update:

- `orcid_id` controls the ORCID icon link.
- `scholar_userid` controls the Google Scholar icon link.
- `email` controls the email icon link.
- `rss_icon: true` displays the RSS icon.
- `custom_social.logo` controls the final custom image icon. It currently uses the ITC logo.
- `custom_social.url` controls where the ITC logo links.

Add:

- To replace the ITC logo, place the new file in `assets/img/home/`, then update:

```yaml
custom_social:
  logo: /assets/img/home/new-logo.png
```

Delete:

- To hide the RSS icon:

```yaml
rss_icon: false
```

- To hide the final ITC icon, delete the full `custom_social:` block.

<span style="color:#0b6f6a"><strong>Key point:</strong></span> Home footer icons are edited in `_data/socials.yml`, not in `_pages/Home.md`.

<a id="research"></a>

## 4. Research Page Editing

Research page URL:

```text
https://mbelgiu.github.io/Team_Mariana/research/
```

Main files:

| Content | File |
| --- | --- |
| Page introduction and highlighted projects | `_pages/Research.md` |
| Research cards | `_projects/*.md` |
| Research images | `assets/img/research/` |

### 4.1 Edit Page Title and Navigation

File: `_pages/Research.md`

Code block:

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

Update:

- `title` controls the navigation label.
- `description` controls the page description.
- `nav_order` controls the navigation order.

Add:

```yaml
display_categories: [research, new-category]
```

Delete:

- To hide the page from the navigation bar:

```yaml
nav: false
```

### 4.2 Edit Research Overview and Keywords

File: `_pages/Research.md`

Code block:

```markdown
## Research overview

Mariana Belgiu's research develops GeoAI ...

<div class="expertise-tags" aria-label="Research expertise">
  <span>Remote sensing</span>
  <span>GeoAI</span>
</div>
```

Update:

- Edit the paragraphs to update the research overview.
- Edit `<span>...</span>` items to update keywords.

Add:

```html
<span>New expertise</span>
```

Delete:

- Delete any `<span>...</span>` item that is no longer needed.

### 4.3 Edit Selected Funded Projects and Networks

File: `_pages/Research.md`

Code block:

```html
<article class="project-highlight">
  <h3>EO4Nutri</h3>
  <p>ESA-funded work using Earth Observation and spatial data ...</p>
  <span>2023-2025</span>
</article>
```

Update:

- `<h3>` is the project name.
- `<p>` is the project description.
- `<span>` is the project period.

Add:

```html
<article class="project-highlight">
  <h3>New Project</h3>
  <p>Short project description.</p>
  <span>2026-2028</span>
</article>
```

Delete:

- Delete one full `<article class="project-highlight"> ... </article>` block.

### 4.4 Edit Research Cards

Folder: `_projects/`

Example file: `_projects/data-centric-eo.md`

Code block:

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

Update:

- `title` updates the card title.
- `description` updates the card summary.
- `img` updates the card image. Research images should usually be stored in `assets/img/research/`.
- `importance` controls ordering. Smaller numbers appear earlier.

Add:

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

Delete:

- Delete the corresponding `.md` file in `_projects/` to remove the card.

<a id="publication"></a>

## 5. Publication Page Editing

Publication page URL:

```text
https://mbelgiu.github.io/Team_Mariana/publications/
```

Main files:

| Content | File |
| --- | --- |
| Page structure, Google Scholar summary, citation chart | `_pages/Publications.md` |
| Publication list | `_bibliography/papers.bib` |
| Venue abbreviations | `_data/venues.yml` |
| Scholar block styles | `_sass/_site.scss` |

### 5.1 Edit Page Title and Navigation

File: `_pages/Publications.md`

Code block:

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

Update:

- Change `title` to update the navigation label.
- Change `description` to update the page description.

Delete:

- To hide the page from the navigation bar, set `nav: false`.

### 5.2 Edit Google Scholar Citation Summary

File: `_pages/Publications.md`

Code block:

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

Update:

- Edit the numbers for `Citations`, `h-index`, and `i10-index`.

Add:

```html
<tr>
  <th scope="row">New metric</th>
  <td>100</td>
  <td>80</td>
</tr>
```

Delete:

- Delete the corresponding `<tr> ... </tr>` row.

### 5.3 Edit the Citation Bar Chart

File: `_pages/Publications.md`

Code block:

```html
<div class="scholar-chart__bar" style="--height: 32%">
  <span class="scholar-chart__year">2019</span>
  <span class="scholar-chart__value">704</span>
</div>
```

Update:

- `--height` controls the visual bar height.
- `scholar-chart__year` controls the year label.
- `scholar-chart__value` controls the value shown on hover.
- The preview chart and modal chart each have their own copy of the data. Usually you need to update both.

Add:

```html
<div class="scholar-chart__bar" style="--height: 60%">
  <span class="scholar-chart__year">2027</span>
  <span class="scholar-chart__value">1320</span>
</div>
```

Delete:

- Delete one full `scholar-chart__bar` block.

### 5.4 Edit Public Access

File: `_pages/Publications.md`

Code block:

```html
<span class="scholar-access__closed">2 articles not available</span>
<span class="scholar-access__open">29 articles available</span>
```

Update:

- Edit the article counts.

Delete:

- Delete the full `<div class="scholar-access"> ... </div>` block to remove the Public access section.

### 5.5 Edit Publication Entries

File: `_bibliography/papers.bib`

Code block:

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

Update:

- Edit `title`, `author`, `journal`, `year`, and other BibTeX fields.
- `selected = {true}` makes the paper appear in the Home page selected publications list.

Add:

- Add a new BibTeX entry at the end of `papers.bib`.

Delete:

- Delete one full `@article{...}` or `@misc{...}` entry.

<a id="teams"></a>

## 6. Teams Page Editing

Teams page URL:

```text
https://mbelgiu.github.io/Team_Mariana/teams/
```

Main files:

| Content | File |
| --- | --- |
| Teams page entry | `_pages/Teams.md` |
| PI profile text | `_pages/people_director.md` |
| Student and alumni list | `_pages/people_students.md` |
| Member portraits | `assets/img/teams/` |

### 6.1 Edit the Teams Page Entry

File: `_pages/Teams.md`

Code block:

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

Update:

- `image` controls the PI image.
- `content: people_director.md` means the PI text comes from `_pages/people_director.md`.
- `content: people_students.md` means the student list comes from `_pages/people_students.md`.

Delete:

- Delete `- content: people_students.md` to hide the student list.

### 6.2 Edit the PI Profile

File: `_pages/people_director.md`

Code block:

```markdown
### Dr. Mariana Belgiu

Mariana Belgiu is an Associate Professor ...

<dl class="profile-contact">
  <dt>Email</dt>
  <dd><a href="mailto:m.belgiu@utwente.nl">m.belgiu@utwente.nl</a></dd>
</dl>
```

Update:

- Edit the heading, paragraphs, `<dt>`, and `<dd>` values.

Add:

```html
<dt>Office</dt>
<dd>Langezijds 1326, University of Twente</dd>
```

Delete:

- Delete one pair of `<dt>...</dt>` and `<dd>...</dd>`.

### 6.3 Edit Current PhD Researchers

File: `_pages/people_students.md`

Code block:

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

Update:

- Edit the name, study period, research interests, and email.
- Store member portraits in `assets/img/teams/`.

Add:

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

Delete:

- Delete one full `<article class="team-member"> ... </article>` block.

### 6.4 Edit Alumni

File: `_pages/people_students.md`

Update:

- Alumni entries use the same structure as Current PhD Researchers.
- Edit the `<article class="team-member">` blocks inside the Alumni section.

Add:

- Add a new `<article>` block inside the Alumni `<section>`.

Delete:

- Delete the full `<article>` block for the alumni entry you want to remove.

<a id="news"></a>

## 7. News Page Editing

News page URL:

```text
https://mbelgiu.github.io/Team_Mariana/news/
```

Main files:

| Content | File |
| --- | --- |
| News page entry | `_pages/News.md` |
| News items | `_news/*.md` |
| Number of News items on Home | `_pages/Home.md` |

### 7.1 Edit the News Page Entry

File: `_pages/News.md`

Code block:

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

Update:

- Edit `title` and `nav_order`.

Delete:

- Do not delete `{% include news.liquid %}` because it renders the News list.

### 7.2 Add a News Item

Folder: `_news/`

Add:

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

Update:

- Edit `title`, `date`, `inline`, and the body text.

Delete:

- Delete the corresponding `_news/*.md` file.

### 7.3 Edit the Number of News Items on Home

File: `_pages/Home.md`

Code block:

```yaml
announcements:
  enabled: true
  scrollable: true
  limit: 5
```

Update:

- Change `limit` to control how many News items appear on the Home page.

Delete:

```yaml
announcements:
  enabled: false
```

<a id="teaching"></a>

## 8. Teaching Page Editing

Teaching page URL:

```text
https://mbelgiu.github.io/Team_Mariana/teaching/
```

Main files:

| Content | File |
| --- | --- |
| Teaching page introduction | `_pages/Teaching.md` |
| Course items | `_teachings/*.md` |

### 8.1 Edit Teaching Page Title and Introduction

File: `_pages/Teaching.md`

Code block:

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

Update:

- Edit `title`, `description`, and the introductory paragraph.

Delete:

- To hide the page from the navigation bar, set `nav: false`.

### 8.2 Edit Teaching Areas

File: `_pages/Teaching.md`

Code block:

```markdown
## Teaching areas

- Optical remote sensing and image analysis.
- Machine learning and deep learning for geospatial sciences.
```

Update:

- Edit the list items.

Add:

```markdown
- New teaching area.
```

Delete:

- Delete list items that are no longer needed.

### 8.3 Edit Course Items

Folder: `_teachings/`

Example:

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

Update:

- Edit `title`, `description`, `year`, `term`, `location`, and the body text.

Add:

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

Delete:

- Delete the corresponding course file in `_teachings/`.

<a id="check-and-publish"></a>

## 9. Check and Publish

Local build check:

```bash
../conda-ruby/bin/bundle exec jekyll build
```

Local preview:

```bash
../conda-ruby/bin/bundle exec jekyll serve --host 127.0.0.1 --port 4001 --baseurl '' --livereload --livereload-port 35731
```

Open in the browser:

```text
http://127.0.0.1:4001/
```

Publish online:

```bash
git status
git add .
git commit -m "Update website content"
git push
```

<span style="color:#b54708"><strong>Do not edit:</strong></span>

- `_site/`
- `.jekyll-cache/`
- `vendor/`

These directories are generated output or dependency folders. They are not normal content editing entry points.
