{% for link in site.data.navigation.main %}
  {% if link.url contains "://" %}
    <a class="normal{% if link.right %} right{% endif %}" href="{{ link.url }}" target="_blank">{{ link.title }}</a>
  {% else %}
    <a class="normal{% if link.right %} right{% endif %}" href="../{{ link.url }}">{{ link.title }}</a>
  {% endif %}
{% endfor %}

