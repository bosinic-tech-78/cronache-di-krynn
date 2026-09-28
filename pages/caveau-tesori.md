---
title: "Il Caveau del Master"
permalink: "/stanza-segreta-tesori-xyz/"
templateEngineOverride: njk, md
---

<div class="griglia-carte">
  {% for oggetto in collections.master_tesori %}
  
  <div class="carta-dnd sfondo-{{ oggetto.data.colore }}">
    <h3 class="carta-titolo">{{ oggetto.data.title }}</h3>
    
    {% if oggetto.data.image %}
    <div class="carta-illustrazione">
        <img src="{{ oggetto.data.image }}" alt="{{ oggetto.data.title }}">
    </div>
    {% endif %}
    
    <div class="carta-tipo">{{ oggetto.data.tipo }}</div>
    
    <div class="carta-descrizione">
      {{ oggetto.templateContent | safe }}
    </div>
  </div>
  
  {% endfor %}
</div>
