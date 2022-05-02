---
layout: default
permalink: /publications/
---

## MEME and SEEDS Publications

{% comment %}
Get the set twice: once to do the year groups, then again to make the actual list inside the years. Since it is a sub-set it grabs the items for just that year.
{% endcomment %}


{% assign citations = site.data.publications |  sort: "date" | reverse | group_by: "date"  %}


{% for citation in citations %}
<h3>{{ citation.name }}</h3>

  <ul class="pubs">
  {% assign itemsSorted = citation.items | sort: "date" | reverse %}
  {% for item in itemsSorted %}<li>{{item.citation}}        
    {% for link in item.links %}
      {% if link.url %}<a href="{{link.url}}" target="_blank">[{{link.linklabel}}]</a>
      {% endif %}
    {% endfor %}
    </li>
  {% endfor %}
  </ul>
{% endfor %}

