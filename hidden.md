---
layout: default
---

<div>
  
  <h2>Hidden Posts</h2>

  <div>&nbsp;</div>

  <ul class="post-list">
    {% for post in site.posts %}
    {% capture postyear %}{{post.date | date: '%Y'}}{% endcapture %}
    {% if postyear == '2001' %}
      <li>
        {% if post.cover %}
            <img src="{{ post.cover }}" style="
                width: 100%;
                height: 100%;
                top: 0;
                left: 0;
                margin: auto;
                ">
        {% endif %}

        {% assign date_format = site.cayman-blog.date_format | default: "%b %-d, %Y" %}
        <span class="post-meta">{{ post.date | date: date_format }}</span>

        <h2>
          <a class="post-link" href="{{ post.url | relative_url }}" title="{{ post.title }}">{{ post.title | escape }}</a>
        </h2>

        <span>{{ post.excerpt | markdownify | truncatewords: 30 }}</span>

      </li>
    {% endif %}
    {% endfor %}
  </ul>

</div>