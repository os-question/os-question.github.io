---
title: Questions
layout: default
---

# Questions

Welcome to the Questions section of **OS-QUESTION**.  
Below are the available articles, sorted by date (newest first).

{% comment %}
说明：
- 文章放在 questions/ 目录
- Front Matter 建议包含：
  ---
  title: "文章标题"
  date: 2026-01-05
  ---
- nav_exclude: true 可隐藏
{% endcomment %}

<ul class="question-list">
{% assign question_pages = site.pages
  | where_exp: "p", "p.path contains 'questions/'"
  | where_exp: "p", "p.path != 'questions/index.md'"
%}

{% for page in question_pages %}
  {% if page.title %}
    <li class="question-item">
      {% if page.date %}
        <span class="question-date">
          {{ page.date | date: "%Y-%m-%d" }}
        </span>
      {% endif %}
      <a class="question-title" href="{{ page.url | relative_url }}">
        {{ page.title }}
      </a>
    </li>
  {% endif %}
{% endfor %}
</ul>




---

<!--
使用说明：
1. 每篇文章文件放在 questions/ 目录下，Front Matter 必须至少包含：
   ---
   title: "文章标题"
   ---
2. 如果文章不希望在首页列表显示，加：
   nav_exclude: true
3. 每次新增文章 push 后，index.md 会自动生成列表，无需手动更新。
-->
