---
layout: page
title: Careers
permalink: /careers/
description: Explore career opportunities at Creative Net.
nav: false
---

{% for job in site.data.careers %}
<div class="job-listing">
  <h3>{{ job.title }}</h3>
  {% if job.department %}
    <p><strong>Department:</strong> {{ job.department }}</p>
  {% endif %}
  <p><strong>Location:</strong> {{ job.location }}</p>
  <p>{{ job.description }}</p>
  <a href="{{ job.apply_url }}" target="_blank" >Apply Now</a>
</div>
{% endfor %}

---
We are always looking for talented and passionate individuals to join our team. You can fill in the talent form below, and we will get back to you if there is a suitable opportunity.

<a href="https://forms.gle/Sfk2RaKhYb474yHk9" target="_blank" rel="noopener noreferrer">Talent Form</a>
