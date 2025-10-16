---
layout: page
title: Courses
permalink: /courses-list/
nav: true
description: List of paid courses offered by Creative Net.
nav_order: 7
---

<h2>Jekyll Static Files Check</h2>
<pre>{{ site.static_files | jsonify }}</pre>

<h2>Filtered Collection Check</h2>
{% assign course_files = site.static_files | where: 'collection', 'courses' %}
<pre>{{ course_files | jsonify }}</pre>

{% tabs Courses %}

{% tab Courses Current-Course-List %}
{% include course_listing_loop.liquid archive_status="current" %}
{% endtab %}

{% tab Courses Archived-Course-List %}
{% include course_listing_loop.liquid archive_status="archived" %}
{% endtab %}

{% endtabs %}
