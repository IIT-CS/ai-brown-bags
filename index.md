{% assign revsem = site.data.brown-bags | reverse %}
{% for sem in revsem %}

# {{ sem.semester }}

In {{ sem.semester }}  the group is meeting {{ sem.day }} at {{ sem.time }} in {{ sem.room }} unless indicated otherwise

{% assign revtalks = sem.presentations | reverse %}

  {% for talk in revtalks %}

## {{ talk.date }} -  {{ talk.speaker }} - {{ talk.title }}
- **Title:** {{ talk.title }}
- **Type of talk**: {{ talk.type }}
- **Speaker**: {% if talk.speakerlink %}[{{ talk.speaker }}]({{ talk.speakerlink }}){% else %}{{ talk.speaker }}{% endif %}
- **Room:** {% if talk.room %}{{ talk.room }}{% else %}{{ sem.room }}{% endif %}
- **Date and Time:**  {{ talk.date }} - {% if talk.time %}{{ talk.time }}{% else %}{{ sem.time }}{% endif %}

{% if talk.abstract %}
### Abstract

{{ talk.abstract }}
{% endif %}

{% if talk.bio %}
### Bio

{{ talk.bio }}
{{ talk.bio }}
{% endif %}


	{% endfor %}
{% endfor %}
