---
layout: layouts/base.njk
permalink: /
title: "Le Cronache di Krynn"
---
<div class="pergamena-container">
  <h1>Le Cronache di Krynn</h1>
  <p>Benvenuti nell'archivio ufficiale della nostra campagna. Qui troverete i resoconti delle sessioni e le schede dei protagonisti.</p>
  
  <h2>Diario di Campagna</h2>
  <ul>
  {% for capitolo in collections.diario | reverse %}
    <li>
      <strong><a href="{{ capitolo.url }}">{{ capitolo.data.title }}</a></strong>
    </li>
  {% endfor %}
  </ul>
</div>
