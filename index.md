---
layout: page
show-avatar: true
title: Hola.!
subtitle: Mi nombre es Richard Palacios y soy Desarrollador de Software
use-site-title: true
bigimg: 
  - '/img/first-big-image-unsplash.jpg': "Foto de Unsplash.com"
css: '/css/extend-home.css'
---
<h1 class="text-center">Proyectos Actuales</h1>

<div class="spacer"></div>


<div class="row text-center">
  <div class="col-md-4 col-md-offset-0 col-sm-4 col-sm-offset-0 col-xs-12 col-xs-offset-0 text-center">
    <div class="project-card">
      {%- assign gh-user = "OCram85"-%}
      {%- assign gh-project = "Test Project 1" -%}
      <a target="_blank" href="https://github.com/{{- gh-user -}}/{{- gh-project -}}" class="project-link" title="Go to Github Poject Page">
        <span class="fa-stack fa-4x">
          <i class="fa fa-square fa-stack-2x stack-color"></i>
          <i class="fa fa-terminal fa-stack-1x fa-inverse"></i>
        </span>
        <h4>{{- gh-project -}}</h4>
        <hr class="seperator">
        <p class="text-muted">Esto es una descripción de prueba.</p>
        <hr class="seperator">
        <img src="https://img.shields.io/github/forks/{{- gh-user -}}/{{- gh-project -}}.svg?style=social&label=Fork" alt="Github" title="Github Forks">
        <img src="https://img.shields.io/github/stars/{{- gh-user -}}/{{- gh-project -}}.svg?style=social&label=Stars" alt="Github" title="Github Stars">
      </a>
    </div>
  </div>
  <div class="col-md-4 col-md-offset-0 col-sm-4 col-sm-offset-0 col-xs-12 col-xs-offset-0 text-center">
    <div class="project-card">
      {%- assign gh-project = "Test Proyect 2" -%}
      <a target="_blank" href="https://github.com/{{- gh-user -}}/{{- gh-project -}}" class="project-link" title="Go to Github Poject Page">
        <span class="fa-stack fa-4x">
          <i class="fa fa-square fa-stack-2x stack-color"></i>
          <i class="fa fa-file-code-o fa-stack-1x fa-inverse"></i>
        </span>
        <h4>{{- gh-project -}}</h4>
        <hr class="seperator">
        <p class="text-muted">Esta es una descripción de prueba para el segundo proyecto.</p>
        <hr class="seperator">
        <img src="https://img.shields.io/github/forks/{{- gh-user -}}/{{- gh-project -}}.svg?style=social&label=Fork" alt="Github" title="Github Forks">
        <img src="https://img.shields.io/github/stars/{{- gh-user -}}/{{- gh-project -}}.svg?style=social&label=Stars" alt="Github" title="Github Stars">
      </a>
    </div>
  </div>
  <div class="col-md-4 col-md-offset-0 col-sm-4 col-sm-offset-0 col-xs-12 col-xs-offset-0 text-center">
    <div class="project-card">
    {%- assign gh-project = "Test Project 3" -%}
      <a target="_blank" href="https://github.com/{{- gh-user -}}/{{- gh-project -}}" class="project-link" title="Go to Github Poject Page">
        <span class="fa-stack fa-4x">
          <i class="fa fa-square fa-stack-2x stack-color"></i>
          <i class="fa fa-user-secret fa-stack-1x fa-inverse"></i>
        </span>
        <h4>{{- gh-project -}}</h4>
        <hr class="seperator">
        <p class="text-muted">Esta es la descripción para el 3er proyecto de prueba.</p>
        <hr class="seperator">
        <img src="https://img.shields.io/github/forks/{{- gh-user -}}/{{- gh-project -}}.svg?style=social&label=Fork" alt="Github" title="Github Forks">
        <img src="https://img.shields.io/github/stars/{{- gh-user -}}/{{- gh-project -}}.svg?style=social&label=Stars" alt="Github" title="Github Stars">
      </a>
    </div>
  </div>
</div>

<ul class="pager main-pager">
  <li>
    <a href="{{site.baseurl}}/portfolio">Portafolio </a>
  </li>
</ul>

----

<h1 class="text-center">Publicaciones Recientes</h1>
<div class="spacer"></div>


<div class="posts-list">
  {% for post in site.posts limit:3 %}
  <article class="post-preview">
    <a href="{{ post.url | prepend: site.baseurl }}">
      <h3 class="post-title">{{ post.title }}</h3>

      {% if post.subtitle %}
      <h4 class="post-subtitle">
        {{ post.subtitle }}
      </h4>
      {% endif %}
    </a>

    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>

    <div class="post-entry-container">
      {% if post.image %}
      <div class="post-image">
        <a href="{{ post.url | prepend: site.baseurl }}">
          <img src="{{ post.image }}">
        </a>
      </div>
      {% endif %}
      <div class="post-entry">
        {{ post.excerpt | strip_html | xml_escape | truncatewords: site.excerpt_length }}
        {% assign excerpt_word_count = post.excerpt | number_of_words %}
        {% if post.content != post.excerpt or excerpt_word_count > site.excerpt_length %}
          <a href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</a>
        {% endif %}
      </div>
    </div>

    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags:
      {% if site.link-tags %}
      {% for tag in post.tags %}
      <a href="{{ site.baseurl }}/tags#{{ tag }}">{{ tag }}</a>
      {% endfor %}
      {% else %}
        {{ post.tags | join: ", " }}
      {% endif %}
    </div>
    {% endif %}

   </article>
  {% endfor %}
</div>

<ul class="pager main-pager">
  <li>
    <a href="{{site.baseurl}}/blog">Todas las publicaciones </a>
  </li>
</ul>
