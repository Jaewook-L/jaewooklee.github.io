---
layout: single
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

## Under Review / In Revision

{% assign under_review = site.publications | where_exp: "item", "item.venue == 'Under Review' or item.venue == 'In Revision'" | sort: 'date' | reverse %}
{% for post in under_review %}
  {% include archive-single.html %}
{% endfor %}

## In Preparation

{% assign in_prep = site.publications | where_exp: "item", "item.venue == 'In Preparation'" | sort: 'date' | reverse %}
{% for post in in_prep %}
  {% include archive-single.html %}
{% endfor %}

## Published Journal Articles

{% assign published = site.publications | where: "category", "manuscripts" | where_exp: "item", "item.venue != 'Under Review' and item.venue != 'In Revision' and item.venue != 'In Preparation'" | sort: 'date' | reverse %}
{% for post in published %}
  {% include archive-single.html %}
{% endfor %}

## Book Chapters

{% assign books = site.publications | where: "category", "books" | sort: 'date' | reverse %}
{% for post in books %}
  {% include archive-single.html %}
{% endfor %}
