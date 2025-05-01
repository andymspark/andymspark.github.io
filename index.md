---
layout: home
---


{% assign projects = site.github.public_repositories
                     | where_exp:'p','p.fork == false'
                     | sort: 'pushed_at'
                     | reverse %}

<ul class="project-list">
{% for p in projects %}
  <li>
    <a href="/{{ p.name | url_encode }}/">{{ p.name }}</a>
    <small> — {{ p.description }}</small>
  </li>
{% endfor %}
</ul>
