---
layout: layouts/base.njk
permalink: /personaggi/
title: "Dramatis Personae"
templateEngineOverride: njk
---
<div class="pergamena-container">
  <h1>Dramatis Personae</h1>
  <p>Qui trovate l'elenco dei Protagonisti (PG) e dei principali Personaggi Non Giocanti (PNG) incontrati durante l'avventura nelle terre di Ansalon.</p>

  <div class="sezioni-grid">
  {% for pg in collections.personaggi %}
    <div class="sezione-card scheda-personaggio">
      <div class="personaggio-header">
        <h2>{{ pg.data.title }}</h2>
        {% if pg.data.tipo %}
          <div class="tipo-badge">[{{ pg.data.tipo }}]</div>
        {% endif %}
      </div>

      {% if pg.data.image %}
        <div class="ritratto-container" style="margin: 0 auto 1rem auto;">
          <img src="{{ pg.data.image }}" alt="{{ pg.data.title }}" class="ritratto-img">
        </div>
      {% endif %}

      <p style="text-align: center;"><strong>{{ pg.data.razza_classe }}</strong></p>

      {% if pg.data.ca or pg.data.pf %}
        <div class="statistiche-grid" style="margin-bottom: 1rem;">
          {% if pg.data.ca %}
            <div class="stat-box">
              <span class="stat-label">CA</span>
              <span class="stat-value">{{ pg.data.ca }}</span>
            </div>
          {% endif %}
          {% if pg.data.pf %}
            <div class="stat-box">
              <span class="stat-label">PF</span>
              <span class="stat-value">{{ pg.data.pf }}</span>
            </div>
          {% endif %}
        </div>
      {% endif %}

      {% if pg.templateContent %}
        <p class="cta-link"><a href="{{ pg.url }}">Leggi la storia &rarr;</a></p>
      {% endif %}
    </div>
  {% else %}
    <p><em>Nessun personaggio registrato per il momento. Aggiungi i primi protagonisti dal pannello CMS!</em></p>
  {% endfor %}
  </div>
</div>
