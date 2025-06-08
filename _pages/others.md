---
layout: page
title: others
description: A growing collection of misc projects
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
permalink: /others/ # others will be in page [blabla..].io/others/
---

In my free time, I like to stay active and try new challenges: specially running, cycling and swimming. I started keeping track of some of the sports events and activities I’ve been part of below.
Still need to add some more!

<!-- pages/projects.md -->
<div class="projects">

  <!-- Display categorized projects -->

{% for category in page.display_categories %}
<a id="{{ category }}" href=".#{{ category }}">
<h2 class="category">{{ category }}</h2>
</a>
{% assign categorized_projects = site.projects | where: "category", category %}
{% assign sorted_projects = categorized_projects | sort: "importance" %}
<!-- Generate cards for each project -->
<div class="row row-cols-1 row-cols-md-3">
{% for project in sorted_projects %}
{% include projects.liquid %}
{% endfor %}
</div>
{% endfor %}

</div>
