---
layout: page
title: data/codes
permalink: /projects/
description: Datasets and open-source codes
nav: true
---

<div class="projects grid">

  {% assign sorted_projects = site.projects | sort: "importance" %}
  {% for project in sorted_projects %}
  <div class="grid-item">
    {% if project.redirect %}
      <a href="{{ project.redirect }}" target="_blank">
    {% else %}
      <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card">
        <div class="card-body">
          <div class="row ml-auto mr-auto">
            <div class="col-md-2">
                 {% if project.img %}
                     <img src="{{ project.img | relative_url }}" alt="project thumbnail">
                 {% endif %}
            </div>
            <div class="col-md-8">
                <h5 class="card-title">{{ project.title }}</h5>
                <p class="card-text">{{ project.description }}</p>
            </div>
            <div class="col-md-2">
                {% if project.github %}
                <div class="github-icon">
                  {% if project.github_user %}
                    <iframe src="https://ghbtns.com/github-btn.html?user={{ project.github_user }}&repo={{ project.github_repo }}&type=star&count=true" frameborder="0" scrolling="0" width="150" height="20" title="GitHub"></iframe>
                  {% endif %}
                {% if project.cited_by %}
                    <it>Cited: {{ project.cited_by }}</it>
                {% endif %}
                </div>
                {% endif %}
            </div>
          </div>
        </div>
      </div>
    </a>
  </div>
{% endfor %}

</div>
