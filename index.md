---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
title: 🏠 Home
layout: home
nav_exclude: false
nav_order: 1
---

{% assign course_vars = site.data[site.data_folder].course %}
{% assign staff_vars = site.data[site.data_folder].staff %}
{% assign calendar = site.data[site.data_folder].calendar %}
{% assign staff = staff_vars[0] %} <!-- Cannot change this to instructor = because it will break the staffer.html include. If this needs to be instructor, then include.staff needs to be used as the variable in staffer.html  -->

# {{ site.tagline }}

{: .mb-2 }
{{ site.description }}
{: .fs-6 .fw-300 }

{{ course_vars.quarter }}
{: .md-badge-purple }

{{ course_vars.building }}
{: .md-badge-purple }

{{ course_vars.timings }}
{: .md-badge-purple }

{% include staffer.html staff=staff nobio='true' %}

{: .important }
If you are joining the course late and would still like to earn full credit for assignments, please **[read this](https://docs.google.com/document/d/1wNoespOvpfwMG5H4839B1Ap2KSnDMXlp3jQ-fbNBmWk/edit?tab=t.0#heading=h.l1tve2rn62el)**!

## Office Hours
* **Prof. Lai** : Tues, 2-3pm (<a href="https://calendar.app.google/1nebbtvdYdn6WFpw5" target="_blank" rel="noopener">book &#x2197;</a> only) @ CSB 244/Zoom OR Thurs, 2-3pm (walk-in) @ CSB244
* **TAs**: During discussion section
* **PLAs**: Friday, 12-2p @ Zoom AND CSB 180/courtyard

<!-- **{{ course_vars.announcement.text }}** -->

{% for week in calendar %}
  {% include week.html week=week %}
{% endfor %}
