---
layout: page
title: Home
id: home
permalink: /
---

## 카오의 2nd Brain 창고에 오신 것을 환영합니다! 🌱

<p style="padding: 3em 1em; background: #f5f7ff; border-radius: 4px;">
  옵시디언으로 정리한 자료를 퍼블리싱하는 페이지 입니다. 
  개인적으로 사용하는 곳이나 혹시 들어오시는 분에게도 도움이 되길 바랍니다. 
</p>

<strong>Recently updated notes</strong>

<ul>
  {% assign recent_notes = site.notes | sort: "last_modified_at_timestamp" | reverse %}
  {% for note in recent_notes limit: 10 %}
    <li>
      {{ note.last_modified_at | date: "%Y-%m-%d" }} — <a class="internal-link" href="{{ note.url }}">{{ note.title }}</a>
    </li>
  {% endfor %}
</ul>

<style>
  .wrapper {
    max-width: 46em;
  }
</style>
