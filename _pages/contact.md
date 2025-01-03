---
layout: page
title: Contact Us
permalink: /contact/
description: Contact details for Creative Net.
nav: true
nav_order: 9
horizontal: false
---

## Contact Person
Dhruva Shaw

## Email Address
(creativenet@dhruvashaw.in)[mailto:creativenet@dhruvashaw.in]

## Registered Office Address
1267, Ostad Amir Khan Sarani, Kolkata, West Bengal, India - 700082


<!-- Social -->
{% if page.social %}
    <div class="social">
        <div class="contact-icons">{% include social.liquid %}</div>
    <div class="contact-note">{{ site.contact_note }}</div>
    </div>
{% endif %}
