---
layout: home
title: PDF
feature_image: "https://picsum.photos/1300/400?image=989"
feature_text: |
    ## PDF
---

{% assign dict = site.static_files | where_exp: 'a', "a.extname contains 'pdf'" | group_by_exp: "a", "a.path | truncate: 5, ''" %}

This page contains all pdf files on this site.

{% for group in dict %}
{% if group.name contains "cour" %}
<h1>Courses Routine</h1>
{% elsif group.name contains "pdfs" %}
<h1>Course Materials</h1>
{% elsif group.name contains "term" %}
<h1>Class Schedule</h1>
{% else %}
<h1>Other</h1>
{% endif %}
<ul>
{% for file in group.items %}
<li><a href="{{ file.path }}">{{ file.name }}</a></li>
{% endfor %}
</ul>
{% endfor %}
