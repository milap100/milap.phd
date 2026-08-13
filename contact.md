---
title: Contact
description: Contact Milap Rajgor about research, teaching, and academic work.
permalink: /contact/
---
<header class="page-hero"><div class="shell page-hero-inner"><p class="index">06 / Contact</p><h1>Let’s begin a<br><em>research conversation.</em></h1><p>For questions about research, academic collaboration, or teaching, use the contact details below.</p></div></header>
<section class="page-section shell"><p class="label">Contact</p><div><h2>Write to me</h2>{% if site.data.profile.email != "" %}<a class="email" href="mailto:{{ site.data.profile.email }}">{{ site.data.profile.email }} ↗</a>{% else %}<div class="empty">An email address has not been published yet. Add it in <code>_data/profile.yml</code> when ready.</div>{% endif %}<nav class="contact-links">{% if site.data.profile.scholar_url != "" %}<a href="{{ site.data.profile.scholar_url }}">Google Scholar ↗</a>{% endif %}{% if site.data.profile.orcid_url != "" %}<a href="{{ site.data.profile.orcid_url }}">ORCID ↗</a>{% endif %}{% if site.data.profile.github_url != "" %}<a href="{{ site.data.profile.github_url }}">GitHub ↗</a>{% endif %}{% if site.data.profile.linkedin_url != "" %}<a href="{{ site.data.profile.linkedin_url }}">LinkedIn ↗</a>{% endif %}</nav></div></section>
