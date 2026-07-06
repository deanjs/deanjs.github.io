# CLAUDE.md

## Notion Markdown Conversion Rules

When given a .md file exported from Notion, convert it to Chirpy format following the rules below.

### 0. Required input checklist
When a Notion .md file is given, ask for the following before converting:

- [ ] title
- [ ] date (YYYY-MM-DD)
- [ ] categories [대분류, 소분류]
- [ ] description

Then suggest appropriate tags based on the content.

### 1. Add front matter
Add the following at the top of the file.

---
title: "Title"
date: YYYY-MM-DD 00:00:00 +0900
categories: [Category, Subcategory]
tags: [tag1, tag2]
math: true
toc: true
description: "One-line description"
---

### 2. Notion callout conversion

Convert `<aside>` blocks to Chirpy prompt boxes based on the color label written at the top of the callout.
- 초록 → `{: .prompt-tip}`
- 파랑 → `{: .prompt-info}`
- 노랑 → `{: .prompt-warning}`
- 빨강 → `{: .prompt-danger}`

Example:
> 내용
{: .prompt-info}

### 3. Image paths
- Convert `![...](폴더명/image.png)` → `![...](/assets/img/posts/폴더명/image.png)`
- Extract images into `assets/img/posts/폴더명/` folder

### 4. Code block filename
- If a comment with filename exists above a code block, add it as `# file: "파일명"`
- If no filename comment exists, just use the language name

### 5. Output
- Filename: `YYYY-MM-DD-제목.md`
- Place in `_posts/` folder