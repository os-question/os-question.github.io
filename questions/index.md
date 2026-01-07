---
title: Questions
layout: default
---

# Questions

Welcome to the Questions section of OS-QUESTION.  
Below are the articles currently available:

{% comment %}
自动生成文章列表，排除当前首页 index.md
文章 Front Matter 中可以添加 nav_exclude: true 来隐藏
{% endcomment %}

<ul>
{% for page in site.pages %}
  {% if page.path contains 'questions/' and page.path != 'questions/index.md' %}
    {% if page.title %}
      <li>
        <a href="{{ page.url | relative_url }}">{{ page.title }}</a>
      </li>
    {% endif %}
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
