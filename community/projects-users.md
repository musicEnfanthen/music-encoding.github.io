---
layout: default
title: "Projects and users"
---
{% assign c = site.collections | where: "label","projects" | first %}
<div class="filter columns">
  <input type="radio" id="tag-0" class="filter-tag" name="filter-radio" hidden>
  <input type="radio" id="tag-1" class="filter-tag" name="filter-radio" hidden checked>
  <input type="radio" id="tag-2" class="filter-tag" name="filter-radio" hidden>

  <div class="filter-nav column col-4 col-md-12 my-2">
    <label class="chip" for="tag-1">Active</label>
    <label class="chip" for="tag-2">Archived</label>
    <label class="chip" for="tag-0">See All</label>
  </div>
  <div class="column col-md-12 my-2">
    <span class="show-md">If you'd like to see your project added here, please <a href="mailto:info@music-encoding.org">contact us</a>.</span>
    <span class="float-right hide-md">If you'd like to see your project added here, please <a href="mailto:info@music-encoding.org">contact us</a>.</span></div>
  <div class="filter-body columns projects column col-12">
  {% for project in c.docs %}
  <div class="column filter-item col-4 col-sm-12 col-lg-6" data-tag="{% if project.archive == true %}tag-2{% else %}tag-1{% endif %}">
      <div class="card project">
          <div class="card-image">
              {% if project.image %}
              <img class="mei-project-image img-fit-cover" alt="{{ project.name }}" src="{{ site.baseurl }}/images/{{ project.image }}"/>
              {% endif %}
          </div>
          <div class="card-header">
              <div class="card-title h5">
                  {{ project.name }}
              </div>
              <div class="card-subtitle text-gray">
                  {{ project.fullname }}
              </div>
          </div>
          <div class="card-footer">
              <a class="btn float-right btn-sm" href="{{ project.url }}.html">More…</a>
          </div>
      </div>
  </div>
  {% endfor %}
  </div>
</div>
