---
layout: blog
title: Blog
permalink: /blog/
---

## Recent Posts
 {% assign posts = site.posts %}

  {%- if posts.size > 0 -%}
    {%- if page.list_title -%}
      <h2>{{ page.list_title }}</h2>
    {%- endif -%}
    <table>
      {%- assign date_format = site.date_format | default: "%b %-d, %Y" -%}
      {%- for post in posts limit:5 -%}
      <tr>
        <td>{{ post.date | date: site.date_format }}</td>
        <td><a href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a> </td>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </tr>
      {%- endfor -%}
    </table>
  {%- endif -%}


## Archived Posts
