---
layout: page
title: Courses Offered
permalink: /courses/
---

<ul class="nav nav-tabs" id="courseTabs" role="tablist">
  <li class="nav-item">
    <a class="nav-link active" href="/courses/">Current Courses</a>
  </li>
  <li class="nav-item">
    <a class="nav-link" href="/courses/archive/">Archived Courses</a>
  </li>
</ul>
<br>

<h2>Current Course List</h2>
{% include course_listing_loop.liquid archive_status="current" %}
