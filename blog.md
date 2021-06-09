---
layout: default
title: Blog
---
<div class="container" style="margin-top:30px; margin-bottom:80px;">
<h1 style="text-transform: uppercase; font-size:50px; font-family: Gotham XNarrow;color:#fff;">Top posts</h1>

{% for post in site.posts %}

{% if post.featured %}
  <div class="posts post-web" >


    <div class="post-title post-title-web" style="margin-bottom: 0rem;"><h1 style="font-weight:600;"><a href="{{ post.url }}">{{ post.title }}</a></h1><h3 style="font-size: 1.8rem;font-weight:300;color:#dadada;">~ {{ post.date | date_to_string }}</h3></div>
    {% if post.description %}<p class="post-description post-description-web">{{ post.description }}<br><a href="{{ post.url }}"><button class="post-button">...Read more</button></a></p>{% endif %}

  </div>
  {% endif %}
{% endfor %}

<h1 style="text-transform: uppercase; font-size:50px; font-family: Gotham XNarrow;color:#fff;padding-top:50px;">All posts</h1>

{% for post in site.posts %}

{% if post.featured %}
{% else %}

  <div class="post post-web">



    <div class="post-title post-title-web" style="margin-bottom: 0rem;"><h1 style="font-weight:600;"><a href="{{ post.url }}">{{ post.title }}</a></h1><h3 style="font-weight:300;font-size:1.9rem;">~ {{ post.date | date_to_string }}</h3></div>
    {% if post.description %}<p class="post-description post-description-web">{{ post.description }}<br><a href="{{ post.url }}"><button class="post-button">...Read more</button></a></p>{% endif %}


  </div>
  {% endif %}
{% endfor %}
</div>
