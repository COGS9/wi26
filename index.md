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
If you are joining the course late and would still like to earn full credit for assignments, please **[read this](https://docs.google.com/document/d/1i3c8oN-QEdW7sisnoAQkgKoKgPBzV5TmuyMYZFJyl_A/edit?tab=t.0#heading=h.l1tve2rn62el)**! Please also note that I have **no control over the waitlist**. Please email [cogsadvising@ucsd.edu](mailto:cogsadvising@ucsd.edu) or drop in their office hours (your best bet)!

## Office Hours
* **Prof. Lai**:
  * Tues, 1-2:30pm (1-1, <a href="https://calendar.app.google/1nebbtvdYdn6WFpw5" target="_blank" rel="noopener">book &#x2197;</a> only) @ CSB 244 or Zoom
  * Tues, 2:45-4pm (open office hours, walk-in!) @ <a href="https://maps.app.goo.gl/cb1DK2ASsVHa4G3j6" target="_blank" rel="noopener">CSB Courtyard &#x2197;</a> 
* **TAs**: During discussion section
* **PLAs**:
  * Mon, 1-2pm @ <a href="https://maps.app.goo.gl/cb1DK2ASsVHa4G3j6" target="_blank" rel="noopener">CSB Courtyard &#x2197;</a>  (in-person only!) with Alex Nieto
  * Mon, 4-5pm @ <a href="https://ucsd.zoom.us/j/97813903283" target="_blank" rel="noopener">Zoom &#x2197;</a> with Gabriel Lopes
  * Mon, 7-8p @ <a href="https://us04web.zoom.us/j/72088395540?pwd=TrQUUxSnrNZHbf8wORdA2KOfVJ85VS.1" target="_blank" rel="noopener">Zoom &#x2197;</a> with Yash Date
  * Tues, 2-3pm, @ HDSI 155 + <a href="https://ucsd.zoom.us/j/92992107788" target="_blank" rel="noopener">Zoom &#x2197;</a> with Amelia Oo + Tanvi Vidyala
  * Tues, 5-6pm, @ HDSI 155 + <a href="https://ucsd.zoom.us/j/96480924664?pwd=e4vv2dLOVtLbSIx6JYjDi9rLh4Z18a.1" target="_blank" rel="noopener">Zoom &#x2197;</a> with Michael Yang

<!-- **{{ course_vars.announcement.text }}** -->

{% for week in calendar %}
  {% include week.html week=week %}
{% endfor %}
