---
layout: blog
title: Blog
permalink: /blog/
---

## Recent Blog Posts
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


## Highlighted Posts
<table>
  <tr>
   <td>2021-03-11</td>
   <td><a href="/blog/2021/03/11/i-love-syncthing/">I Love Syncthing</a></td>
  </tr>
  <tr>
   <td>2021-01-28</td>
   <td><a href="/blog/2021/01/28/30plusdays-gentoo-experience/">My 30+ Days using Gentoo Linux: A Newbie's Perspective</a></td>
  </tr>
  <tr>
   <td>2021-01-10</td>
   <td><a href="/blog/2021/01/10/why-i-stopped-using-spotify/">Why I stopped using Spotify</a></td>
  </tr>
</table>


## Archived Posts
