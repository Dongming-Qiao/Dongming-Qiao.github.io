{% assign academic_experience = site.data.experience.academic %}
{% assign industry_experience = site.data.experience.industry %}

{% if academic_experience or industry_experience %}
<h2 id="experience">Experience</h2>

<div class="experience-section">
{% if academic_experience %}
<div class="experience-group">
  <h3>Academic Experience</h3>
  <div class="publications experience-list">
  <ol class="bibliography">
{% for item in academic_experience %}
    <li>
      <div class="pub-row">
        <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
          {% if item.image %}
          <img src="{{ item.image }}" alt="{{ item.image_alt | default: item.organization }}" class="teaser img-fluid z-depth-1">
          {% endif %}
        </div>
        <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
          <div class="title experience-title">
            {% if item.url %}
            <a href="{{ item.url }}" target="_blank" rel="noopener">{{ item.organization }}</a>
            {% else %}
            {{ item.organization }}
            {% endif %}
          </div>
          <div class="author"><strong>{{ item.role }}:</strong> {{ item.period }}.</div>
          {% if item.topics %}
          <div class="periodical"><strong><em>Topics:</em></strong> <em>{{ item.topics }}</em></div>
          {% endif %}
          {% if item.advisor %}
          <div class="periodical">
            <strong>{{ item.advisor_label | default: "Research Advisor" }}:</strong>
            {% if item.advisor_url %}
            <a href="{{ item.advisor_url }}" target="_blank" rel="noopener">{{ item.advisor }}</a>.
            {% else %}
            {{ item.advisor }}.
            {% endif %}
          </div>
          {% endif %}
        </div>
      </div>
    </li>
    <br>
{% endfor %}
  </ol>
  </div>
</div>
{% endif %}

{% if industry_experience %}
<div class="experience-group">
  <h3>Industry Experience</h3>
  <div class="publications experience-list">
  <ol class="bibliography">
{% for item in industry_experience %}
    <li>
      <div class="pub-row">
        <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
          {% if item.image %}
          <img src="{{ item.image }}" alt="{{ item.image_alt | default: item.organization }}" class="teaser img-fluid z-depth-1">
          {% endif %}
        </div>
        <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
          <div class="title experience-title">
            {% if item.url %}
            <a href="{{ item.url }}" target="_blank" rel="noopener">{{ item.organization }}</a>
            {% else %}
            {{ item.organization }}
            {% endif %}
          </div>
          <div class="author"><strong>{{ item.role }}:</strong> {{ item.period }}.</div>
          {% if item.topics %}
          <div class="periodical"><strong><em>Topics:</em></strong> <em>{{ item.topics }}</em></div>
          {% endif %}
          {% if item.advisor %}
          <div class="periodical">
            <strong>{{ item.advisor_label | default: "Mentor" }}:</strong>
            {% if item.advisor_url %}
            <a href="{{ item.advisor_url }}" target="_blank" rel="noopener">{{ item.advisor }}</a>.
            {% else %}
            {{ item.advisor }}.
            {% endif %}
          </div>
          {% endif %}
        </div>
      </div>
    </li>
    <br>
{% endfor %}
  </ol>
  </div>
</div>
{% endif %}
</div>
{% endif %}
