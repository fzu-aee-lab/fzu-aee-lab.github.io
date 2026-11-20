---
title: 研究方向
permalink: /research/
---

我们围绕以下三个方向开展研究与项目实践。

{% for direction in site.data.lab.directions %}
<section class="lab-direction" id="direction-{{ forloop.index }}">
  <h2>{{ direction.title | escape }}</h2>
  {% if direction.description != empty %}<p>{{ direction.description | escape }}</p>{% endif %}
</section>
{% endfor %}

[查看项目实践]({{ '/projects/' | relative_url }}){: .btn .btn--primary}
