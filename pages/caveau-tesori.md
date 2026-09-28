---
title: "Il Caveau del Master"
permalink: "/stanza-segreta-tesori-xyz/" 
---
<!DOCTYPE html>
<html lang="it">
<head>
  <meta charset="UTF-8">
  <title>{{ title }}</title>
  <!-- Assicurati che il percorso del tuo CSS sia corretto -->
  <link rel="stylesheet" href="/css/style.css"> 
</head>
<body>
  <h1>I Tesori di Krynn</h1>
  
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
</body>
</html>
