---
title: Teaching
description: Teaching, mentoring, and course activities by Milap Rajgor.
permalink: /teaching/
---
<header class="page-hero"><div class="shell page-hero-inner"><p class="index">03 / Teaching</p><h1>Teaching &amp;<br><em>mathematical practice.</em></h1><p>A record of courses, teaching roles, mentoring, and selected instructional materials can be maintained here.</p></div></header>
<section class="page-section shell"><p class="label">Teaching record</p><div><h2>Courses &amp; activities</h2>{% if site.data.teaching.size > 0 %}<div class="records">{% for item in site.data.teaching %}<article><small>{{ item.term }}</small><h3>{{ item.course }}</h3><p>{{ item.role }}{% if item.institution != "" %} · {{ item.institution }}{% endif %}</p>{% if item.summary %}<p>{{ item.summary }}</p>{% endif %}</article>{% endfor %}</div>{% else %}<div class="empty">Teaching information will be added after course titles, roles, institutions, and terms are confirmed.</div>{% endif %}</div></section>
