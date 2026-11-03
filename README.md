# Watchstep's Resume

- English: <https://watchstep.site/>
- Korean: <https://watchstep.site/kr/>

## Setup

### 1. Install Ruby

Install Ruby with [RubyInstaller for Windows](https://rubyinstaller.org/downloads/) or Homebrew on macOS.

```bash
brew install ruby
ruby -v
```

### 2. Install dependencies

```bash
gem install bundler
bundle config set --local path vendor/bundle
bundle install
```

### 3. Run locally

```bash
bundle exec jekyll serve
```

Open the pages in a browser:

- English: <http://localhost:4000/>
- Korean: <http://localhost:4000/kr/>

### 4. Build

```bash
bundle exec jekyll build
```

The build output is written to `_site/`.

## Resume data

Each language has a separate YAML file.

| Language | Data file | Page |
| --- | --- | --- |
| English | `_data/resume/en.yml` | `/` |
| Korean | `_data/resume/kr.yml` | `/kr/` |

Keep matching entries in the same order across both files. Language-specific contacts can differ. KakaoTalk is included only in the Korean data.

## Edit the resume

### Profile

| Field | Type | Description |
| --- | --- | --- |
| `title` | String | Browser tab title |
| `name` | String | Name |
| `jobtitle` | String | Job title |
| `about` | String list | Introductory lines |
| `contact` | Object list | Contact icons and links |

```yaml
title: watchstep's resume
name: Juii Kim
jobtitle: AI Engineer
about:
  - First introduction line
contact:
  - name: email
    url: mailto:example@example.com
  - name: blog
    label: Blog
    url: https://example.com/blog
  - name: github
    url: https://github.com/example
```

`contact.name` must match an icon name in `_includes/svg.html`.
The optional `contact.label` is used as the icon's accessible label and hover title.

### Education

```yaml
education:
  - university: Yonsei University
    duration: Mar 2020 - Feb 2025
    location: Seoul, South Korea
    major: Double Major in Library and Information Science and Applied Statistics
    gpa: 3.92 / 4.3
```

Education entries use `university`, `duration`, `location`, and `major`. The optional `gpa` field is displayed below the major.

### Experience, projects, and activities

| Section | YAML key |
| --- | --- |
| Experience | `work_experience` |
| Projects | `projects` |
| Activities | `extracurricular_activities` |

These sections use the same fields.

```yaml
work_experience:
  - title: AI Engineer
    org: JINHAKSA
    url: https://example.com
    duration: Jan 2025 - Present
    about: Optional subtitle
    description: Optional description
    description_url: https://example.com/details
    highlights:
      - First achievement
      - title: Detailed achievement title
        description: >-
          A longer explanation displayed below the bold title. Existing string
          highlights and structured highlights can be used together.
```

| Field | Required | Description |
| --- | --- | --- |
| `title` | Yes | Role, project, or activity name |
| `duration` | Yes | Date range |
| `org` | No | Organization |
| `url` | No | External link |
| `about` | No | Subtitle shown beside the date range |
| `description` | No | Summary |
| `description_url` | No | Link icon displayed beside the description |
| `highlights` | No | List of string highlights or `title`/`description` objects |

Entries appear in YAML order. Quote strings that contain a colon. Trusted HTML such as `<b>text</b>` is rendered as HTML. Links added with `<a href="https://example.com">text</a>` inside descriptions or highlights automatically use the accent-colored underline style.

---

Based on the [crispgm/resume](https://github.com/crispgm/resume/tree/master) Jekyll theme. See the [Jekyll documentation](https://jekyllrb.com/docs/) for more details.
