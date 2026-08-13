---
title: Articles
description: Research notes by Milap Rajgor on topology, molecular dynamics, and scientific reasoning.
permalink: /articles/
---
<header class="page-hero"><div class="shell page-hero-inner"><p class="index">Research / Articles</p><h1>Ideas in progress,<br><em>explained carefully.</em></h1><p>Research notes on topology, molecular dynamics, and the boundary between an interesting signal and a defensible scientific claim.</p></div></header>
<section class="page-section shell"><p class="label">Research notes</p><div><h2>Latest articles</h2><div class="article-list">{% for post in site.posts %}<article><p class="article-date">{{ post.date | date: "%B %-d, %Y" }}</p><h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3><p>{{ post.description }}</p><a class="article-read" href="{{ post.url | relative_url }}">Read article <span aria-hidden="true">→</span></a></article>{% endfor %}</div></div></section>
