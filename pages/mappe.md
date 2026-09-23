---
layout: layouts/base.njk
permalink: /mappe/
title: "Atlante di Krynn"
templateEngineOverride: njk
---
<div class="pergamena-container">
  <h1>Atlante di Krynn</h1>
  <p>Consultate le carte geografiche e la cartografia delle terre di Ansalon per orientarvi durante la spedizione.</p>

  <div class="sezioni-grid">
  {% for mappa in collections.mappe | reverse %}
    <div class="sezione-card">
      <h2>{{ mappa.data.title }}</h2>
      {% if mappa.data.image %}
        <div class="ritratto-container" style="margin: 0 auto 1rem auto;">
          <img src="{{ mappa.data.image }}" alt="{{ mappa.data.title }}" class="ritratto-img">
        </div>
      {% endif %}
      <p>{{ mappa.data.description }}</p>
      {% if mappa.templateContent %}
        <p class="cta-link"><a href="{{ mappa.url }}">Esplora la mappa &rarr;</a></p>
      {% endif %}
    </div>
  {% else %}
    <p><em>Nessuna mappa o luogo registrato per il momento. Le carte geografiche verranno aggiunte man mano che esplorerete nuove regioni.</em></p>
  {% endfor %}
  </div>
</div>
