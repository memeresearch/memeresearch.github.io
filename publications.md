---
layout: default
permalink: /publications/
---

## MEME and SEEDS Publications
{% comment %}
  Note, using projects so that I can re-use this code across RAPT Lab websites 
{% endcomment %}

{% assign citations = site.data.publications | where: "project", "SEEDS" | group_by: "project" | sort: "value" %}
{% for citation in citations %}
  {% comment %} Remove the comments below this if we want to see a project name for each set {% endcomment %}
  {% comment %}<h3>{{ citation.name }}</h3>{% endcomment %}
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
