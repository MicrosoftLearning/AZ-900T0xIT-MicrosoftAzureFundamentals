---
title: Istruzioni ospitate online
permalink: index.html
layout: home
---

# Directory di contenuti

Collegamenti ipertestuali a ogni procedura dettagliata. Gli istruttori possono scegliere di usare la procedura dettagliata come dimostrazione o come lab per gli studenti. 

## Procedure dettagliate

{% assign wts = site.pages | where_exp:"page", "page.url contains '/Instructions/Walkthroughs'" %}
| Modulo | Procedura dettagliata |
| --- | --- | 
{% for activity in wts %}| {{ activity.wts.module }} | [{{ activity.wts.title }}{% if activity.wts.type %} - {{ activity.wts.type }}{% endif %}]({{ site.github.url }}{{ activity.url }}) |
{% endfor %}

