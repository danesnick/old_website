---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: home
title: Home
---

# Hello!

You've reached my little corner of the internet. This website is mostly about my blog, which talks about technology, privacy, minimalism & more. 

[More about me &#x2198;](/about/)

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

[Read more posts &#x2198;](/archive/)
