---
layout: page
title: Write-ups
permalink: /writeups/
---

# Write-ups

Technical reports from labs, CTFs, and research, written in the same format I'd use for a client deliverable.

<ul>
  {% for post in site.writeups %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a> — {{ post.date | date: "%b %-d, %Y" }}
    </li>
  {% endfor %}
</ul>

---

*New write-ups are added as each phase of my [learning roadmap](https://github.com/your-github-handle/pentester-portfolio) is completed.*
