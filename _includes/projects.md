<h2 id="projects" style="margin: 2px 0px -15px;">Projects</h2>

<div class="publications projects">
<ol class="bibliography">

{% for project in site.data.projects.main %}

<li>
<div class="pub-row">
  {% if project.image and project.image != "" %}
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    <img src="{{ project.image }}" alt="{{ project.image_alt | default: project.title }}" class="teaser img-fluid z-depth-1">
    {% if project.notes %}
    <abbr class="badge">{{ project.notes }}</abbr>
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
  {% else %}
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 0;width: 100%;">
  {% endif %}
      <div class="title">
        {% if project.page %}
        <a href="{{ project.page }}">{{ project.title }}</a>
        {% else %}
        {{ project.title }}
        {% endif %}
      </div>
      {% if project.technologies %}
      <div class="author">{{ project.technologies }}</div>
      {% endif %}
      {% if project.date %}
      <div class="periodical"><em>{{ project.date }}</em></div>
      {% endif %}
      {% if project.description %}
      <div class="description">{{ project.description }}</div>
      {% endif %}
    <div class="links">
      {% if project.pdf %}
      <a href="{{ project.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if project.code %}
      <a href="{{ project.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if project.page %}
      <a href="{{ project.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if project.bibtex %}
      <a href="{{ project.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if project.notes %}
      {% unless project.image and project.image != "" %}
      <strong> <i style="color:#e74d3c">{{ project.notes }}</i></strong>
      {% endunless %}
      {% endif %}
      {% if project.others %}
      {{ project.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>
