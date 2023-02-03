---
layout: post
title:  "Using Mermaid charts on your GitHub Pages hosted Jekyll site"
date:   2023-02-03 15:00:00 +0000
categories: Code
mermaid: true
---

**Note:** if you add a code block in the top most of the page, the page loads the code block wrong and executes the html code instead of just showing it.



**I added mermaid chart compability by inserting the following in the \_includes\head.html file just before the closing \</head\> tag:**

{% raw %}
```liquid
{%- if page.mermaid -%}
   <script type="module">
    import mermaid from 'https://cdn.jsdelivr.net/npm/mermaid@9/dist/mermaid.esm.min.mjs';
    mermaid.initialize({ startOnLoad: true, theme: 'forest' });
  </script>
{%- endif -%}
```
{% endraw %}

**Adding a separate section showing only posts categorized as "Misc"**
1. I created a new file _misc.md_ in root folder.
2. I added misc.md under the _header_pages_ option in the _config.yml_ file.
3. Inside the misc.md file, I copied the yaml frontmatter from the about.md page and changed the _title_ and _permalink_ values. The _layout: page_ code ensures that the content of /layout/page.md is included, with the content of misc.md itself being placed inside the _\{\{ content \}\}_ section inside page.md.
4. The content of misc.md, is what comes after the frontmatter. I just copied this directly from the \layout\home.md file and only replaced _site.posts_ with _site.categories.misc_. I originally wanted to use _layout: home_ in the frontmatter and only write _assign site.posts = site.categories.misc_ in the content,  but this did not work, and I do not know wether this is due to site.posts being an object or if this assignment is overwritten by the content of home.md.

{% raw %}
```liquid
---
layout: page
title: Misc.
permalink: /misc/
---
  {%- assign posts = site.categories.Misc -%}

  {%- if posts.size > 0 -%}
    {%- if page.list_title -%}
      <h2 class="post-list-heading">{{ page.list_title }}</h2>
    {%- endif -%}
    <ul class="post-list">
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      {%- for post in posts -%}
      <li>
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {%- endfor -%}
    </ul>
  {%- endif %}
```
{% endraw %}

**Showing only posts tagged with "Code" on the front page**

The front page is defined by the \layouts\home.md file, which has the following code:

{% raw %}
```liquid
<div class="home">
  {%- if page.title -%}
    <h1 class="page-heading">{{ page.title }}</h1>
  {%- endif -%}

  {{ content }}

  {% if site.paginate %}
    {% assign posts = paginator.posts %}
  {% else %}
    {% assign posts = site.posts %}
  {% endif %}

  {%- if posts.size > 0 -%}
    {%- if page.list_title -%}
      <h2 class="post-list-heading">{{ page.list_title }}</h2>
    {%- endif -%}
    <ul class="post-list">
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      {%- for post in posts -%}
      <li>
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {%- endfor -%}
    </ul>

    {% if site.paginate %}
      <div class="pager">
        <ul class="pagination">
        {%- if paginator.previous_page %}
          <li><a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page">{{ paginator.previous_page }}</a></li>
        {%- else %}
          <li><div class="pager-edge">•</div></li>
        {%- endif %}
          <li><div class="current-page">{{ paginator.page }}</div></li>
        {%- if paginator.next_page %}
          <li><a href="{{ paginator.next_page_path | relative_url }}" class="next-page">{{ paginator.next_page }}</a></li>
        {%- else %}
          <li><div class="pager-edge">•</div></li>
        {%- endif %}
        </ul>
      </div>
    {%- endif %}
  {%- endif -%}
</div>
```
{% endraw %}

Into the following, where i just removed all liquid code related to the paginator function, 
and changed _assign posts = site.posts_ into _assign posts = site.categories.Code_:

{% raw %}
```liquid 
<div class="home">
  {%- if page.title -%}
    <h1 class="page-heading">{{ page.title }}</h1>
  {%- endif -%}

  {{ content }}

  {% assign posts = site.categories.Code %}

  {%- if posts.size > 0 -%}
    {%- if page.list_title -%}
      <h2 class="post-list-heading">{{ page.list_title }}</h2>
    {%- endif -%}
    <ul class="post-list">
      {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
      {%- for post in posts -%}
      <li>
        <span class="post-meta">{{ post.date | date: date_format }}</span>
        <h3>
          <a class="post-link" href="{{ post.url | relative_url }}">
            {{ post.title | escape }}
          </a>
        </h3>
        {%- if site.show_excerpts -%}
          {{ post.excerpt }}
        {%- endif -%}
      </li>
      {%- endfor -%}
    </ul>
  {%- endif -%}
</div>
```
{% endraw %}
