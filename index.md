---
layout: page
title: Brian Hicks
tagline: Be Good.
---
{% include JB/setup %}

Hey there. I'm Brian Hicks. How do you do? You can see I've been blogging here.
If you want to see more things I've done and said, follow the links in the
footer. That's all for now!

<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
