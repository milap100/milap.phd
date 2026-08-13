---
title: Publications
description: Publications by Milap Rajgor.
permalink: /publications/
---
<header class="page-hero shell"><p class="index">02 / Publications</p><h1>Published work &amp;<br><em>scholarly record.</em></h1><p>Publications will be listed with complete authorship, venue, year, and links to the paper or DOI.</p></header>
<section class="page-section shell"><p class="label">All publications</p><div><h2>Publications</h2>{% if site.data.publications.size > 0 %}<ol class="records publications">{% for item in site.data.publications %}<li><small>{{ item.status }}</small><h3>{% if item.url != "" %}<a href="{{ item.url }}">{{ item.title }}</a>{% else %}{{ item.title }}{% endif %}</h3><p>{{ item.authors }}</p><p>{{ item.venue }}</p>{% if item.note %}<p>{{ item.note }}</p>{% endif %}<nav>{% if item.url != "" %}<a href="{{ item.url }}">DOI / record ↗</a>{% endif %}{% if item.pdf != "" %}<a href="{{ item.pdf | relative_url }}">PDF ↓</a>{% endif %}</nav></li>{% endfor %}</ol>{% else %}<div class="empty">No publication entries have been added yet. This page is intentionally empty rather than populated with invented citations.</div>{% endif %}</div></section>
