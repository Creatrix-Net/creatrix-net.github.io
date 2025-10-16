---
layout: page
title: Courses Offered
permalink: /courses-list/
nav: true
description: List of paid courses offered by Creative Net.
nav_order: 7
---

{% tabs Courses %}

{% tab Courses Current-Course-List %}
{% include course_listing_loop.liquid archive_status="current" %}
{% endtab %}

{% tab Courses Archived-Course-List %}
{% include course_listing_loop.liquid archive_status="archived" %}
{% endtab %}

{% endtabs %}
