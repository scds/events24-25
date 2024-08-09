---
layout: home
title: Home
nav_order: 1
has_toc: false

# Set this to "false" if you removed 'previousOffering.md'
has_children: false 
---

{%- assign workshops = site.pages 
    | where_exp: "item", "item.grand_parent == null"
    | where_exp: "item", "item.parent == null"
    | where_exp: "item", "item.nav_exclude != true"
    | sort: "title" 
-%}

<img src="assets/img/titleSlide.png" alt="Workshop Title Slide" width="100%">

<!-- Main header -->
# Welcome to the 2024-2025 Special Events Page

This page contains event recordings of some special events that were held in the 2024-2025 year offering.

## 2024-25 Special Events

<div markdown="1" style="border: 1px solid #7a003c; border-radius: 6px; margin-bottom: 1em; padding: 0.5em 1em 0; margin-top: 1em;" class="toc">
<summary style="cursor:default; display: block; border-bottom: 1px solid #302d36; margin-bottom: 0.5em">
  Workshops
</summary>
<ul>
{% for workshop in workshops %}
{% if workshop.title != null and workshop.title != "Home" %}
<li><a href="{{workshop.url | absolute_url}}">{{workshop.title}}</a></li>
{% endif %}
{% endfor %}
</ul>
</div>

## Land Acknowledgment

{% include def/land_ack.md %}