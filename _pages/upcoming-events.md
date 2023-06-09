---
permalink: /upcoming-events/
title: "Upcoming Events"
---

{% assign curDate = site.time | date: '%s' %}
{% assign sorted = site.posts| sort %}
{% for post in sorted %}
    {% assign postStartDate = post.date | date: '%s' %}
    {% if postStartDate >= curDate %}
        {% include archive-single.html type=entries_layout %}
    {% endif %}
{% endfor %}