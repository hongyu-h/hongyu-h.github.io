{% for link in site.data.selected_publication.main %}
<div class="publications">
<ol class="bibliography">

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
            <abbr class="badge">{{ link.conference_short }}</abbr>
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.title_link | default: link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical">
        <em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.video %}
      <a href="{{ link.video }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Video</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.data %} 
      <a href="{{ link.data }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Dataset</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.notes %} 
      <strong><i class="note-text">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
	    {% if link.artifact_badges %}
	    <div class="artifact-line" aria-label="Artifact badges">
	      {% for badge in link.artifact_badges %}
	        {% unless forloop.first %}<span class="artifact-sep">, </span>{% endunless %}
	        <span class="artifact-item">
	          {% if badge.url %}<a class="artifact-link" href="{{ badge.url }}" target="_blank" rel="noopener noreferrer">{% endif %}
	          <img class="artifact-badge" src="{{ badge.image }}" alt="{{ badge.alt | default: badge.name }}" title="{{ badge.name }}" loading="lazy" decoding="async">
	          {% if badge.url %}</a>{% endif %}
	          <span class="artifact-label{% if badge.key %} artifact-label--{{ badge.key }}{% endif %}">{{ badge.label | default: badge.name }}</span>
	        </span>
	      {% endfor %}
	    </div>
	    {% endif %}
	  </div>
</div>
</li>

</ol>
</div>
{% endfor %}
