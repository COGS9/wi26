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
If you are joining the course late and would still like to earn full credit for assignments, you **MUST**: (1) email Prof. Lai + your section TA/PLA (see [syllabus](https://docs.google.com/document/d/1G8SD9n54daiYbeYOqWQfL4beGwLJiq4AFJvM7zNcmX0/edit?usp=sharing)) **before the end of Week 3** letting us know that you joined the course late so we don’t count your work late. (2) Read the [course syllabus](https://docs.google.com/document/d/1G8SD9n54daiYbeYOqWQfL4beGwLJiq4AFJvM7zNcmX0/edit?usp=sharing) and catch up on missed lectures (see podcast) (3) submit all missed assignments (R1 quiz + Pre-course survey + Syllabus quiz + R2 quiz) by **Friday 11:59pm of Week 3**. No other assignments after those in Weeks 1 & 2 will be accepted late in this fashion.

## Office Hours
* **Prof. Lai** : Tues, 2-3pm** ([book](https://calendar.app.google/1nebbtvdYdn6WFpw5) only) @ CSB 244/Zoom OR Thurs, 2-3pm** (walk-in) @ CSB244
* **TAs**: During discussion section
* **PLAs**: Friday, 12-2p @ Zoom AND CSB 180

<!-- **{{ course_vars.announcement.text }}** -->

{% for week in calendar %}
  {% include week.html week=week %}
{% endfor %}
