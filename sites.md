---
layout: page
title: "@richlitt websites"
description: ""
---
{% include JB/setup %}

<div class="row col-md-12 projects">
  <h2>Websites</h2>
  {% assign sites = (site.sites | sort: 'ranking') %}
  {% for project in sites limit:16 %}
    {% assign loopindex = forloop.index | modulo: 3 %}
    {% if loopindex == 1 %}
      <div class="col-xs-6 col-sm-4 col-md-3" style="margin-left:0px;">
    {% else %}
      <div class="col-xs-6 col-sm-4 col-md-3">
    {% endif %}
        <div class="img-container">
          <a href="{{ project.url }}">
            <img src="{{ HOME_PATH }}images/{{ project.picture }}" class="card-image"/>
          </a>
        </div>
        <a class="project-title" href="{{ project.url }}">
          <h4>
            {{ project.title }}
          </h4>
          <p>{{ project.stub}}<br />
          {{ project.role }} <span class="status">{{ project.status }}</span></p>
        </a>
      </div>
    {% if forloop.index == 3 %}
      <div class="clearfix visible-sm-block"></div>
    {% elsif forloop.index == 4 %}
      <div class="clearfix visible-md-block visible-lg-block"></div>
    {% elsif forloop.index == 12 %}
      <div class="clearfix visible-md-block visible-lg-block"></div>
    {% endif %}
  {% endfor %}
</div>
