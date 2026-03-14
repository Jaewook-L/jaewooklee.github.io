---
layout: single
title: "Publications"
permalink: /publications/
author_profile: true
---
{% if site.author.googlescholar %}
  You can also find my articles on <u><a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

## Under Review / In Revision

{% assign under_review = "" | split: "" %}
{% for item in site.publications %}
  {% if item.venue == "Under Review" or item.venue == "In Revision" %}
    {% assign under_review = under_review | push: item %}
  {% endif %}
{% endfor %}
{% assign under_review = under_review | sort: "date" | reverse %}
{% for post in under_review %}
  {% include archive-single.html %}
{% endfor %}

## In Preparation

{% assign in_prep = "" | split: "" %}
{% for item in site.publications %}
  {% if item.venue == "In Preparation" %}
    {% assign in_prep = in_prep | push: item %}
  {% endif %}
{% endfor %}
{% assign in_prep = in_prep | sort: "date" | reverse %}
{% for post in in_prep %}
  {% include archive-single.html %}
{% endfor %}

## Published Journal Articles

{% assign published = "" | split: "" %}
{% for item in site.publications %}
  {% if item.category == "manuscripts" and item.venue != "Under Review" and item.venue != "In Revision" and item.venue != "In Preparation" %}
    {% assign published = published | push: item %}
  {% endif %}
{% endfor %}
{% assign published = published | sort: "date" | reverse %}
{% for post in published %}
  {% include archive-single.html %}
{% endfor %}

## Book Chapters

{% assign books = site.publications | where: "category", "books" | sort: "date" | reverse %}
{% for post in books %}
  {% include archive-single.html %}
{% endfor %}
