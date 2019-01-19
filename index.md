---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

{% for tutorial in site.tutorials %}
  <h2> 
    <a href="{{ tutorial.url }}">
    {{ tutorial.title }}
    </a>
  </h2>
{% endfor %}
