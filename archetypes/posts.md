---
title: "{{ replace .File.ContentBaseName "-" " " | title }}"
date: {{ .Date | time.Format "2006-01-02" }}
tags: []
categories: []
summary: ""
draft: true
---

Write in plain Markdown. LaTeX math works out of the box:
inline $E = mc^2$, or display math:

$$
\mathcal{L} = -\sum_{i} y_i \log \hat{y}_i
$$

Put images next to this file and reference them as `![caption](image.png)`.
Delete this placeholder text before publishing.
