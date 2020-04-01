---
title: Term
layout: default
feature_text: <h2>Sort by terms</h2>
feature_image: "https://picsum.photos/1300/400?image=989"
---
<main class="main container">
    <div class="content">

        <p>You can click the <i>term heading</i> (e.g. <a href="#">Fall 2017</a>) to view other courses I have audited, which may have incomplete notes and some remarks.</p>

        <br><br><br>
        <!-- my code -->
        {% assign all_terms = site.term | reverse %}

        {% for item in all_terms %}
        {% assign courses = site.posts | where: "term", item.term | where: "hide", false %}
                <div class="typeset" style="border: 1px solid #EEEEEE; padding: 1em; border-radius: 0.3em;">
                    <h1 align="center" style="font-size:2em"><a href="{{ item.url }}">{{ item.feature_text | split: "|" | last | strip_html }}</a></h1>
                    <ul>
                        {% for c in courses %}
                        <span class="label label--category"><a href="{{ c.url }}" class="post-tag" style="white-space: nowrap">{{ c.title }}</a></span> &nbsp;&nbsp;
                        {% endfor %}
                    </ul>
                </div>
            <br>
        {% endfor %}
    </div>
</main>
