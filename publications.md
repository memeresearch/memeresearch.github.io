---
layout: default
permalink: /publications/
---

## MEME and SEEDS Publications

{% assign groups = site.data.publications | group_by: "project" | sort: "value" %}
{% for group in groups %}
<h3>{{ group.name }}</h3><ul>
{% assign itemsSorted = group.items | sort: "date" | reverse %}
{% for item in itemsSorted %}<li>{{item.citation}}
  {% if item.link %} [{{item.linklabel}}]({{item.link}}) {% endif %}
  </li>{% endfor %}
</ul>
{% endfor %}
