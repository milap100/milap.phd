---
title: Research
description: Research interests and projects spanning mathematics, topology, biological structure, and scientific computing.
permalink: /research/
---
<header class="page-hero"><div class="shell page-hero-inner"><p class="index">01 / Research</p><h1>Research shaped by<br><em>structure and change.</em></h1><p>My work sits at the interface of mathematics and scientific questions about complex structure.</p></div></header>
<section class="page-section shell" id="projects"><p class="label">Projects</p><div><h2>Research projects</h2>{% if site.data.projects.size > 0 %}<div class="records">{% for item in site.data.projects %}<article><small>{{ item.status }} · {{ item.period }}</small><h3>{{ item.title }}</h3><p>{{ item.summary }}</p></article>{% endfor %}</div>{% else %}<div class="empty">Project descriptions will be added after the research titles, dates, and summaries are confirmed.</div>{% endif %}</div></section>
