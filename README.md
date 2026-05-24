# Gu-a-de-bolsillo-rboles-Nativos-chilenos<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
<meta name="theme-color" content="#1f4e2c">
<title>Árboles de Chile · Guía de bolsillo</title>
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; -webkit-tap-highlight-color: transparent; }
  
  :root {
    --verde-oscuro: #1f4e2c;
    --verde-medio: #2e6b3f;
    --verde-claro: #4a8e5e;
    --crema: #fdfbf4;
    --crema-oscuro: #f0ead6;
    --beige: #f5f1e8;
    --marron: #8b6f3a;
    --marron-claro: #c9a877;
    --texto: #2a2a2a;
    --texto-sec: #6b6b6b;
    --borde: #d4c9a8;
    --amarillo: #f0d96a;
    --amarillo-claro: #fef4d4;
    --azul-norte: #d99060;
    --verde-centro: #6b9c4a;
    --azul-sur: #4a89b8;
  }
  
  html { scroll-behavior: smooth; -webkit-text-size-adjust: 100%; }
  
  body {
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', sans-serif;
    background: var(--beige);
    color: var(--texto);
    line-height: 1.55;
    font-size: 16px;
    padding-bottom: 60px;
  }
  
  /* === PORTADA === */
  .portada {
    background: linear-gradient(160deg, var(--verde-oscuro) 0%, var(--verde-medio) 100%);
    color: var(--crema);
    padding: 50px 24px 40px;
    text-align: center;
  }
  .portada::before {
    content: '🌿';
    font-size: 3em;
    display: block;
    margin-bottom: 8px;
  }
  .portada h1 {
    font-size: 1.9em;
    font-weight: 700;
    letter-spacing: 0.5px;
    line-height: 1.15;
    margin-bottom: 10px;
  }
  .portada .lema {
    font-size: 1em;
    opacity: 0.85;
    font-style: italic;
    margin-bottom: 18px;
  }
  .portada .meta {
    display: inline-block;
    background: rgba(255,255,255,0.15);
    padding: 6px 16px;
    border-radius: 20px;
    font-size: 0.85em;
  }
  
  /* === BARRA BÚSQUEDA + FILTROS === */
  .barra-busqueda {
    position: sticky;
    top: 0;
    z-index: 50;
    background: var(--beige);
    padding: 10px 12px;
    border-bottom: 1px solid var(--borde);
    box-shadow: 0 2px 6px rgba(0,0,0,0.08);
  }
  .barra-busqueda input {
    width: 100%;
    padding: 10px 14px;
    font-size: 16px;
    border: 1px solid var(--borde);
    border-radius: 8px;
    background: white;
    font-family: inherit;
    color: var(--texto);
  }
  .barra-busqueda input:focus {
    outline: none;
    border-color: var(--verde-medio);
    box-shadow: 0 0 0 3px rgba(46, 107, 63, 0.15);
  }
  
  .filtros-zona {
    display: flex;
    gap: 6px;
    margin-top: 8px;
    flex-wrap: wrap;
  }
  .filtro-btn {
    flex: 1;
    min-width: 70px;
    background: white;
    border: 1px solid var(--borde);
    border-radius: 18px;
    padding: 8px 12px;
    font-size: 0.85em;
    font-weight: 600;
    color: var(--texto-sec);
    cursor: pointer;
    transition: all 0.15s;
    font-family: inherit;
    display: flex;
    align-items: center;
    justify-content: center;
    gap: 4px;
  }
  .filtro-btn:active { transform: scale(0.97); }
  .filtro-btn.activo[data-zona="Todas"] { background: var(--verde-medio); color: white; border-color: var(--verde-medio); }
  .filtro-btn.activo[data-zona="Norte"] { background: var(--azul-norte); color: white; border-color: var(--azul-norte); }
  .filtro-btn.activo[data-zona="Centro"] { background: var(--verde-centro); color: white; border-color: var(--verde-centro); }
  .filtro-btn.activo[data-zona="Sur"] { background: var(--azul-sur); color: white; border-color: var(--azul-sur); }
  .filtro-emoji { font-size: 1.1em; }
  .filtro-count { border-radius: 10px; padding: 0 6px; font-size: 0.78em; margin-left: 2px; }
  .filtro-btn.activo .filtro-count { background: rgba(0,0,0,0.15); color: white; }
  .filtro-btn:not(.activo) .filtro-count { background: var(--crema-oscuro); color: var(--marron); }
  
  /* === ÍNDICE === */
  .indice { background: var(--crema); padding: 28px 20px; border-bottom: 1px solid var(--borde); }
  .indice h2 { color: var(--verde-oscuro); font-size: 1.3em; margin-bottom: 6px; text-align: center; }
  .indice .tip { text-align: center; color: var(--texto-sec); font-size: 0.85em; margin-bottom: 20px; font-style: italic; }
  .indice-lista { list-style: none; display: grid; gap: 4px; }
  .indice-lista li a { display: flex; align-items: center; gap: 12px; padding: 12px 10px; background: white; border-radius: 8px; text-decoration: none; color: var(--texto); border-left: 3px solid var(--verde-medio); }
  .indice-lista li a:active { background: var(--crema-oscuro); }
  .indice-num { background: var(--verde-medio); color: white; width: 32px; height: 32px; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 0.75em; font-weight: 700; flex-shrink: 0; }
  .indice-nombre { display: flex; flex-direction: column; min-width: 0; }
  .indice-nombre em { font-style: italic; font-weight: 600; color: var(--verde-oscuro); font-size: 0.95em; overflow: hidden; text-overflow: ellipsis; }
  .indice-nombre small { color: var(--texto-sec); font-size: 0.8em; margin-top: 2px; }
  
  /* === FICHAS === */
  .ficha { background: var(--crema); padding: 26px 20px 22px; margin: 14px 12px; border-radius: 12px; box-shadow: 0 1px 3px rgba(0,0,0,0.06); scroll-margin-top: 110px; }
  .ficha-header { border-bottom: 2px solid var(--verde-oscuro); padding-bottom: 14px; margin-bottom: 18px; }
  .ficha-num { color: var(--marron); font-size: 0.75em; letter-spacing: 1.5px; text-transform: uppercase; font-weight: 600; margin-bottom: 6px; }
  .familia-tag { color: var(--verde-medio); font-weight: 600; }
  .nombre-cientifico { font-size: 1.4em; color: var(--verde-oscuro); font-weight: 400; line-height: 1.2; margin-bottom: 8px; }
  .nombre-cientifico em { font-style: italic; font-weight: 600; }
  .nombre-cientifico .autor { font-size: 0.65em; color: var(--texto-sec); font-weight: 400; }
  .nombres-comunes { color: var(--marron); font-size: 0.95em; font-weight: 500; line-height: 1.4; margin-bottom: 10px; }
  
  /* === STATUS BADGE === */
  .status-badge { display: inline-block; padding: 4px 12px; border-radius: 12px; font-size: 0.78em; font-weight: 600; margin-top: 4px; cursor: help; }
  .status-endemico-chile { background: #ffe8e0; color: #8b4513; border: 1px solid #d4a373; }
  .status-endemico-region { background: #fff4d4; color: #6b5520; border: 1px solid #e8c668; }
  .status-nativo { background: #d8ebe0; color: #1f4e2c; border: 1px solid #a3c9b0; }
  
  /* === BLOQUES === */
  .bloque { margin-bottom: 12px; background: white; border-radius: 8px; padding: 12px 14px; border-left: 3px solid var(--verde-claro); }
  .bloque-titulo { font-size: 0.8em; text-transform: uppercase; letter-spacing: 1.2px; color: var(--verde-oscuro); font-weight: 700; margin-bottom: 8px; }
  
  /* CONTEXTO DE ILUSTRACIÓN FLEXIBLE */
  .desc-flex-container { display: flex; gap: 14px; align-items: center; margin-bottom: 12px; background: var(--beige); padding: 8px; border-radius: 8px; }
  .desc-general { font-size: 0.95em; color: var(--texto); line-height: 1.55; margin: 0; }
  .ilustracion-botanica { background: white; border-radius: 50%; border: 1px solid var(--borde); flex-shrink: 0; box-shadow: inset 0 2px 4px rgba(0,0,0,0.03); }
  
  .desc-items { border-top: 1px dashed var(--borde); padding-top: 10px; display: grid; gap: 8px; }
  .desc-item { font-size: 0.92em; line-height: 1.5; color: var(--texto); padding-left: 8px; border-left: 2px solid var(--crema-oscuro); }
  .desc-label { font-weight: 700; color: var(--verde-oscuro); display: inline-block; min-width: 90px; }
  
  .bloque.distribucion { border-left-color: var(--marron); background: linear-gradient(to right, #fef9e7 0%, white 80%); }
  .bloque.curiosidad { border-left-color: var(--amarillo); background: linear-gradient(to right, var(--amarillo-claro) 0%, white 80%); }
  .bloque.curiosidad p { font-style: italic; color: #5a4d20; }
  
  /* === MAPA === */
  .mapa-wrapper { margin-top: 14px; background: white; padding: 10px; border-radius: 6px; border: 1px solid var(--borde); }
  .mapa-chile { display: block; width: 100%; max-width: 340px; height: auto; margin: 0 auto; }
  
  /* === FOTOS LINKS === */
  .bloque-fotos { background: linear-gradient(to right, #e8f0e8, white); padding: 12px 14px; border-radius: 8px; border-left: 3px solid var(--verde-medio); display: flex; flex-wrap: wrap; align-items: center; gap: 8px; font-size: 0.9em; }
  .fotos-label { font-weight: 600; color: var(--verde-oscuro); margin-right: 4px; }
  .bloque-fotos a { background: var(--verde-medio); color: white; padding: 5px 12px; border-radius: 14px; text-decoration: none; font-size: 0.85em; font-weight: 500; }
  .bloque-fotos a:active { background: var(--verde-oscuro); }
  
  /* === BOTÓN VOLVER ARRIBA === */
  .btn-arriba { position: fixed; bottom: 16px; right: 16px; width: 48px; height: 48px; background: var(--verde-oscuro); color: white; border-radius: 50%; border: none; font-size: 1.4em; box-shadow: 0 3px 12px rgba(0,0,0,0.3); cursor: pointer; z-index: 100; opacity: 0; transform: translateY(20px); transition: opacity 0.2s, transform 0.2s; display: flex; align-items: center; justify-content: center; }
  .btn-arriba.visible { opacity: 1; transform: translateY(0); }
  
  .ficha.oculta { display: none; }
  .indice.oculto { display: none; }
  .resultado-vacio { text-align: center; padding: 40px 20px; color: var(--texto-sec); font-style: italic; display: none; }
  .resultado-vacio.visible { display: block; }
  
  /* === LEYENDA STATUS === */
  .leyenda { background: var(--crema); margin: 14px 12px; padding: 16px 18px; border-radius: 12px; border-left: 4px solid var(--verde-medio); }
  .leyenda h3 { color: var(--verde-oscuro); font-size: 1em; margin-bottom: 10px; }
  .leyenda-items { display: flex; flex-wrap: wrap; gap: 8px; font-size: 0.85em; }
  
  /* === PIE === */
  .pie { text-align: center; padding: 30px 24px 20px; color: var(--texto-sec); font-size: 0.8em; line-height: 1.6; }
  .pie p { margin-bottom: 8px; }
  
  /* === RESPONSIVE === */
  @media (min-width: 700px) {
    body { font-size: 17px; }
    .portada { padding: 70px 24px 50px; }
    .portada h1 { font-size: 2.5em; }
    .indice { padding: 40px 24px; }
    .indice-lista { grid-template-columns: repeat(2, 1fr); max-width: 900px; margin: 0 auto; }
    .ficha { max-width: 800px; margin: 18px auto; padding: 32px 30px 28px; }
    .nombre-cientifico { font-size: 1.6em; }
    .leyenda { max-width: 800px; margin: 14px auto; }
    .barra-busqueda { padding: 12px 16px; }
    .filtros-zona { max-width: 800px; margin-left: auto; margin-right: auto; }
    .desc-label { min-width: 110px; }
  }
  @media (min-width: 1000px) { .indice-lista { grid-template-columns: repeat(3, 1fr); max-width: 1100px; } }
  @media print { body { background: white; font-size: 11pt; } .portada, .barra-busqueda, .btn-arriba, .indice { display: none; } .ficha { box-shadow: none; border: 1px solid #ccc; page-break-inside: avoid; margin: 10px 0; } }
</style>
</head>
<body>

<header class="portada">
  <h1>Árboles Nativos<br>de Chile</h1>
  <p class="lema">Guía botánica de bolsillo</p>
  <div class="meta">43 especies · ordenadas A-Z</div>
</header>

<div class="barra-busqueda">
  <input type="text" id="buscador" placeholder="🔍 Buscar por nombre, familia o región..." autocomplete="off" autocorrect="off" autocapitalize="off" spellcheck="false">
  <div class="filtros-zona" id="filtrosZona">
    <button class="filtro-btn activo" data-zona="Todas">
      <span class="filtro-emoji">🌎</span>Todas <span class="filtro-count" id="count-Todas"></span>
    </button>
    <button class="filtro-btn" data-zona="Norte">
      <span class="filtro-emoji">🏜️</span>Norte <span class="filtro-count" id="count-Norte"></span>
    </button>
    <button class="filtro-btn" data-zona="Centro">
      <span class="filtro-emoji">🌳</span>Centro <span class="filtro-count" id="count-Centro"></span>
    </button>
    <button class="filtro-btn" data-zona="Sur">
      <span class="filtro-emoji">🌲</span>Sur <span class="filtro-count" id="count-Sur"></span>
    </button>
  </div>
</div>

<div class="leyenda">
  <h3>Estado de origen</h3>
  <div class="leyenda-items">
    <span class="status-badge status-endemico-chile">Endémico de Chile</span>
    <span class="status-badge status-endemico-region">Endémico Chile-Argentina</span>
    <span class="status-badge status-nativo">Nativo (no endémico)</span>
  </div>
  <p style="margin-top: 10px; font-size: 0.82em; color: var(--texto-sec);">
    <b>Endémico:</b> solo vive aquí. <b>Nativo:</b> es originario pero también crece en otros países. Todas las especies de esta guía son nativas (ninguna fue introducida).
  </p>
</div>

<nav class="indice" id="indice">
  <h2>📑 Índice</h2>
  <p class="tip">Toca un árbol para ir a su ficha. Usa el botón ↑ para volver aquí.</p>
  <ol class="indice-lista">
    <li><a href="#acacia-caven"><span class="indice-num">01</span><span class="indice-nombre"><em>Acacia caven</em><small>Espino</small></span></a></li>
    <li><a href="#aextoxicon-punctatum"><span class="indice-num">02</span><span class="indice-nombre"><em>Aextoxicon punctatum</em><small>Olivillo</small></span></a></li>
    <li><a href="#araucaria-araucana"><span class="indice-num">03</span><span class="indice-nombre"><em>Araucaria araucana</em><small>Araucaria</small></span></a></li>
    <li><a href="#austrocedrus-chilensis"><span class="indice-num">04</span><span class="indice-nombre"><em>Austrocedrus chilensis</em><small>Ciprés de la cordillera</small></span></a></li>
    <li><a href="#beilschmiedia-berteroana"><span class="indice-num">05</span><span class="indice-nombre"><em>Beilschmiedia berteroana</em><small>Belloto del sur</small></span></a></li>
    <li><a href="#beilschmiedia-miersii"><span class="indice-num">06</span><span class="indice-nombre"><em>Beilschmiedia miersii</em><small>Belloto del norte</small></span></a></li>
    <li><a href="#citronella-mucronata"><span class="indice-num">07</span><span class="indice-nombre"><em>Citronella mucronata</em><small>Naranjillo</small></span></a></li>
    <li><a href="#cryptocarya-alba"><span class="indice-num">08</span><span class="indice-nombre"><em>Cryptocarya alba</em><small>Peumo</small></span></a></li>
    <li><a href="#dasyphyllum-diacanthoides"><span class="indice-num">09</span><span class="indice-nombre"><em>Dasyphyllum diacanthoides</em><small>Trevo</small></span></a></li>
    <li><a href="#drimys-winteri"><span class="indice-num">10</span><span class="indice-nombre"><em>Drimys winteri</em><small>Canelo</small></span></a></li>
    <li><a href="#embothrium-coccineum"><span class="indice-num">11</span><span class="indice-nombre"><em>Embothrium coccineum</em><small>Notro</small></span></a></li>
    <li><a href="#eucryphia-cordifolia"><span class="indice-num">12</span><span class="indice-nombre"><em>Eucryphia cordifolia</em><small>Ulmo</small></span></a></li>
    <li><a href="#fitzroya-cupressoides"><span class="indice-num">13</span><span class="indice-nombre"><em>Fitzroya cupressoides</em><small>Alerce</small></span></a></li>
    <li><a href="#gevuina-avellana"><span class="indice-num">14</span><span class="indice-nombre"><em>Gevuina avellana</em><small>Avellano</small></span></a></li>
  </ol>
</nav>

<div class="resultado-vacio" id="vacio">
  <p>No se encontraron árboles que coincidan con tu búsqueda.</p>
</div>

<article class="ficha" id="acacia-caven" data-buscable="acacia caven espino espinillo caven churqui fabaceae coquimbo valparaiso metropolitana o higgins maule nuble biobio arbol o arbusto pequeno espinoso 2 6 m caracteristico del espinal del valle central copa aparasolada nativo no endemico de chile en mapudungun se le conoce como caven o caben no tiene descomposicion de raices documentada es una palabra primaria el nombre churqui usado en zonas andinas viene del quechua" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 01 · <span class="familia-tag">Fabaceae</span></div>
    <h2 class="nombre-cientifico"><em>Acacia caven</em> <span class="autor">(Molina) Molina</span></h2>
    <div class="nombres-comunes">Espino, Espinillo, Caven, Churqui</div>
    <div class="status-badge status-nativo" title="Especie nativa de Chile pero también presente naturalmente en Argentina, Uruguay, Paraguay, Bolivia y sur de Brasil.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Acacia caven">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 72 Q 42 48 38 38 T 58 22 M 38 38 Q 24 32 20 18 M 42 50 Q 55 42 64 45" stroke="#5a4d20" stroke-width="2.5" fill="none" stroke-linecap="round"/>
        <path d="M 38 40 L 28 43 M 38 40 L 32 48 M 45 46 L 54 48 M 41 32 L 48 26" stroke="#c9a877" stroke-width="1.5" fill="none"/>
        <circle cx="58" cy="22" r="5.5" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
        <circle cx="20" cy="18" r="4.5" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
        <circle cx="64" cy="45" r="4" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
        <circle cx="32" cy="34" r="5" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol o arbusto pequeño espinoso (2-6 m), característico del 'espinal' del valle central. Copa aparasolada.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, compuestas bipinnadas, pequeñas (2-4,5 cm), de textura fina, verde claro. En la base de cada hoja, dos espinas blancas rectas de 2 cm.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Castaño oscura, fisurada longitudinalmente con grietas profundas. Ramas tortuosas oscuras.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores en pomponcillos amarillo-dorados, muy perfumados, en cabezuelas globosas de 1-2 cm. Florecen en primavera. Fruto: legumbre gruesa cilíndrica casi negra, indehiscente.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Acacia</b>: del griego <i>akakía</i> (ἀκακία), derivado de <i>akís</i> (punta, espina). <b>caven</b>: latinización del nombre mapuche <i>cavén</i>.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>cavén</b> o <b>cabén</b>. No tiene descomposición de raíces documentada: es una palabra primaria. El nombre 'churqui' usado en zonas andinas viene del quechua.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Zona mediterránea y semiárida. Crece en suelos secos y degradados.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El espino es uno de los pocos árboles que ha aumentado su distribución por la acción humana: la tala del bosque esclerófilo nativo dejó espacios que el espino colonizó rápidamente. Lo que hoy parece 'paisaje típico de Chile central' (cerros pelados con espinos dispersos) es en realidad un ecosistema empobrecido que reemplazó al bosque original.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Acacia%20caven" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Acacia%20caven&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Acacia%20caven" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="aextoxicon-punctatum" data-buscable="aextoxicon punctatum olivillo tique aceitunillo palo muerto aextoxicaceae coquimbo fray jorge valparaiso maule biobio la araucania los rios los lagos aysen arbol siempreverde de gran porte hasta 25 m tronco recto arbol fundamental del bosque costero de neblina nativo endemico de la region andina chileno argentina en mapudungun se llama tique o tiqui palabra primaria sin descomposicion documentada olivillo es castellano por la semejanza de sus frutos con aceitunas pequenas" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 02 · <span class="familia-tag">Aextoxicaceae</span></div>
    <h2 class="nombre-cientifico"><em>Aextoxicon punctatum</em> <span class="autor">Ruiz &amp; Pav.</span></h2>
    <div class="nombres-comunes">Olivillo, Tique, Aceitunillo, Palo muerto</div>
    <div class="status-badge status-endemico-region" title="Especie monotípica: único miembro de su familia y género. Habita en Chile y un sector reducido del oeste argentino.">Nativo · Endémico de la región andina chileno-argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Aextoxicon punctatum">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 20 45 C 22 25, 38 18, 55 15 C 50 35, 42 50, 20 45" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 20 45 Q 38 32 55 15" stroke="#4a8e5e" stroke-width="1.5" fill="none"/>
        <circle cx="28" cy="32" r="1" fill="#8b6f3a"/><circle cx="34" cy="26" r="1" fill="#8b6f3a"/>
        <circle cx="44" cy="22" r="1" fill="#8b6f3a"/><circle cx="38" cy="38" r="1" fill="#8b6f3a"/>
        <circle cx="46" cy="34" r="1" fill="#8b6f3a"/>
        <path d="M 45 42 L 52 56" stroke="#6b6b6b" stroke-width="1.5" fill="none"/>
        <ellipse cx="54" cy="60" r="4" rx="3" ry="5" fill="#3a3a5a" stroke="#2a2a2a" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol siempreverde de gran porte (hasta 25 m), tronco recto. Árbol fundamental del bosque costero de neblina.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, opuestas, lanceoladas (5-10 cm), enteras, verde oscuro brillante por arriba y plateado-escamoso por debajo. El envés punteado es la clave para identificarlo.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Lisa, gris-blanquecina en árboles jóvenes; más oscura y agrietada en adultos. Tronco frecuentemente cubierto de musgos y líquenes.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, blanco-amarillentas, en racimos colgantes. Fruto en drupa ovoide morada-negruzca, parecida a una pequeña aceituna (de ahí 'olivillo').</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Aextoxicon</b>: del griego <i>aix, aigós</i> (cabra) + <i>toxikón</i> (veneno), por la creencia (errónea) de que era tóxico para las cabras. <b>punctatum</b>: del latín, 'punteado', por las escamas de sus hojas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>tique</b> o <b>tiqui</b>, palabra primaria sin descomposición documentada. 'Olivillo' es castellano, por la semejanza de sus frutos con aceitunas pequeñas.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Bosques costeros donde la neblina (camanchaca) aporta humedad. Cordillera de la Costa y cordones andinos bajos.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Es el árbol estrella del Parque Nacional Bosque Fray Jorge, en pleno semiárido de Coquimbo, donde sobrevive un bosque reliquia gracias a la neblina costera. Es un ecosistema 'fantasma' del pasado glacial: cuando el clima de Chile central era más húmedo, este bosque cubría grandes extensiones. Hoy es un fósil viviente atrapado entre el desierto y el océano.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Aextoxicon%20punctatum" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Aextoxicon%20punctatum&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Aextoxicon%20punctatum" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="araucaria-araucana" data-buscable="araucaria araucana araucaria pehuen pino araucano pinonero araucariaceae biobio nahuelbuta la araucania conifera milenaria hasta 50 m copa en forma de paraguas o candelabro en arboles adultos vive mas de 1 000 anos nativo endemico de chile y argentina en mapudungun el termino pewenche se compone de pewen la araucaria che gente gente del pehuen la palabra pewen en si misma es una raiz primaria a las semillas se les llama ngulliu pinones" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 03 · <span class="familia-tag">Araucariaceae</span></div>
    <h2 class="nombre-cientifico"><em>Araucaria araucana</em> <span class="autor">(Molina) K. Koch</span></h2>
    <div class="nombres-comunes">Araucaria, Pehuén, Pino araucano, Piñonero</div>
    <div class="status-badge status-endemico-region" title="Habita exclusivamente en una franja restringida entre Chile y Argentina. Monumento Natural de Chile desde 1976.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Araucaria araucana">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 72 L 40 32" stroke="#5a4d20" stroke-width="4.5" stroke-linecap="round"/>
        <path d="M 40 38 Q 24 35 16 26 Q 22 24 36 34" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 40 38 Q 56 35 64 26 Q 58 24 44 34" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 40 46 Q 20 44 14 36 Q 22 34 36 42" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 40 46 Q 60 44 66 36 Q 58 34 44 42" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
        <ellipse cx="40" cy="24" r="16" ry="7" fill="#1f4e2c"/>
      </svg>
      <p class="desc-general">Conífera milenaria (hasta 50 m), copa en forma de paraguas o candelabro en árboles adultos. Vive más de 1.000 años.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, en forma de escamas rígidas, lanceoladas-triangulares, terminadas en una punta muy aguda y punzante (3-4 cm). Color verde oscuro brillante. Cubren densamente las ramas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gruesa (hasta 15 cm), corchosa, dividida en placas poligonales como mosaico, gris-pardo. Adaptación contra incendios.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta dioica (machos y hembras separados). Conos masculinos cilíndricos amarillentos; conos femeninos esféricos grandes (15-20 cm) que contienen los piñones (semillas comestibles).</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Araucaria</b>: de 'Arauco', territorio mapuche, latinizado por Antoine de Jussieu en 1789. <b>araucana</b>: refuerza la procedencia geográfica.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>pewen</b>. El término <b>pewenche</b> se compone de <b>pewen</b> (la araucaria) + <b>che</b> (gente) = 'gente del pehuén'. A las semillas se les llama <b>ngülliu</b> (piñones).</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Cordillera de los Andes y Nahuelbuta entre 600-1.800 msnm. Bosques de araucaria.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El piñón fue la base alimenticia del pueblo pehuenche: en otoño viajaban a las 'piñonadas' para cosecharlos. Una sola araucaria adulta puede producir hasta 200 kilos de piñones al año, y las familias almacenaban estos frutos en silos enterrados ('cuevi') para tener alimento todo el año. La planta es dioica: hay araucarias macho y hembra, pero solo las hembras dan piñones.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Araucaria%20araucana" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Araucaria%20araucana&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Araucaria%20araucana" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="austrocedrus-chilensis" data-buscable="austrocedrus chilensis cipres de la cordillera cipres chileno len cupressaceae metropolitana o higgins maule nuble biobio la araucania los rios los lagos aysen conifera de porte piramidal hasta 20 m copa angosta y columnar especies muy longevas mas de 1 500 anos nativo endemico de chile y argentina en mapudungun se llama len lleng o leng palabra primaria sin descomposicion clara el toponimo lenga y muchos nombres geograficos del sur derivan de raices vinculadas a arboles" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 04 · <span class="familia-tag">Cupressaceae</span></div>
    <h2 class="nombre-cientifico"><em>Austrocedrus chilensis</em> <span class="autor">(D.Don) Pic.Serm. &amp; Bizzarri</span></h2>
    <div class="nombres-comunes">Ciprés de la cordillera, Ciprés chileno, Len</div>
    <div class="status-badge status-endemico-region" title="Habita solo en los Andes patagónicos de Chile y Argentina. Especie de gran longevidad.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Austrocedrus chilensis">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 70 L 40 14" stroke="#8b6f3a" stroke-width="2.5" stroke-linecap="round"/>
        <path d="M 40 15 L 28 55 L 52 55 Z" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 40 22 L 31 50 L 49 50 Z" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="0.5"/>
        <path d="M 40 55 L 24 62 M 40 58 L 54 64" stroke="#8b6f3a" stroke-width="1.5"/>
      </svg>
      <p class="desc-general">Conífera de porte piramidal (hasta 20 m), copa angosta y columnar. Especies muy longevas (más de 1.500 años).</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, en forma de escamas pequeñas (2-4 mm), dispuestas en parejas opuestas que cubren las ramillas. Color verde-azulado con bandas blanquecinas en el envés. Aromáticas al frotar.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-rojiza, fibrosa, se desprende en tiras longitudinales largas. Característica diagnóstica.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta dioica. Conos masculinos amarillentas pequeños; conos femeninos ovoides (1 cm) con 4 escamas leñosas, verde-azulados antes de madurar.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Austrocedrus</b>: del latín <i>auster</i> (sur) + <i>cedrus</i> (cedro) = 'cedro del sur'. <b>chilensis</b>: de Chile.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>len</b>, <b>lleng</b> o <b>leng</b>, palabra primaria sin descomposición clara. El topónimo <b>Lenga</b> y muchos nombres geográficos del sur derivan de raíces vinculadas a árboles.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Precordillera y cordillera andina, sectores secos y rocosos entre 600-1.800 msnm.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El ciprés de la cordillera es uno de los árboles más longevos de Chile: hay registros de ejemplares de más de 1.500 años. Su madera era tan apreciada que la explotación masiva durante los siglos XIX y XX redujo enormemente su distribución. Hoy sufre del 'mal del ciprés', una enfermedad causada por el hongo Phytophthora austrocedri que ha diezmado bosques completos.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Austrocedrus%20chilensis" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Austrocedrus%20chilensis&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Austrocedrus%20chilensis" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="beilschmiedia-berteroana" data-buscable="beilschmiedia berteroana belloto del sur belloto lauraceae o higgins maule nuble biobio arbol siempreverde de tamano mediano 15 25 m copa redondeada follaje denso nativo endemico de chile sin nombre mapuche documentado belloto es palabra castellana derivada de bellota por la semejanza de sus frutos con las bellotas de los robles europeos" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 05 · <span class="familia-tag">Lauraceae</span></div>
    <h2 class="nombre-cientifico"><em>Beilschmiedia berteroana</em> <span class="autor">(Gay) Kosterm.</span></h2>
    <div class="nombres-comunes">Belloto del sur, Belloto</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. Monumento Natural desde 1995. En peligro de extinción (UICN).">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Beilschmiedia berteroana">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 62 Q 35 48 65 30" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 32 44 C 20 30, 24 15, 45 22 C 38 34, 38 42, 32 44" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="1"/>
        <path d="M 46 41 L 52 46" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 50 49 C 48 45, 55 42, 56 46 Z" fill="#c9a877" stroke="#8b6f3a" stroke-width="0.5"/>
        <ellipse cx="58" cy="54" r="5" rx="4" ry="7" fill="#c99c4a" stroke="#8b6f3a" stroke-width="1" transform="rotate(-30 58 54)"/>
      </svg>
      <p class="desc-general">Árbol siempreverde de tamaño mediano (15-25 m), copa redondeada, follaje denso.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, elíptico-oblongas (8-15 cm), enteras, verde oscuro brillante por arriba, más pálidas por abajo. Coriáceas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Lisa, gris-parduzca a marrón oscura. Tronco recto y cilíndrico.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, amarillo-verdosas, agrupadas en panículas axilares. Fruto en drupa grande, ovoide-alargada (3-4 cm), parecida a una bellota (de ahí 'belloto'), de color verde-amarillento.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Beilschmiedia</b>: honra a Carl Traugott Beilschmied (botánico alemán, 1793-1848). <b>berteroana</b>: por Carlo Giuseppe Bertero, naturalista italiano.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>Sin nombre mapuche documentado. <i>Belloto</i> es palabra castellana derivada de 'bellota', por la semejanza de sus frutos con las bellotas de los robles europeos.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Pocas localidades aisladas de la cordillera de la Costa y precordillera andina del centro-sur. Quebradas húmedas.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El belloto del sur ha quedado tan fragmentado que muchos ejemplares adultos están aislados: aunque florecen y dan frutos, no hay polinizadores ni dispersores suficientes para que prosperen plántulas. Es lo que los ecólogos llaman 'muertos vivientes': árboles maduros sin descendencia, condenados a desaparecer si no se interviene.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Beilschmiedia%20berteroana" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Beilschmiedia%20berteroana&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Beilschmiedia%20berteroana" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="beilschmiedia-miersii" data-buscable="beilschmiedia miersii belloto del norte belloto lauraceae valparaiso metropolitana o higgins arbol siempreverde grande hasta 25 m copa amplia crece en quebradas humedas mediterraneas nativo endemico de chile sin nombre mapuche documentado belloto es palabra castellana por la semejanza del fruto con la bellota" data-zonas="Centro">
  <header class="ficha-header">
    <div class="ficha-num">N° 06 · <span class="familia-tag">Lauraceae</span></div>
    <h2 class="nombre-cientifico"><em>Beilschmiedia miersii</em> <span class="autor">(Gay) Kosterm.</span></h2>
    <div class="nombres-comunes">Belloto del norte, Belloto</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile central. Monumento Natural desde 1995. En peligro de extinción.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Beilschmiedia miersii">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 65 65 Q 45 45 15 35" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 42 44 C 54 36, 62 18, 44 26 C 36 34, 38 42, 42 44" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 32 38 C 22 24, 14 12, 28 15 C 32 24, 30 32, 32 38" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="1"/>
        <path d="M 45 45 L 50 54" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <circle cx="53" cy="58" r="6" fill="#bca368" stroke="#8b6f3a" stroke-width="1"/>
        <path d="M 49 54 Q 53 52 57 56" stroke="#8b6f3a" stroke-width="0.5" fill="none"/>
      </svg>
      <p class="desc-general">Árbol siempreverde grande (hasta 25 m), copa amplia. Crece en quebradas húmedas mediterráneas.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, elíptico-lanceoladas (6-12 cm), enteras, verde brillante. Olor aromático al estrujarlas (familia Lauraceae).</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Lisa, gris-clara a oscura. Tronco cilíndrico y recto.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Diminutas, blanco-amarillentas, agrupadas en panículas axilares. Fruto en drupa grande ovoide-elipsoidal (3-5 cm), verde-amarillento, similar a una bellota grande.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Beilschmiedia</b>: por Carl Traugott Beilschmied. <b>miersii</b>: por John Miers, botánico inglés del siglo XIX.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>Sin nombre mapuche documentado. <i>Belloto</i> es palabra castellana, por la semejanza del fruto con la bellota.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Quebradas profundas de la cordillera de la Costa y precordillera andina del centro-norte de Chile.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El belloto del norte se mantiene gracias a un curioso aliado: las ranas chilenas y las lluvias invernales que mantienen las quebradas frescas en verano. Sus frutos eran consumidos por la fauna del pasado (megafauna del Pleistoceno) y hoy quedan en gran parte sin dispersores naturales, lo que dificulta su regeneración.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Beilschmiedia%20miersii" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Beilschmiedia%20miersii&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Beilschmiedia%20miersii" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="citronella-mucronata" data-buscable="citronella mucronata naranjillo huillipatagua cardiopteridaceae coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania los rios arbol siempreverde mediano 8 15 m copa densa y redondeada crecimiento lento nativo endemico de chile en mapudungun se llama huillipatagua palabra compuesta huilli sur patagua otro arbol crinodendron patagua patagua del sur caso interesante de derivacion a partir de otra planta conocida" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 07 · <span class="familia-tag">Cardiopteridaceae</span></div>
    <h2 class="nombre-cientifico"><em>Citronella mucronata</em> <span class="autor">(Ruiz &amp; Pav.) D.Don</span></h2>
    <div class="nombres-comunes">Naranjillo, Huillipatagua</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. No se encuentra en ningún otro país.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Citronella mucronata">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 18 52 C 22 28, 44 24, 60 22 C 50 44, 38 56, 18 52" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="1.5"/>
        <path d="M 18 52 Q 38 38 60 22" stroke="#2e6b3f" stroke-width="1.5" fill="none"/>
        <path d="M 60 22 L 65 20" stroke="#2a2a2a" stroke-width="2" stroke-linecap="round"/>
        <circle cx="24" cy="44" r="2.5" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
        <circle cx="28" cy="48" r="2" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol siempreverde mediano (8-15 m), copa densa y redondeada. Crecimiento lento.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovado-lanceoladas (4-8 cm), coriáceas, verde oscuro brillante. Margen entero con punta aguda (mucronada). Aroma cítrico fuerte al estrujarlas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Grisácea, lisa en jóvenes, más rugosa en adultos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, blanco-amarillentas, agrupadas en panículas axilares. Fruto en drupa ovoide negruzca (8-12 mm) que recuerda una pequeña aceituna.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Citronella</b>: diminutivo del latín <i>citrus</i> (limonero), por el aroma cítrico de sus hojas. <b>mucronata</b>: del latín <i>mucro</i> (punta), por las hojas terminadas en pequeña punta.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>huillipatagua</b>, palabra compuesta: <b>huilli</b> (sur) + <b>patagua</b> (otro árbol, Crinodendron patagua) = 'patagua del sur'. Caso interesante de derivación a partir de otra planta conocida.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Quebradas y laderas húmedas de la cordillera de la Costa y precordillera. Bosque esclerófilo y valdiviano de transición.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Si estrujas una hoja entre los dedos, libera un aroma intenso a limón y cítricos, muy similar al de la verdadera citronela usada como repelente de mosquitos. De hecho, sus aceites esenciales contienen compuestos químicos similares, aunque pertenece a una familia botánica completamente distinta.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Citronella%20mucronata" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Citronella%20mucronata&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Citronella%20mucronata" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="cryptocarya-alba" data-buscable="cryptocarya alba peumo lauraceae coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania arbol siempreverde mediano 10 20 m copa densa y globosa especie clave del bosque esclerofilo nativo endemico de chile y argentina en mapudungun se llama pengu peumo o peuwum es una palabra raiz presente en muchos toponimos de chile central como peumo o higgins" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 08 · <span class="familia-tag">Lauraceae</span></div>
    <h2 class="nombre-cientifico"><em>Cryptocarya alba</em> <span class="autor">(Molina) Looser</span></h2>
    <div class="nombres-comunes">Peumo</div>
    <div class="status-badge status-endemico-region" title="Habita en Chile central y un pequeño sector de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Cryptocarya alba">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 50 Q 40 45 65 30" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 24 48 C 15 32, 28 20, 42 28 C 34 38, 30 46, 24 48" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 44 40 C 40 22, 58 14, 64 26 C 54 34, 50 38, 44 40" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 34 46 L 36 54" stroke="#8b6f3a" stroke-width="1.5" fill="none"/>
        <ellipse cx="38" cy="58" r="4" rx="3.5" ry="5.5" fill="#c93a3a" stroke="#8b1515" stroke-width="0.5"/>
        <path d="M 48 38 L 52 48" stroke="#8b6f3a" stroke-width="1.5" fill="none"/>
        <ellipse cx="54" cy="52" r="4" rx="3.5" ry="5.5" fill="#c93a3a" stroke="#8b1515" stroke-width="0.5" transform="rotate(15 54 52)"/>
      </svg>
      <p class="desc-general">Árbol siempreverde mediano (10-20 m), copa densa y globosa. Especie clave del bosque esclerófilo.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, opuestas, ovado-elípticas (3-7 cm), coriáceas, verde oscuro brillante por arriba, glaucas (blanco-azuladas) por debajo. Aromáticas al estrujarlas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, lisa en jóvenes, agrietada longitudinalmente en adultos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Diminutas, blanco-amarillentas, agrupadas en panículas axilares. Fruto en drupa rojo intenso brillante (1-1,5 cm) al madurar en otoño, comestible.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Cryptocarya</b>: del griego <i>kryptós</i> (oculto) + <i>káryon</i> (nuez), por la semilla oculta en el fruto. <b>alba</b>: del latín, 'blanca'.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>pengu</b>, <b>peumo</b> o <b>peuwüm</b>. Es una palabra raíz presente en muchos topónimos de Chile central como <i>Peumo</i> (O'Higgins).</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Laderas con orientación sur (umbrías) y quebradas húmedas del valle central y cordilleras.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El fruto del peumo se comía tradicionalmente con un truco curioso: NO se mastica el carozo (es muy duro y resinoso). Se cocían en agua tibia hasta que la pulpa se ablandara y luego se chupaban, escupiendo la semilla. La pulpa tiene sabor entre dulce y resinoso, muy distinto a cualquier fruta cultivada.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Cryptocarya%20alba" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Cryptocarya%20alba&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Cryptocarya%20alba" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="dasyphyllum-diacanthoides" data-buscable="dasyphyllum diacanthoides trevo palo santo tayu asteraceae maule nuble biobio la araucania los rios los lagos aysen arbol grande del bosque valdiviano hasta 25 m tronco recto unico arbol grande de la familia asteraceae en chile nativo endemico de chile y argentina en mapudungun se llama trevo o trewo tambien tayu palabras primarias sin descomposicion documentada" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 09 · <span class="familia-tag">Asteraceae</span></div>
    <h2 class="nombre-cientifico"><em>Dasyphyllum diacanthoides</em> <span class="autor">(Less.) Cabrera</span></h2>
    <div class="nombres-comunes">Trevo, Palo santo, Tayú</div>
    <div class="status-badge status-endemico-region" title="Habita el bosque valdiviano de Chile y zonas vecinas de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Dasyphyllum diacanthoides">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 55 Q 35 48 65 35" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 35 45 C 24 35, 26 22, 42 28 C 38 38, 38 42, 35 45" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 35 45 L 28 50 M 35 45 L 34 53" stroke="#c9a877" stroke-width="1.2"/>
        <path d="M 52 40 L 58 48" stroke="#8b6f3a" stroke-width="1.5" fill="none"/>
        <circle cx="58" cy="48" r="4.5" fill="#e8e4d4" stroke="#8b6f3a" stroke-width="0.5"/>
        <path d="M 58 48 L 64 54 M 59 49 L 66 51 M 57 47 L 62 43" stroke="#6b6b6b" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol grande del bosque valdiviano (hasta 25 m), tronco recto. Único árbol grande de la familia Asteraceae en Chile.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovado-lanceoladas (3-7 cm), coriáceas, verde oscuro brillante. Provistas de dos espinas punzantes en la base de la yema axilar.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, agrietada en placas en árboles adultos. Tronco recto, limpio y cilíndrico.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores reunidas en capítulos terminales pequeños, blanco-amarillentos, rodeados de brácteas rígidas. Fruto: aquenio velloso provisto de un vilano blanco que facilita su dispersión por el viento.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Dasyphyllum</b>: del griego <i>dasýs</i> (peludo) + <i>phýllon</i> (hoja). <b>diacanthoides</b>: 'parecido a Diacantha', por sus dos espinas axilares.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>trevo</b> o <b>trewo</b>, también <b>tayú</b>. Palabras primarias sin descomposición documentada.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Bosque valdiviano y norpatagónico. Cordillera de los Andes y de la Costa.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Esta es una rareza botánica mundial: casi todas las Asteraceae son hierbas o arbustos pequeños (piensa en margaritas, girasoles, lechugas, alcachofas). Pero en Chile, la familia desarrolló un árbol gigante que compite con los Nothofagus por luz. Es un caso evolutivo único: las 'margaritas' se transformaron en árboles del bosque.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Dasyphyllum%20diacanthoides" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Dasyphyllum%20diacanthoides&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Dasyphyllum%20diacanthoides" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="drimys-winteri" data-buscable="drimys winteri canelo foike winteraceae coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania los rios los lagos aysen magallanes arbol siempreverde hasta 20 m tronco grisaceo poco ramificado arbol sagrado del pueblo mapuche nativo no endemico de chile en mapudungun se llama foike foye o voigue los lideres mapuches que portaban un baston de canelo se llamaban ngen foye que significa duenos del canelo ngen dueno espiritu protector" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 10 · <span class="familia-tag">Winteraceae</span></div>
    <h2 class="nombre-cientifico"><em>Drimys winteri</em> <span class="autor">J.R.Forst. &amp; G.Forst.</span></h2>
    <div class="nombres-comunes">Canelo, Foike</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina, con la distribución latitudinal más amplia de los árboles chilenos.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Drimys winteri">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 65 65 Q 40 50 15 35" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 38 44 C 48 34, 52 14, 32 26 C 26 34, 30 42, 38 44" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 45 48 L 52 53" stroke="#8b6f3a" stroke-width="1.2" fill="none"/>
        <g transform="translate(54,55)">
          <path d="M 0 0 L -4 -6 M 0 0 L 4 -6 M 0 0 L 7 -2 M 0 0 L 6 4 M 0 0 L 1 7 M 0 0 L -4 6 M 0 0 L -7 2 M 0 0 L -6 -3" stroke="#2a2a2a" stroke-width="2.5" stroke-linecap="round"/>
          <path d="M 0 0 L -4 -6 M 0 0 L 4 -6 M 0 0 L 7 -2 M 0 0 L 6 4 M 0 0 L 1 7 M 0 0 L -4 6 M 0 0 L -7 2 M 0 0 L -6 -3" stroke="white" stroke-width="1.5" stroke-linecap="round"/>
          <circle cx="0" cy="0" r="2.5" fill="#f0d96a"/>
        </g>
      </svg>
      <p class="desc-general">Árbol siempreverde (hasta 20 m), tronco grisáceo poco ramificado. Árbol sagrado del pueblo mapuche.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, elíptico-oblongas (5-15 cm), coriáceas, verde oscuro brillante por arriba y glauco-blanquecinas por el envés. Olor picante al estrujarlas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-clara, lisa, suave. Rica en taninos y vitamina C (la 'corteza de Winter' antiescorbútica).</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Blancas, jazminoides, fragantes, agrupadas en umbelas terminales o axilares (5-7 pétalos). Florecen en primavera. Fruto en baya negro-azulada de varias semillas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Drimys</b>: del griego <i>drimýs</i> (acre, picante), por el sabor de su corteza. <b>winteri</b>: por el capitán John Winter, que en 1578 acompañó a Francis Drake y usó esta corteza para curar el escorbuto.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>foike</b>, <b>foye</b> o <b>voigue</b>. Los líderes mapuches que portaban un bastón de canelo se llamaban <b>ngen-foye</b>, que significa 'dueños del canelo' (<i>ngen</i> = dueño, espíritu protector).</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Sitios húmedos cercanos a cursos de agua y mallines.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>John Winter, navegando con Francis Drake en 1578, descubrió que la corteza de este árbol curaba el escorbuto que devastaba a sus marineros. La llevó a Europa como 'corteza de Winter' y se convirtió en uno de los primeros remedios contra esta enfermedad. Razón: tiene altísimo contenido de vitamina C. Los mapuches ya lo sabían: usaban el foike como medicina mucho antes de la llegada de los europeos.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Drimys%20winteri" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Drimys%20winteri&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Drimys%20winteri" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="embothrium-coccineum" data-buscable="embothrium coccineum notro ciruelillo treumun fosforito proteaceae maule nuble biobio la araucania los rios los lagos aysen magallanes arbol pequeno o arbusto 6 15 m copa angosta famoso por su floracion espectacular nativo no endemico de chile en mapudungun se llama notru notro o treumun son palabras raiz sin descomposicion documentada" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 11 · <span class="familia-tag">Proteaceae</span></div>
    <h2 class="nombre-cientifico"><em>Embothrium coccineum</em> <span class="autor">J.R.Forst. &amp; G.Forst.</span></h2>
    <div class="nombres-comunes">Notro, Ciruelillo, Treumún, Fosforito</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina, con amplia distribución austral.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Embothrium coccineum">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 20 60 Q 40 50 55 35" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 40 45 C 50 35, 45 15, 30 25 Z" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
        <g stroke="#c93a3a" stroke-width="2.5" stroke-linecap="round" fill="none">
          <path d="M 48 38 Q 62 30 68 34"/>
          <path d="M 46 36 Q 58 22 64 25"/>
          <path d="M 42 42 Q 58 44 62 38"/>
        </g>
        <g stroke="#f0d96a" stroke-width="1.2" stroke-linecap="round" fill="none">
          <path d="M 68 34 L 73 36"/>
          <path d="M 64 25 L 68 24"/>
          <path d="M 62 38 L 66 39"/>
        </g>
      </svg>
      <p class="desc-general">Árbol pequeño o arbusto (6-15 m), copa angosta. Famoso por su floración espectacular.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes (semicaducas en climas fríos), simples, alternas, lanceoladas (5-12 cm), coriáceas, verde oscuro brillante.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Lisa, gris-clara a parduzca, con lenticelas claras notorias.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Tubulares, escarlatas-coccíneas brillantes, agrupadas en racimos terminales muy llamativos. Florecen en primavera-verano. Atraen al picaflor. Fruto en folículo leñoso con semillas aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Embothrium</b>: del griego <i>en</i> (dentro) + <i>bóthrion</i> (pequeño hoyo), por las anteras hundidas en cavidades. <b>coccineum</b>: del latín, 'escarlata'.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>notru</b>, <b>notro</b> o <b>treumún</b>. Son palabras raíz sin descomposición documentada.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Cordillera de los Andes y la Costa. Especie pionera tras incendios.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El nombre 'fosforito' viene de que su madera arde con tanta facilidad que prende como cerilla, incluso estando verde. Esto, sumado a que es de las primeras especies en colonizar áreas quemadas, la convierte en una especie de doble cara con el fuego: vulnerable a él en su forma adulta, pero ganadora ecológica después del incendio porque coloniza el terreno antes que otras.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Embothrium%20coccineum" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Embothrium%20coccineum&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Embothrium%20coccineum" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="eucryphia-cordifolia" data-buscable="eucryphia cordifolia ulmo muermo cunoniaceae maule nuble biobio la araucania los rios los lagos aysen arbol grande del bosque valdiviano hasta 40 m tronco recto cilindrico floracion blanca espectacular nativo endemico de chile y argentina en mapudungun se llama ngulmo ulmo o muermo son palabras primarias sin descomposicion conocida" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 12 · <span class="familia-tag">Cunoniaceae</span></div>
    <h2 class="nombre-cientifico"><em>Eucryphia cordifolia</em> <span class="autor">Cav.</span></h2>
    <div class="nombres-comunes">Ulmo, Muermo</div>
    <div class="status-badge status-endemico-region" title="Habita el bosque valdiviano chileno y zonas vecinas de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Eucryphia cordifolia">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <g transform="translate(40,40)">
          <path d="M 0 0 C -12 -12, -18 -4, -18 10 C -18 18, -10 18, 0 0" fill="white" stroke="#6b6b6b" stroke-width="0.8"/>
  
<li><a href="#jubaea-chilensis"><span class="indice-num">15</span><span class="indice-nombre"><em>Jubaea chilensis</em><small>Palma chilena</small></span></a></li>
    <li><a href="#laurelia-sempervirens"><span class="indice-num">16</span><span class="indice-nombre"><em>Laurelia sempervirens</em><small>Laurel chileno</small></span></a></li>
    <li><a href="#laureliopsis-philippiana"><span class="indice-num">17</span><span class="indice-nombre"><em>Laureliopsis philippiana</em><small>Tepa</small></span></a></li>
    <li><a href="#lithraea-caustica"><span class="indice-num">18</span><span class="indice-nombre"><em>Lithraea caustica</em><small>Litre</small></span></a></li>
    <li><a href="#lomatia-ferruginea"><span class="indice-num">19</span><span class="indice-nombre"><em>Lomatia ferruginea</em><small>Romerillo</small></span></a></li>
    <li><a href="#lomatia-hirsuta"><span class="indice-num">20</span><span class="indice-nombre"><em>Lomatia hirsuta</em><small>Radal</small></span></a></li>
    <li><a href="#luma-apiculata"><span class="indice-num">21</span><span class="indice-nombre"><em>Luma apiculata</em><small>Arrayán</small></span></a></li>
    <li><a href="#maytenus-boaria"><span class="indice-num">22</span><span class="indice-nombre"><em>Maytenus boaria</em><small>Maitén</small></span></a></li>
    <li><a href="#nothofagus-alessandrii"><span class="indice-num">23</span><span class="indice-nombre"><em>Nothofagus alessandrii</em><small>Ruil</small></span></a></li>
    <li><a href="#nothofagus-antarctica"><span class="indice-num">24</span><span class="indice-nombre"><em>Nothofagus antarctica</em><small>Ñirre</small></span></a></li>
    <li><a href="#nothofagus-betuloides"><span class="indice-num">25</span><span class="indice-nombre"><em>Nothofagus betuloides</em><small>Coihue de Magallanes</small></span></a></li>


<article class="ficha" id="jubaea-chilensis" data-buscable="jubaea chilensis palma chilena palma de coquitos cocopalma arecaceae coquimbo valparaiso metropolitana o higgins palma robusta hasta 30 m altura 1 m diametro tronco recto cilindrico caracteristico puede vivir mas de 700 anos nativo endemico de chile en mapudungun antiguo se llamaba lilla la palma y kan kan o llilla sus frutos son palabras raiz sin descomposicion clara hoy estos nombres estan casi olvidados y se usa palma o coquito" data-zonas="Norte,Centro">
  <header class="ficha-header">
    <div class="ficha-num">N° 15 · <span class="familia-tag">Arecaceae</span></div>
    <h2 class="nombre-cientifico"><em>Jubaea chilensis</em> <span class="autor">(Molina) Baill.</span></h2>
    <div class="nombres-comunes">Palma chilena, Palma de coquitos, Cocopalma</div>
    <div class="status-badge status-endemico-chile" title="Exclusiva de Chile central. Monumento Natural desde 1995. En peligro de extinción. Es la palma más austral del mundo y la única palma nativa de Chile.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Jubaea chilensis">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 35 74 L 35 38 L 45 38 L 45 74 Z" fill="#9e9e9e" stroke="#6b6b6b" stroke-width="1"/>
        <path d="M 35 48 L 45 48 M 35 58 L 45 58 M 35 68 L 45 68" stroke="#555" stroke-width="0.8"/>
        <g stroke="#2e6b3f" stroke-width="1.8" fill="none" stroke-linecap="round">
          <path d="M 37 38 Q 22 28 14 36"/>
          <path d="M 37 38 Q 20 18 24 10"/>
          <path d="M 43 38 Q 58 28 66 36"/>
          <path d="M 43 38 Q 60 18 56 10"/>
          <path d="M 40 38 L 40 12"/>
        </g>
        <circle cx="36" cy="42" r="2" fill="#d99060"/><circle cx="40" cy="43" r="1.8" fill="#d99060"/><circle cx="44" cy="41" r="2" fill="#d99060"/>
      </svg>
      <p class="desc-general">Palma robusta (hasta 30 m altura, 1 m diámetro), tronco recto cilíndrico característico. Puede vivir más de 700 años.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, pinnadas gigantes (3-5 m de largo), con numerosos folíolos rígidos verdes, dispuestas en penacho terminal. Las viejas se desprenden dejando cicatrices anulares en el tronco.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Lisa, gris-clara, con marcadas cicatrices anulares de hojas caídas. Aspecto de columna de piedra.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Inflorescencias colgantes amarillentas que salen entre las hojas, con flores macho y hembra en la misma planta (monoica). Fruto: drupa globosa amarillenta (2-3 cm), parecida a un coco en miniatura. La semilla interna es el 'coquito' comestible.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Jubaea</b>: por Juba II, rey de Mauritania (52 a.C. - 23 d.C.), conocido naturalista. <b>chilensis</b>: de Chile.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun antiguo se llamaba <b>lilla</b> (la palma) y <b>kan-kan</b> o <b>llilla</b> (sus frutos). Son palabras raíz, sin descomposición clara. Hoy estos nombres están casi olvidados y se usa 'palma' o 'coquito'.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Reductos en La Campana, Ocoa, Cocalán y Palmas de Tilama.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>¿Por qué las palmas chilenas aparecen desparramadas por las laderas de los cerros? Porque el degú (<i>Octodon degus</i>), un roedor endémico de Chile central, recoge los coquitos y los lleva a sus madrigueras. Olvida muchos en el camino y entierra otros, dispersando las semillas cerro arriba. Hoy esta relación está en peligro: la rata negra (<i>Rattus rattus</i>), introducida desde Europa, devora las semillas en vez de dispersarlas. El degú es el verdadero jardinero de los palmares.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Jubaea%20chilensis" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Jubaea%20chilensis&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Jubaea%20chilensis" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="laurelia-sempervirens" data-buscable="laurelia sempervirens laurel chileno trihue tihue atherospermataceae maule nuble biobio la araucania los rios los lagos arbol siempreverde grande hasta 40 m tronco recto copa amplia y densa nativo endemico de chile en mapudungun se llama trihue tihue o triwe el toponimo trihueco en el sur de chile deriva de este nombre" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 16 · <span class="familia-tag">Atherospermataceae</span></div>
    <h2 class="nombre-cientifico"><em>Laurelia sempervirens</em> <span class="autor">(Ruiz &amp; Pav.) Tul.</span></h2>
    <div class="nombres-comunes">Laurel chileno, Trihue, Tihue</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile centro-sur. No se encuentra en ningún otro país.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Laurelia sempervirens">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 52 Q 40 46 68 34" stroke="#8b6f3a" stroke-width="1.8" fill="none"/>
        <path d="M 32 48 C 22 34, 25 20, 42 28 C 36 38, 36 44, 32 48" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 52 42 C 44 26, 50 14, 64 24 C 55 32, 55 38, 52 42" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="1"/>
        <path d="M 24 34 L 25 32 M 29 27 L 31 26 M 48 24 L 50 23" stroke="#1f4e2c" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol siempreverde grande (hasta 40 m), tronco recto, copa amplia y densa.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, opuestas, lanceoladas (5-10 cm), bordes aserrados, verde brillante. Muy aromáticas al estrujarlas (similar al laurel europeo, se usan de condimento).</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-clara, lisa en jóvenes, ligeramente fisurada en adultos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, amarillento-verdosas, agrupadas en racimos terminales. Fruto en aquenio peloso (plumoso) que se dispersa con el viento.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Laurelia</b>: diminutivo del latín <i>laurus</i> (laurel europeo), por su parecido con esa especie. <b>sempervirens</b>: del latín, 'siempre verde'.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>trihue</b>, <b>tihue</b> o <b>triwe</b>. El topónimo <b>Trihueco</b> en el sur de Chile deriva de este nombre.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Sitios húmedos de la cordillera de la Costa y precordillera andina.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Aunque se llama 'laurel chileno' y sus hojas se usan como condimento similar al laurel europeo, no están emparentados: el laurel europeo (Laurus nobilis) es de la familia Lauraceae, mientras que el laurel chileno pertenece a Atherospermataceae, una familia que solo existe en el hemisferio sur (Chile, Australia y Nueva Caledonia). Su presencia aquí es un eco de Gondwana, el supercontinente del Mesozoico.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Laurelia%20sempervirens" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Laurelia%20sempervirens&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Laurelia%20sempervirens" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="laureliopsis-philippiana" data-buscable="laureliopsis philippiana tepa huahuan atherospermataceae maule nuble biobio la araucania los rios los lagos aysen arbol siempreverde grande hasta 30 m copa amplia madera blanda muy usada en artesania nativo endemico de chile y argentina en mapudungun se llama tepa tepu o huahuan wawan cuidado no confundir con el tepu tepualia stipularis que es otra especie distinta" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 17 · <span class="familia-tag">Atherospermataceae</span></div>
    <h2 class="nombre-cientifico"><em>Laureliopsis philippiana</em> <span class="autor">(Looser) Schodde</span></h2>
    <div class="nombres-comunes">Tepa, Huahuán</div>
    <div class="status-badge status-endemico-region" title="Habita el bosque valdiviano chileno y sectores adyacentes de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Laureliopsis philippiana">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 55 C 22 25, 45 20, 62 18 C 50 46, 35 58, 15 55" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 15 55 Q 38 38 62 18" stroke="#1f4e2c" stroke-width="1.5" fill="none"/>
        <path d="M 28 32 L 24 33 M 34 26 L 30 28 M 44 21 L 40 23 M 52 19 L 49 20" stroke="#1f4e2c" stroke-width="1.5"/>
        <circle cx="22" cy="50" r="2" fill="#8b6f3a"/>
        <path d="M 22 50 L 26 56 M 22 50 L 29 52 M 22 50 L 24 58" stroke="#9e9e9e" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol siempreverde grande (hasta 30 m), copa amplia. Madera blanda muy usada en artesanía.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, opuestas, ovado-lanceoladas grandes (5-12 cm), bordes fuertemente aserrados, verde oscuro brillante por arriba, más claras por debajo. Aromáticas al estrujar.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Lisa, gris-clara, con lenticelas notorias en árboles jóvenes.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, verde-amarillentas, agrupadas en racimos axilares. Fruto en aquenio peloso plumoso, dispersado por el viento.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Laureliopsis</b>: 'parecido a Laurelia' (del griego <i>-opsis</i> = aspecto, apariencia). <b>philippiana</b>: por Rodulfo Amando Philippi, naturalista alemán-chileno del siglo XIX, padre de la botánica chilena moderna.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>tepa</b>, <b>tepu</b> o <b>huahuán</b> (wawan). <b>Cuidado:</b> NO confundir con el <i>tepú</i> (Tepualia stipularis), que es otra especie distinta.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Bosque siempreverde de la cordillera de la Costa y los Andes.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>La madera de tepa es tan dócil y predecible que los artesanos de Chiloé y la Patagonia la prefieren para tallar máscaras ceremoniales, instrumentos musicales (kultrún) y artesanías finas. Sin embargo, es tan blanda y poco resistente a la pudrición que es inútil en exteriores: una contradicción curiosa para un árbol de un bosque tan lluvioso.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Laureliopsis%20philippiana" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Laureliopsis%20philippiana&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Laureliopsis%20philippiana" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="lithraea-caustica" data-buscable="lithraea caustica litre anacardiaceae atacama coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania arbol o arbusto siempreverde mediano 5 12 m copa redondeada densa esclerofilo tipico de chile central nativo endemico de chile en mapudungun se llama litre o lithi palabra raiz que paso directo al nombre cientifico los mapuches conocian tan bien sus propiedades alergenicas que aconsejaban no dormir bajo su sombra" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 18 · <span class="familia-tag">Anacardiaceae</span></div>
    <h2 class="nombre-cientifico"><em>Lithraea caustica</em> <span class="autor">(Molina) Hook. &amp; Arn.</span></h2>
    <div class="nombres-comunes">Litre</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. Especie común y dominante del bosque esclerófilo.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Lithraea caustica">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 18 48 C 20 25, 42 22, 60 26 C 52 48, 38 58, 18 48" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 18 48 Q 38 37 60 26" stroke="#f0d96a" stroke-width="1.5" fill="none"/>
        <path d="M 28 42 Q 25 35 24 32 M 38 37 Q 35 28 34 24 M 48 32 Q 46 24 45 20" stroke="#f0d96a" stroke-width="1" fill="none"/>
        <circle cx="20" cy="56" r="2.5" fill="#e8e4d4" stroke="#6b6b6b" stroke-width="0.5"/>
        <circle cx="25" cy="58" r="2" fill="#e8e4d4" stroke="#6b6b6b" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol o arbusto siempreverde mediano (5-12 m), copa redondeada densa. Esclerófilo típico de Chile central.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovado-oblongas (3-7 cm), coriáceas, verde oscuro brillante, con borde entero ondulado. Nervaduras amarillas muy ramificadas y visibles por ambas caras.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, agrietada longitudinalmente. Madera rojiza extremadamente dura y duradera.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, verde-amarillentas, agrupadas en panículas axilares e inflorescencias cortas. Fruto en drupa pequeña (4-5 mm), blanco-amarillenta, seca y aplastada al madurar.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Lithraea</b>: latinización del mapudungun <i>litre</i>. <b>caustica</b>: del latín <i>causticus</i> (que quema), por sus propiedades urticantes.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>litre</b> o <b>lithi</b>, palabra raíz que pasó directo al nombre científico. Los mapuches conocían tan bien sus propiedades alergénicas que aconsejaban no dormir bajo su sombra.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Laderas con orientación norte (solanas) y llanos secos del valle central.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El dicho popular '¿Te picó el litre?' tiene base científica. El árbol contiene uroshioles, los mismos compuestos químicos que la hiedra venenosa norteamericana (poison ivy). Curiosamente, no todas las personas reaccionan: aproximadamente un tercio de la población es altamente sensible y desarrolla una dermatitis severa con picazón intensa y ampollas. Según la tradición popular, para evitar el sarpullido hay que saludar al árbol con respeto ("Buenos días, señor Litre") al pasar cerca.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Lithraea%20caustica" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Lithraea%20caustica&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Lithraea%20caustica" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="lomatia-ferruginea" data-buscable="lomatia ferruginea romerillo fuinque huinque proteaceae biobio la araucania los rios los lagos aysen magallanes arbol pequeno o arbusto 3 10 m copa angosta ornamental por su follaje y flores nativo endemico de chile y argentina en mapudungun se llama fuinque huinque o wingkul wingkul en mapudungun general tambien significa cerro o loma lo que sugiere una asociacion con su habitat de quebradas y faldas montanosas" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 19 · <span class="familia-tag">Proteaceae</span></div>
    <h2 class="nombre-cientifico"><em>Lomatia ferruginea</em> <span class="autor">(Cav.) R.Br.</span></h2>
    <div class="nombres-comunes">Romerillo, Fuinque, Huinque</div>
    <div class="status-badge status-endemico-region" title="Habita el bosque valdiviano y norpatagónico de Chile y Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Lomatia ferruginea">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 65 L 55 25" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <path d="M 28 52 Q 14 48 20 40 Q 30 45 32 50 Z" fill="#2e6b3f"/>
        <path d="M 42 38 Q 28 32 34 24 Q 44 28 46 34 Z" fill="#2e6b3f"/>
        <path d="M 52 28 Q 44 14 50 10 Q 56 16 54 24 Z" fill="#4a8e5e"/>
        <circle cx="48" cy="52" r="5" fill="#c93a3a" stroke="#8b1515" stroke-width="0.5"/>
        <circle cx="58" cy="44" r="4.5" fill="#2a2a2a" stroke="black" stroke-width="0.5"/>
        <path d="M 40 48 L 48 52 M 48 38 L 58 44" stroke="#8b6f3a" stroke-width="1.2"/>
      </svg>
      <p class="desc-general">Árbol pequeño o arbusto (3-10 m), copa angosta. Ornamental por su follaje recortado y flores bicolor.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, compuestas pinnadas o bipinnadas (10-25 cm), con folíolos finamente divididos y aspecto de helecho. Verde oscuro mate por arriba y cubiertas de una pubescencia de color óxido o herrumbre por debajo (de ahí <i>ferruginea</i>).</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-grisácea, delgada y con lenticelas. Ramas jóvenes densamente cubiertas de pelos aterciopelados color óxido.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Tubulares, arqueadas, amarillo-anaranjadas intensas con llamativos tonos rojos, dispuestas en racimos axilares cortos. Florecen en primavera y verano. Fruto en folículo leñoso arqueado (3-4 cm) que se abre liberando semillas aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Lomatia</b>: del griego <i>lóma</i> (borde, franja), por el borde alado de las semillas. <b>ferruginea</b>: del latín <i>ferrugineus</i> (color herrumbre), por la pubescencia oxidada de las ramas jóvenes.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>fuinque</b>, <b>huinque</b> o <b>wingkul</b>. <b>Wingkul</b> en mapudungun general también significa 'cerro o loma', lo que sugiere una asociación con su hábitat de quebradas y faldas montañosas.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Sitios húmedos y umbríos del bosque valdiviano y norpatagónico, tanto en la Costa como en los Andes.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Es una de las especies preferidas por el picaflor chico (<i>Sephanoides sephaniodes</i>), el único picaflor que vive todo el año en los bosques templados del sur. Sus flores tubulares están diseñadas evolutivamente para que solo el pico largo y la lengua de esta ave puedan alcanzar el néctar profundo, asegurando una polinización exclusiva. Es coevolución a la chilena.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Lomatia%20ferruginea" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Lomatia%20ferruginea&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Lomatia%20ferruginea" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="lomatia-hirsuta" data-buscable="lomatia hirsuta radal raral nogal silvestre proteaceae coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania los rios los lagos aysen arbol mediano 8 15 m copa irregular sus hojas y corteza tienen usos medicinales tradicionales nativo no endemico de chile en mapudungun se llama radal raral o notru palabras raiz sin descomposicion documentada el toponimo radal siete tazas en el maule debe su nombre a este arbol" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 20 · <span class="familia-tag">Proteaceae</span></div>
    <h2 class="nombre-cientifico"><em>Lomatia hirsuta</em> <span class="autor">(Lam.) Diels</span></h2>
    <div class="nombres-comunes">Radal, Raral, Nogal silvestre</div>
    <div class="status-badge status-nativo" title="Habita en Chile, Argentina, Bolivia, Perú y Ecuador, con amplia distribución andina.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Lomatia hirsuta">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 22 52 C 22 28, 42 22, 60 28 C 54 50, 40 58, 22 52" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="1.5"/>
        <path d="M 22 52 Q 41 40 60 28" stroke="#1f4e2c" stroke-width="1.5" fill="none"/>
        <path d="M 22 52 L 15 56" stroke="#8b6f3a" stroke-width="2" stroke-linecap="round"/>
        <circle cx="26" cy="46" r="1" fill="#8b6f3a"/><circle cx="32" cy="42" r="1" fill="#8b6f3a"/>
        <circle cx="62" cy="34" r="2" fill="#e8e4d4" stroke="#8b6f3a" stroke-width="0.5"/>
        <circle cx="58" cy="40" r="2" fill="#e8e4d4" stroke="#8b6f3a" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol mediano (8-15 m), copa irregular. Sus hojas grandes y corteza tienen gran valor medicinal tradicional.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovadas a elípticas grandes (6-15 cm), bordes regularmente aserrados con dientes gruesos, coriáceas. Verde oscuro brillante por arriba, pubescentes en las nervaduras del envés.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-oscura, agrietada longitudinalmente en placas cuadrangulares en árboles maduros. Ramas jóvenes cubiertas de vellosidades oxidadas.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores pequeñas, blanco-cremosas o verdosas, cubiertas de vellosidades hirsutas, en racimos axilares. Fruto en folículo leñoso oblongo (3 cm) que contiene semillas aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Lomatia</b>: del griego <i>lóma</i> (borde, franja). <b>hirsuta</b>: del latín, 'peluda o erizada', por la pubescencia densa que cubre sus flores y yemas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>radal</b>, <b>raral</b> o <b>ñotru</b>. Palabras raíz sin descomposición documentada. El topónimo <b>Radal Siete Tazas</b> en el Maule debe su nombre a la abundancia histórica de este árbol en la zona.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Cordillera de los Andes y faldeos semi-húmedos desde Coquimbo hasta Aysén. Tolera bien la sequía estival central.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>En la medicina tradicional mapuche y campesina, la infusión de hojas de radal es el remedio por excelencia para aliviar afecciones respiratorias crónicas, tos y asma. Además, de su corteza y raíces se extrae un tinte café-oscuro tradicional usado para teñir lanas. Curioso: aunque se le llama 'nogal silvestre' por el veteado de su hermosa madera, no guarda ningún parentesco con el nogal verdadero (Juglans).</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Lomatia%20hirsuta" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Lomatia%20hirsuta&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Lomatia%20hirsuta" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="luma-apiculata" data-buscable="luma apiculata arrayan palo colorado temu myrtaceae coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania los rios los lagos aysen arbol pequeno a mediano 8 20 m tronco frecuentemente retorcido y multitruncal famoso por su corteza color canela nativo endemico de chile y argentina en mapudungun se llama luma kelumamull o temu kelumamull es palabra compuesta kelu rojo mamull palo madera palo rojo en reference a su corteza anaranjada canela tan caracteristica" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 21 · <span class="familia-tag">Myrtaceae</span></div>
    <h2 class="nombre-cientifico"><em>Luma apiculata</em> <span class="autor">(DC.) Burret</span></h2>
    <div class="nombres-comunes">Arrayán, Palo colorado, Temu</div>
    <div class="status-badge status-endemico-region" title="Crece en Chile y Argentina, asociado a cursos de agua.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Luma apiculata">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 30 74 Q 28 54 36 44 T 44 20" stroke="#d99060" stroke-width="5" fill="none" stroke-linecap="round"/>
        <path d="M 42 48 Q 50 42 54 30" stroke="#d99060" stroke-width="3" fill="none" stroke-linecap="round"/>
        <path d="M 30 65 Q 31 58 34 56" stroke="#f5f1e8" stroke-width="2" fill="none"/>
        <circle cx="44" cy="18" r="8" fill="#1f4e2c"/>
        <circle cx="54" cy="28" r="6" fill="#2e6b3f"/>
        <circle cx="34" cy="42" r="5" fill="#1f4e2c"/>
        <circle cx="50" cy="24" r="2.5" fill="white"/>
        <circle cx="32" cy="38" r="2" fill="white"/>
      </svg>
      <p class="desc-general">Árbol pequeño a mediano (8-20 m), tronco frecuentemente retorcido y multitruncal. Famoso por su corteza color canela fría al tacto.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, opuestas, pequeñas (1-3 cm), ovadas terminadas en una punta corta y nítida (apículo), coriáceas, verde oscuro brillante. Aromáticas al estrujarlas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> <b>La característica más distintiva</b>: color canela-anaranjado intenso, completamente lisa y fría. Se desprende en placas finas dejando parches blancos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Blancas, pequeñas (1.5 cm), con 4 pétalos y un denso penacho central de estambres prominentes. Fruto en baya globosa (5-9 mm), negro-purpúrea al madurar, dulce y comestible.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Luma</b>: latinización directa del nombre mapuche <i>luma</i>. <b>apiculata</b>: del latín <i>apiculus</i> (punta corta), por la pequeña punta aguzada que corona el ápice de sus hojas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>luma</b>, <b>kelümamüll</b> o <b>temu</b>. El término <b>kelümamüll</b> es descriptivo y ceremonial: <b>kelü</b> (rojo) + <b>mamüll</b> (madera/palo) = 'palo rojo', aludiendo al impactante color de sus troncos desnudos.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Siempre asociado a terrenos húmedos, riberas de ríos, esteros y orillas de lagos del sur de Chile.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El famoso 'Bosque de Arrayanes' en la península de Quetrihué (Argentina) dio pie a una persistente leyenda urbana: se dice que el mismísimo Walt Disney se inspiró en sus troncos retorcidos color canela y en la luz mística del lugar para diseñar el bosque de la película animada Bambi (1942). Aunque es un mito desmentido, grafica el impacto visual de caminar bajo este dosel arbóreo de hadas.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Luma%20apiculata" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Luma%20apiculata&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Luma%20apiculata" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="maytenus-boaria" data-buscable="maytenus boaria maiten maitencillo celastraceae atacama coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania los rios los lagos aysen arbol siempreverde de copa redondeada y follaje colgante 10 20 m muy elegante nativo no endemico de chile en mapudungun se llama maghten maiten o mawen palabra que paso directamente al nombre cientifico" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 22 · <span class="familia-tag">Celastraceae</span></div>
    <h2 class="nombre-cientifico"><em>Maytenus boaria</em> <span class="autor">Molina</span></h2>
    <div class="nombres-comunes">Maitén, Maitencillo</div>
    <div class="status-badge status-nativo" title="Habita en Chile, Argentina, Uruguay, Paraguay, Bolivia y sur de Brasil.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Maytenus boaria">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 72 L 40 45" stroke="#8b6f3a" stroke-width="2.5"/>
        <path d="M 40 45 Q 22 35 18 55 M 40 42 Q 58 32 64 50 M 40 45 L 40 18" stroke="#8b6f3a" stroke-width="1.5" fill="none"/>
        <path d="M 18 55 C 16 62, 20 68, 22 72 M 64 50 C 66 58, 62 66, 60 70" stroke="#6b9c4a" stroke-width="2" fill="none" stroke-linecap="round"/>
        <circle cx="40" cy="24" r="14" fill="#6b9c4a" opacity="0.85"/>
        <circle cx="32" cy="35" r="10" fill="#4a8e5e" opacity="0.9"/>
        <circle cx="48" cy="32" r="11" fill="#6b9c4a" opacity="0.9"/>
      </svg>
      <p class="desc-general">Árbol siempreverde de copa redondeada y ramas péndulas (10-20 m). Follaje grácil que recuerda al sauce llorón.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, elíptico-lanceoladas pequeñas (3-6 cm), bordes finamente aserrados, verde claro brillante. Dispuestas de forma colgante.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, lisa en especímenes jóvenes; agrietada de forma rugosa y longitudinal en adultos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores diminutas, verde-amarillentas, agrupadas en las axilas de las hojas. Fruto en cápsula pequeña coriácea (5 mm) amarilla, que al abrirse en dos valvas revela 1 o 2 semillas envueltas en un arilo rojo intenso.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Maytenus</b>: latinización directa de la palabra mapuche <i>maitén</i>. <b>boaria</b>: del latín <i>bos, bovis</i> (buey/vaca), debido a la gran preferencia que muestra el ganado bovino por ramonear sus hojas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>maghtén</b>, <b>maitén</b> o <b>maweñ</b>. Es una palabra raíz pura que pasó directo al inventario internacional de la botánica.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Distribución sumamente amplia. Crece en llanos húmedos, quebradas y valles desde Atacama hasta los archipiélagos de Aysén.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El epíteto de la especie (<i>boaria</i>) es literal: las vacas sienten tal devoción por sus hojas tiernas que pueden ramonear y descopar un árbol joven en pocas horas. En los campos chilenos se dice tradicionalmente que un maitén con su "falda" perfectamente recortada a la misma altura en un potrero es la firma visual del ganado que se ha alimentado de él durante el invierno, cuando el pasto escasea.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Maytenus%20boaria" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Maytenus%20boaria&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Maytenus%20boaria" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-alessandrii" data-buscable="nothofagus alessandrii ruil hualo del maule nothofagaceae maule arbol caducifolio mediano a grande hasta 30 m endemismo restringido y en peligro critico nativo endemico de chile en mapudungun se llama ruil o ruy palabra raiz sin descomposicion conocida" data-zonas="Centro">
  <header class="ficha-header">
    <div class="ficha-num">N° 23 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus alessandrii</em> <span class="autor">Espinosa</span></h2>
    <div class="nombres-comunes">Ruil, Hualo del Maule</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de la Región del Maule. Monumento Natural desde 1995. En peligro crítico de extinción (UICN).">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus alessandrii">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 22 50 C 20 28, 38 18, 58 24 C 52 46, 38 56, 22 50" fill="#6b9c4a" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 22 50 Q 40 36 58 24" stroke="#1f4e2c" stroke-width="1.5" fill="none"/>
        <path d="M 30 43 L 26 36 M 36 39 L 32 30 M 42 35 L 38 25 M 48 31 L 46 22" stroke="#1f4e2c" stroke-width="1" fill="none"/>
        <circle cx="60" cy="32" r="3.5" fill="#c9a877" stroke="#8b6f3a" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol caducifolio mediano a grande (hasta 30 m). Uno de los endemismos forestales más restringidos y amenazados del planeta.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, simples, alternas, ovadas con base redondeada (4-8 cm), márgenes marcadamente dentados. Destacan sus nervaduras secundarias paralelas muy rectas y hundidas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parda, lisa en jóvenes; agrietada longitudinalmente en surcos largos y gruesos en la madurez.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores unisexuales inconspicuas (planta monoica). El fruto está formado por una cúpula leñosa dividida en 4 valvas que encierran 3 pequeñas nueces aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: del griego <i>nóthos</i> (falso) + <i>phagós</i> (haya) = 'falso haya'. <b>alessandrii</b>: epíteto dedicado a Arturo Alessandri Palma, Presidente de Chile, bajo cuyo mandato se estudió la flora de la región.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>ruil</b> o <b>rüy</b>. Es un término primario mapuche propio de las comunidades esclerófilas andinas y de la costa central.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Estrictamente endémico de la cordillera de la Costa de la Región del Maule (provincias de Talca y Cauquenes). Hábitat fragmentado en laderas húmedas de exposición sur.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El ruil es un sobreviviente de un linaje arbóreo prehistórico y hoy se encuentra en Peligro Crítico de Extinción. La masiva reconversión forestal a monocultivos de pino insigne iniciada en la década de 1970 destruyó el 95% de sus bosques originales. Hoy en día, los últimos rodales puros que quedan en el mundo suman menos de 200 hectáreas en total, lo que los vuelve biológicamente irremplazables.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20alessandrii" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20alessandrii&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20alessandrii" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-antarctica" data-buscable="nothofagus antarctica nirre nire roble enano nothofagaceae biobio la araucania los rios los lagos aysen magallanes arbol caducifolio pequeno a mediano 5 15 m o achaparrado en altura tolerante a climas extremos nativo no endemico de chile en mapudungun se llama nirre o nire palabra raiz sin descomposicion clara" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 24 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus antarctica</em> <span class="autor">(G.Forst.) Oerst.</span></h2>
    <div class="nombres-comunes">Ñirre, Ñire, Roble enano</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina, hasta Tierra del Fuego.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus antarctica">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 25 54 C 20 35, 34 22, 54 26 C 50 44, 40 56, 25 54" fill="#d99060" stroke="#8b6f3a" stroke-width="1.2"/>
        <path d="M 25 54 Q 39 40 54 26" stroke="#8b6f3a" stroke-width="1.2" fill="none"/>
        <path d="M 30 32 Q 26 28 34 24 T 44 23" fill="none" stroke="#8b6f3a" stroke-width="1"/>
        <path d="M 22 70 Q 28 58 24 54" stroke="#8b6f3a" stroke-width="2" fill="none"/>
      </svg>
      <p class="desc-general">Árbol caducifolio pequeño a mediano (5-15 m) o arbusto achaparrado de alta montaña. Altamente tolerante a fríos extremos y vientos patagónicos.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, simples, alternas, ovadas a redondeadas muy pequeñas (1.5-3 cm), de bordes irregularmente lobulados u ondulados (crenados). En otoño viran a amarillos intensos y rojos encendidos. Aroma dulce resinoso al brotar.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-oscura, rugosa, agrietada en escamas longitudinales compactas. Troncos y ramas marcadamente tortuosos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta monoica con flores masculinas solitarias de anteras rojas. Fruto formado por una cúpula pequeña con 4 valvas sutiles que liberan 3 nueces diminutas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>antarctica</b>: del latín, hace referencia a sus colonias en los territorios australes y subantárticos de América del Sur.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>ñirre</b> o <b>ñire</b>, término que alude directamente al porte bajo o matorral denso que forma la especie en la cordillera, sirviendo de refugio para la fauna local.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Zonas cordilleranas andinas altas y estepa patagónica húmeda, extendiéndose continuamente hasta el archipiélago de Tierra del Fuego.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El ñirre es un maestro de la supervivencia extrema. En llanos protegidos crece erguido como un árbol tradicional, pero en los filos andinos helados expuestos al viento patagónico persistente, adopta una forma postrada o rastrera llamada <i>Krummholz</i> (madera torcida). Forma densos "ñirrantales" que actúan como bonsáis gigantes de apenas 50 cm de altura, capaces de soportar metros de nieve encima sin quebrarse.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20antarctica" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20antarctica&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20antarctica" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-betuloides" data-buscable="nothofagus betuloides coihue de magallanes coigue magallanico guindo nothofagaceae los lagos aysen magallanes arbol siempreverde mediano a grande hasta 25 m forma el bosque mas austral del mundo nativo no endemico de chile en mapudungun se llama coihue los yamanas y selknam pueblos originarios del extremo austral tambien lo conocian en sus territorios aunque sus nombres en esas lenguas estan en gran parte perdidos" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 25 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus betuloides</em> <span class="autor">(Mirb.) Oerst.</span></h2>
    <div class="nombres-comunes">Coihue de Magallanes, Coigüe magallánico, Guindo</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina, hasta el Cabo de Hornos.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus betuloides">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 22 48 C 22 30, 36 22, 54 26 C 50 44, 40 54, 22 48" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 22 48 Q 38 37 54 26" stroke="#4a8e5e" stroke-width="1.5" fill="none"/>
        <path d="M 24 38 L 23 36 M 28 32 L 27 30 M 36 27 L 35 25 M 46 26 L 45 24" stroke="#1f4e2c" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol siempreverde mediano a grande (hasta 25 m). Especie emblemática que constituye los bosques arbóreos más australes del planeta.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, elípticas a ovadas y pequeñas (1-2.5 cm), coriáceas, de bordes finamente aserrados de forma regular. Superficie haz verde oscuro, lustrosa y brillante.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-oscura a negra, gruesa, agrietada de forma irregular en bloques longitudinales ásperos en árboles maduros.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta monoica con flores solitarias axilares. El fruto consta de una cúpula leñosa pequeña dividida en 4 valvas que liberan 3 nueces triangulares aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>betuloides</b>: del latín, significa 'parecido al abedul' (género <i>Betula</i>), debido a la gran similitud morfológica y tamaño de sus hojas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun general se agrupa bajo el término común <b>coihue</b> o <b>koywe</b>. Los pueblos australes de los canales (yámanas y kawésqar) y de Tierra del Fuego (selknam) poseían vocablos nativos específicos para este guindo austral, hoy extintos o fragmentados.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Zonas costeras expuestas, fiordos y archipiélagos del extremo sur, desde Chiloé continental hasta el Cabo de Hornos.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Este majestuoso árbol marca el límite forestal absoluto de la Tierra. Crece en la Isla Hornos (Cabo de Hornos) a 56° de latitud sur, desafiando temporales marítimos feroces, vientos huracanados permanentes del oeste y lloviznas gélidas durante todo el año. Más allá de sus colonias costeras en este punto, no sobrevive ningún linaje arbóreo en el planeta; el paisaje da paso definitivo a la tundra subantártica y al océano.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20betuloides" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20betuloides&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20betuloides" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-dombeyi" data-buscable="nothofagus dombeyi coihue coigue nothofagaceae maule nuble biobio la araucania los rios los lagos aysen arbol siempreverde gigante hasta 45 m altura 3 m diametro tronco recto y limpio dominante del bosque valdiviano nativo no endemico de chile en mapudungun se llama koywe coihue o coyam aunque este ultimo tambien se usa para el roble nothofagus obliqua lo que genera confusion" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 26 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus dombeyi</em> <span class="autor">(Mirb.) Oerst.</span></h2>
    <div class="nombres-comunes">Coihue, Coigüe</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus dombeyi">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 50 C 35 48, 50 35, 70 38" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <g fill="#1f4e2c" stroke="#1f4e2c" stroke-width="0.5">
          <path d="M 30 45 Q 24 35 32 38 Z"/>
          <path d="M 40 42 Q 35 32 44 36 Z"/>
          <path d="M 50 39 Q 45 28 52 32 Z"/>
          <path d="M 62 36 Q 58 26 64 30 Z"/>
        </g>
        <circle cx="68" cy="36" r="2.5" fill="#c9a877" stroke="#8b6f3a" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol siempreverde gigante (hasta 45 m altura, 3 m diámetro), tronco recto y limpio. Dominante del bosque valdiviano.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovado-lanceoladas pequeñas (2-4 cm), de bordes finamente aserrados, coriáceas y verde oscuro brillante. Disuestas en planos horizontales densos.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-oscura, agrietada en placas longitudinales gruesas en árboles adultos. Tronco generalmente libre de ramas en la mitad inferior.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, unisexuales (monoica). Fruto en cúpula leñosa pequeña provista de 4 valvas que contienen 3 nueces triangulares aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>dombeyi</b>: por Joseph Dombey, botánico francés que exploró Chile entre 1782 y 1785.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>koywe</b>, <b>coihue</b> o <b>coyam</b> (aunque este último también se usa para el roble Nothofagus obliqua, lo que genera confusión).</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Bosque valdiviano y norpatagónico. Sitios húmedos y profundos tanto en la Costa como en los Andes.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El coihue es uno de los árboles que define el bosque valdiviano. Sus ramas inferiores se desprenden cuando el árbol envejece, dejando un fuste largo y limpio, perfecto para que crezcan en sus copas docenas de especies epífitas: musgos, helechos, líquenes y la enredadera 'copihue' (Lapageria rosea, la flor nacional de Chile) suben por sus troncos. Un solo coihue adulto puede ser un ecosistema vertical con más biodiversidad que muchos prados.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20dombeyi" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20dombeyi&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20dombeyi" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-glauca" data-buscable="nothofagus glauca hualo roble del maule nothofagaceae o higgins maule nuble biobio arbol caducifolio grande hasta 30 m endemico de chile forma los bosques maulinos nativo endemico de chile en mapudungun se llama hualo o wallo palabra raiz sin descomposicion documentada" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 27 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus glauca</em> <span class="autor">(Phil.) Krasser</span></h2>
    <div class="nombres-comunes">Hualo, Roble del Maule</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile centro-sur. Especie vulnerable, afectada por la deforestación histórica.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus glauca">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 22 50 C 20 28, 38 18, 58 24 C 52 46, 38 56, 22 50" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 22 50 Q 40 36 58 24" stroke="#1f4e2c" stroke-width="1.5" fill="none"/>
        <path d="M 46 44 C 48 48, 56 42, 58 24 C 52 42, 50 42, 46 44" fill="#d8ebe0" stroke="#a3c9b0" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol caducifolio grande (hasta 30 m). Endémico de Chile, forma los 'bosques maulinos'.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, simples, alternas, ovado-aserradas, grandes para Nothofagus (5-10 cm), verde por arriba pero <b>glauco-blanquecinas por el envés</b> (rasgo diagnóstico).</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, agrietada en placas rectangulares en árboles adultos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, unisexuales (monoica). Fruto en cúpula con 4 valvas coriáceas que encierran 3 nueces aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>glauca</b>: del griego <i>glaukós</i> (verde-azulado), por el envés glauco característico de sus hojas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>hualo</b> o <b>wallo</b>, palabra raíz sin descomposición documentada.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Cordillera de la Costa y precordillera andina entre O'Higgins y Biobío. Bosques maulinos de transición mediterránea.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El hualo es uno de los árboles que mejor se identifica por su envés foliar: si das vuelta una hoja, el reverso es de un verde claro casi blanquecino (glauco), mientras el haz es verde brillante. Esto le da al bosque maulino un 'efecto plateado' cuando sopla viento, similar al de los álamos pero con tonos más verdes. Es uno de los Nothofagus más amenazados de Chile junto al ruil.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20glauca" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20glauca&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20glauca" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-nitida" data-buscable="nothofagus nitida coihue de chiloe coigue de chiloe nothofagaceae los rios los lagos aysen arbol siempreverde grande hasta 30 m adaptado a suelos saturados de agua y turberas nativo endemico de chile en mapudungun variante huilliche lengua del pueblo mapuche del sur se llama coihue" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 28 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus nitida</em> <span class="autor">(Phil.) Krasser</span></h2>
    <div class="nombres-comunes">Coihue de Chiloé, Coigüe de Chiloé</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. Crece en zonas insulares y costeras del sur, con alta pluviometría.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus nitida">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 22 46 C 22 28, 38 22, 54 26 C 48 44, 40 54, 22 46" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 22 46 Q 38 36 54 26" stroke="#4a8e5e" stroke-width="1.5" fill="none"/>
        <path d="M 32 30 Q 36 32 40 28" stroke="white" stroke-width="1.5" fill="none" stroke-linecap="round"/>
        <path d="M 24 36 L 23 34 M 28 30 L 27 28" stroke="#1f4e2c" stroke-width="0.8"/>
      </svg>
      <p class="desc-general">Árbol siempreverde grande (hasta 30 m). Adaptado a suelos saturados de agua y turberas húmedas.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovado-lanceoladas (2-4 cm), bordes aserrados, verde oscuro <b>muy brillante y lustroso</b> (de ahí <i>nitida</i> = brillante), cutícula cerosa gruesa.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca a oscura, agrietada longitudinalmente con surcos delgados y compactos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, unisexuales (planta monoica). Fruto en cúpula con 4 valvas que protegen 3 pequeñas nueces aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>nitida</b>: del latín, 'brillante, lustrosa', por el brillo reflectante característico de sus hojas al sol.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun, variante huilliche (lengua del pueblo mapuche del sur), se llama simplemente <b>coihue</b> o <b>koywe</b>, compartiendo el nombre raíz con su pariente continental.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Cordillera de la Costa e hiper-húmedas zonas insulares del sur (Chiloé, Aisén), donde llueve más de 3.000 mm anuales.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El coihue de Chiloé es uno de los pocos árboles del mundo adaptados a suelos completamente saturados de agua: crece en turberas donde otras especies se ahogarían. Tiene un sistema radicular superficial con raíces tablares que se extienden lateralmente, atrapando nutrientes de la capa más superficial del suelo. En Chiloé es parte del paisaje icónico junto a los alerces.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20nitida" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20nitida&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20nitida" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-obliqua" data-buscable="nothofagus obliqua roble hualle coyam pellin nothofagaceae o higgins maule nuble biobio la araucania los rios los lagos arbol caducifolio grande hasta 40 m copa amplia dominante del bosque maulino y valdiviano simbolo cultural mapuche nativo no endemico de chile en mapudungun hay tres nombres distintos segun la edad y parte del arbol hualle es el arbol joven coyam o koyam es el arbol adulto y pellin es especificamente la madera del corazon del tronco este vocabulario tan detallado refleja la enorme importancia cultural del arbol para el pueblo mapuche" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 29 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus obliqua</em> <span class="autor">(Mirb.) Oerst.</span></h2>
    <div class="nombres-comunes">Roble, Hualle, Coyam, Pellín</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus obliqua">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 26 54 C 20 38, 32 20, 56 24 C 52 44, 44 56, 26 54" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 26 54 Q 41 38 56 24" stroke="#1f4e2c" stroke-width="1.5" fill="none"/>
        <path d="M 26 54 C 28 58, 34 56, 36 53" fill="none" stroke="#1f4e2c" stroke-width="1.5"/>
        <path d="M 32 32 Q 28 26 36 24 T 46 25" fill="none" stroke="#1f4e2c" stroke-width="1"/>
      </svg>
      <p class="desc-general">Árbol caducifolio grande (hasta 40 m), copa amplia. Dominante del bosque maulino y valdiviano. Símbolo cultural mapuche.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, simples, alternas, ovado-lanceoladas (3-8 cm), con la <b>base asimétrica (oblicua)</b> inconfundible (de ahí <i>obliqua</i>), márgenes lobulado-aserrados. Verde claro.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, agrietada profundamente en placas longitudinales gruesas en árboles maduros. La madera del corazón íntimo (pellín) es rojo-oscura y pesada.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, unisexuales (monoica). Fruto protegido en una cúpula leñosa de 4 valvas cortas con 3 nueces aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>obliqua</b>: del latín, 'oblicua, asimétrica', en directa alusión a la base dispareja de sus hojas.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun hay tres nombres distintos según la edad y parte del árbol: <b>hualle</b> es el árbol joven, <b>coyam</b> o <b>koyam</b> es el árbol adulto, y <b>pellín</b> es específicamente la madera del corazón del tronco. Este vocabulario tan detallado refleja la enorme importancia cultural del árbol para el pueblo mapuche.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Valles centrales, ambas cordilleras desde O'Higgins hasta los lagos sureños. Prefiere suelos ricos y profundos.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El pellín (madera del corazón del roble) es probablemente la madera más duradera de Chile: hay durmientes de ferrocarril y pilares de casas hechos en pellín hace más de 150 años que aún están sanos. Para los mapuches, el coyam era el árbol más sagrado después del foike (canelo): bajo sus copas se realizaban los <i>nguillatún</i> (ceremonias de petición). La palabra 'pellinco' significa 'lugar de pellines' y aparece en muchos topónimos.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20obliqua" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20obliqua&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20obliqua" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="nothofagus-pumilio" data-buscable="nothofagus pumilio lenga roble blanco nothofagaceae maule nuble biobio la araucania los rios los lagos aysen magallanes arbol caducifolio grande hasta 30 m o achaparrado en altitud krummholz forma los bosques caducifolios mas australes del mundo nativo no endemico de chile en mapudungun se llama lenga o ruli el nombre lenga es uno de los mas famosos del lexico forestal chileno y aparece en muchos toponimos" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 30 · <span class="familia-tag">Nothofagaceae</span></div>
    <h2 class="nombre-cientifico"><em>Nothofagus pumilio</em> <span class="autor">(Poepp. &amp; Endl.) Krasser</span></h2>
    <div class="nombres-comunes">Lenga, Roble blanco</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina, hasta Magallanes.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Nothofagus pumilio">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 24 52 C 20 32, 36 20, 56 26 C 50 46, 40 56, 24 52" fill="#c93a3a" stroke="#8b1515" stroke-width="1.5"/>
        <path d="M 24 52 Q 40 39 56 26" stroke="#8b1515" stroke-width="1.5" fill="none"/>
        <path d="M 30 31 C 32 25, 38 26, 42 24 C 46 23, 50 25, 52 26" fill="none" stroke="#8b1515" stroke-width="1"/>
      </svg>
      <p class="desc-general">Árbol caducifolio grande (hasta 30 m), o achaparrado en altitud (krummholz). Tiñe de rojo y dorado los paisajes patagónicos en otoño.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, simples, alternas, ovado-redondeadas pequeñas (2-4 cm), bordes con llamativos **dobles dientes o festones apareados** simétricos entre nervaduras secundarias.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-clara a plomiza, lisa en jóvenes; agrietada horizontalmente en surcos largos en árboles adultos. Surcos profundos ásperos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, unisexuales (monoica). Fruto protegido en una cúpula leñosa de 4 valvas con apéndices foliosos que contiene 3 nueces.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Nothofagus</b>: 'falso haya'. <b>pumilio</b>: del latín, 'enano', debido a su porte achaparrado alfombrante en el límite altitudinal nival.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>lenga</b> o <b>rüli</b>. El nombre <i>lenga</i> es uno de los más famosos del léxico forestal chileno y aparece en muchos topónimos.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Cordillera de los Andes desde el Maule hasta Magallanes. Define con exactitud el límite altitudinal de la vegetación forestal chilena.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>La lenga tiene una característica única: marca el 'timberline' o línea del bosque en la Patagonia chilena. Por encima de cierta altitud, donde otros árboles ya no pueden crecer, la lenga sigue intentando, pero adopta formas postradas o 'achaparradas' llamadas <i>krummholz</i> (palabra alemana para 'madera torcida'). Estos bosques bonsai naturales pueden tener árboles de varias décadas que apenas miden 50 cm de altura.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Nothofagus%20pumilio" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Nothofagus%20pumilio&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Nothofagus%20pumilio" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="persea-lingue" data-buscable="persea lingue lingue linge lauraceae maule nuble biobio la araucania los rios los lagos arbol siempreverde grande hasta 30 m tronco recto y limpio mismo genero que la palta nativo endemico de chile y argentina en mapudungun se llama lingue linge o dungu palabra raiz que paso directamente al nombre cientifico" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 31 · <span class="familia-tag">Lauraceae</span></div>
    <h2 class="nombre-cientifico"><em>Persea lingue</em> <span class="autor">(Ruiz &amp; Pav.) Nees</span></h2>
    <div class="nombres-comunes">Lingue, Linge</div>
    <div class="status-badge status-endemico-region" title="Habita en Chile y un sector vecino de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Persea lingue">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 18 50 C 22 25, 45 22, 62 25 C 52 48, 35 58, 18 50" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="1.5"/>
        <path d="M 18 50 Q 38 38 62 25" stroke="#c9a877" stroke-width="1.5" fill="none"/> <path d="M 24 45 L 20 54" stroke="#8b6f3a" stroke-width="1.5" fill="none"/>
        <ellipse cx="19" cy="58" r="3" rx="2.5" ry="4" fill="#1f1f2e" stroke="black" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol siempreverde grande (hasta 30 m), fuste recto y limpio. Estrechamente emparentado con el palto europeo y americano.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, elíptico-lanceoladas u obovadas (8-15 cm), enteras y coriáceas. Verde oscuro en el haz, envés con fina pubescencia dorada-vellosa. Olor dulce al estrujarlas.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-grisácea, rugosa, agrietada longitudinalmente en la madurez. Históricamente sobreexplotada por su enorme riqueza en taninos curtidores.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, hermafroditas, verde-amarillentas vellosas, reunidas en panículas axilares. Fruto en drupa ovoide negra-azulada lustrosa (1.5 cm) rodeada parcialmente por el cáliz. No comestible.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Persea</b>: del griego antiguo, nombre dado por Teofrasto a un árbol mítico egipcio de frutos dulces. <b>lingue</b>: latinización directa del vocablo mapuche primario.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>lingue</b>, <b>linge</b> o <b>düngu</b>. Nombre nativo directo incorporado a la taxonomía internacional.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Suelos ricos de la cordillera de la Costa y valles húmedos templados desde el Maule hasta los lagos sureños.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El lingue pertenece al mismo género que la palta (<i>Persea americana</i>), aunque sus frutos son muy distintos: pequeñas drupas verdes-negras que no se parecen en nada al aguacate. La explotación masiva de su corteza para curtir cueros entre los siglos XIX y XX (millones de árboles cortados solo para obtener corteza) lo dejó muy reducido en muchas zonas.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Persea%20lingue" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Persea%20lingue&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Persea%20lingue" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="pilgerodendron-uviferum" data-buscable="pilgerodendron uviferum cipres de las guaitecas cipres enano lahuan cupressaceae los rios los lagos aysen magallanes conifera mediana hasta 20 m forma piramidal la conifera mas austral del mundo en turberas y suelos anegados nativo endemico de chile y argentina en mapudungun y en lengua chona pueblo de los canales australes se llama lahuan o tenio la palabra lawen en mapudungun significa tambien medicina y comparte raiz con el alerce" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 32 · <span class="familia-tag">Cupressaceae</span></div>
    <h2 class="nombre-cientifico"><em>Pilgerodendron uviferum</em> <span class="autor">(D.Don) Florin</span></h2>
    <div class="nombres-comunes">Ciprés de las Guaitecas, Ciprés enano, Lahuán</div>
    <div class="status-badge status-endemico-region" title="Habita en el sur de Chile y un sector aledaño de Argentina. Monumento Natural desde 1976. La conífera más austral del mundo.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Pilgerodendron uviferum">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 70 L 40 16" stroke="#8b5a36" stroke-width="2.2" stroke-linecap="round"/>
        <path d="M 40 18 L 30 58 L 50 58 Z" fill="#1f4e2c" stroke="#1f4e2c" stroke-width="0.8"/>
        <path d="M 12 68 Q 16 60 20 68" stroke="#8b5a36" stroke-width="1.8" fill="none"/>
        <path d="M 64 68 Q 66 58 70 68" stroke="#8b5a36" stroke-width="1.8" fill="none"/>
        <line x1="10" y1="68" x2="70" y2="68" stroke="#4a89b8" stroke-width="1.5"/>
      </svg>
      <p class="desc-general">Conífera mediana (hasta 20 m), forma piramidal esbelta. La conífera más austral del mundo, confinada a turberas y suelos permanentemente anegados.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, imbricadas en forma de escamas escuamiformes compactas pequeñas (2-3 mm) dispuestas en parejas opuestas cruzadas en cruz que cubren las ramillas de aspecto tetragonal. Verde-claro resinoso.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-rojiza, delgada, fibrosa, se desprende longitudinalmente en tiras angostas largas. Fuste recto cilíndrico.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta dioica. Conos masculinos y femeninos terminales muy pequeños; conos femeninos globosos con escamas leñosas ganchudas que recuerdan racimos de uvas pequeñas (de ahí <i>uviferum</i>).</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Pilgerodendron</b>: género erigido en honor a Robert Pilger, insigne botánico alemán especialista en coníferas + del griego <i>déndron</i> (árbol). <b>uviferum</b>: del latín <i>uva</i> + <i>fero</i> (llevar), debido a la caprichosa forma de racimo de uvas de sus conos leñosos.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun y en lengua chona de los archipiélagos costeros australes se llama <b>lahuán</b> o <b>tenío</b>. Comparte la raíz <i>lawen</i> (medicina) con el alerce real, denotando reverencia espiritual.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Terrenos pantanosos inundados, turberas de esfagno (<i>Sphagnum</i>) y archipiélagos costeros rocosos desde Valdivia continental hasta Magallanes insular.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Es la única conífera del mundo que prospera en turberas (suelos saturados de agua, ácidos y muy pobres en nutrientes). Tiene raíces 'neumatóforos' que sobresalen del suelo como rodillas, igual que los manglares tropicales, para captar oxígeno. La explotación maderera durante los siglos XIX y XX casi la extinguió en muchas islas, porque su madera es de las más resistentes a la pudrición del mundo.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Pilgerodendron%20uviferum" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Pilgerodendron%20uviferum&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Pilgerodendron%20uviferum" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="podocarpus-nubigenus" data-buscable="podocarpus nubigenus manio macho manio de hojas punzantes podocarpaceae la araucania los rios los lagos aysen conifera mediana a grande hasta 25 m sus hojas pinchan al tocarlas de ahi manio macho nativo endemico de chile y argentina en mapudungun se llama manio o maniu palabra raiz sin descomposicion clara que se aplica a varias especies de coniferas similares" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 33 · <span class="familia-tag">Podocarpaceae</span></div>
    <h2 class="nombre-cientifico"><em>Podocarpus nubigenus</em> <span class="autor">Lindl.</span></h2>
    <div class="nombres-comunes">Mañío macho, Mañío de hojas punzantes</div>
    <div class="status-badge status-endemico-region" title="Habita en el bosque valdiviano de Chile y un sector adyacente de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Podocarpus nubigenus">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 50 L 65 32" stroke="#8b6f3a" stroke-width="2" fill="none"/>
        <g stroke="#1f4e2c" stroke-width="1.8" stroke-linecap="round">
          <line x1="25" y1="47" x2="20" y2="35"/>
          <line x1="35" y1="44" x2="32" y2="30"/>
          <line x1="45" y1="40" x2="42" y2="24"/>
          <line x1="55" y1="36" x2="54" y2="20"/>
          <line x1="30" y1="45" x2="34" y2="58"/>
          <line x1="42" y1="41" x2="48" y2="54"/>
        </g>
        <circle cx="58" cy="35" r="3" fill="#c93a3a"/>
        <circle cx="61" cy="33" r="2" fill="#4a89b8"/>
      </svg>
      <p class="desc-general">Conífera mediana a grande (hasta 25 m). Hojas lineares muy rígidas que pinchan firmemente al tacto (origen de su nombre vernacular 'macho').</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, dispuestas radialmente, lineales-lanceoladas cortas (1.5-3 cm), **rígidas y terminadas en un ápice punzante rígido**. Verde oscuro brillante con dos estomas blanquecinos bajo el envés.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-rojiza, fibrosa, se fragmenta longitudinalmente desprendiéndose en placas delgadas irregulares. Madera de excelente calidad clara.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta dioica. Flores masculinas en amentos cilíndricos solitarios; semillas redondeadas madurando sobre un pedúnculo carnoso carnudo (receptáculo) de color rojo-purpúreo.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Podocarpus</b>: del griego <i>poús, podós</i> (pie) + <i>karpós</i> (fruto), en alusión al pie o receptáculo carnoso modificado que sostiene la semilla. <b>nubigenus</b>: del latín, significa 'nacido o procreado entre las nubes', describiendo sus colonias de altura andina lluviosa.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se agrupa bajo la voz común <b>mañío</b> o <b>mañiu</b>, palabra primaria que describe a este grupo selecto de coníferas de maderas nobles del hemisferio sur.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Sotobosques húmedos, faldeos costeros y andinos con alta pluviometría desde la región de la Araucanía hasta los fiordos de Aisén.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Las coníferas del hemisferio sur (Podocarpus, Saxegothaea, Araucaria) son ecos vivos de Gondwana, el supercontinente que existió hace más de 100 millones de años. Cuando Sudamérica, Australia, Nueva Zelanda y la Antártida estaban unidas, estas familias se distribuyeron por todo el sur. Hoy aún tienen 'primos' en Nueva Zelanda y Tasmania.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Podocarpus%20nubigenus" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Podocarpus%20nubigenus&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Podocarpus%20nubigenus" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="podocarpus-salignus" data-buscable="podocarpus salignus manio de hojas largas manio hembra podocarpaceae maule nuble biobio la araucania los rios los lagos conifera mediana hasta 20 m copa estrecha endemica de chile muy ornamental nativo endemico de chile en mapudungun se llama manio o maniu hembra en contraposicion al manio macho de hojas punzantes" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 34 · <span class="familia-tag">Podocarpaceae</span></div>
    <h2 class="nombre-cientifico"><em>Podocarpus salignus</em> <span class="autor">D.Don</span></h2>
    <div class="nombres-comunes">Mañío de hojas largas, Mañío hembra</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. No se encuentra en ningún otro país.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Podocarpus salignus">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 60 15 Q 45 40 18 52" stroke="#8b6f3a" stroke-width="1.5" fill="none"/>
        <path d="M 44 28 C 30 45, 12 58, 14 66 C 20 58, 40 46, 44 28" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="0.8"/>
        <path d="M 52 20 C 44 38, 28 52, 34 64 C 38 52, 48 40, 52 20" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="0.8"/>
        <circle cx="22" cy="54" r="3" fill="#c93a3a"/>
        <circle cx="20" cy="58" r="2.2" fill="#2e6b3f"/>
      </svg>
      <p class="desc-general">Conífera mediana (hasta 20 m), copa estrecha y elegante. Exclusivamente endémica de Chile, de follaje dócil y flexible (mañío 'hembra').</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, lineares **notoriamente largas, falcadas y flexibles** (5-12 cm), ápice agudo pero suave y no punzante. Haz verde brillante lustroso, envés verde pálido. Similares a hojas de sauce.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-rojiza, fibrosa, se exfolia longitudinalmente desprendiéndose en tiras fibrosas finas. Madera de veteado homogéneo muy cotizada.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta dioica. Conos masculinos cilíndricos agrupados en ramillas; frutos compuestos por una semilla globosa verde-azulada sostenida sobre un receptáculo carnoso rojo-anaranjado dulce.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Podocarpus</b>: 'fruto con pie' (ver mañío macho). <b>salignus</b>: del latín, significa 'parecido o semejante al sauce' (género <i>Salix</i>), aludiendo de forma exacta a la longitud y caída péndula de su follaje.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>mañío</b> o <b>mañiu hembra</b>, adjetivación popular introducida para diferenciar la docilidad inofensiva de sus hojas frente al mañío punzante.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Exclusiva de Chile. Quebradas húmedas, cursos de agua sombreados y laderas costeras desde los faldeos del Maule hasta las provincias de Osorno y Llanquihue.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Es una de las pocas coníferas chilenas exportadas como ornamental al exterior: se usa en jardines de Inglaterra, Irlanda y California desde el siglo XIX. Pero en su hábitat natural está cada vez más restringida y se considera vulnerable. El término 'mañío hembra' versus 'mañío macho' no se refiere al sexo de la planta (ambas son dioicas), sino a la textura de sus hojas: suaves versus punzantes.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Podocarpus%20salignus" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Podocarpus%20salignus&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Podocarpus%20salignus" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="polylepis-tarapacana" data-buscable="polylepis tarapacana quenoa quenua rosaceae arica y parinacota tarapaca antofagasta arbol pequeno y achaparrado 3 5 m raramente mas tronco retorcido uno de los arboles que crece a mayor altitud del mundo nativo no endemico de chile importante el nombre quenoa o quenua no viene del mapudungun sino del quechua y aymara esto se debe a que el arbol habita en el altiplano andino del norte de chile fuera del territorio mapuche historico wallmapu" data-zonas="Norte">
  <header class="ficha-header">
    <div class="ficha-num">N° 35 · <span class="familia-tag">Rosaceae</span></div>
    <h2 class="nombre-cientifico"><em>Polylepis tarapacana</em> <span class="autor">Phil.</span></h2>
    <div class="nombres-comunes">Queñoa, Queñua</div>
    <div class="status-badge status-nativo" title="Habita en el altiplano andino de Chile, Perú, Bolivia y Argentina.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Polylepis tarapacana">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 32 74 Q 28 54 36 44 T 44 26" stroke="#c9a877" stroke-width="4.5" fill="none" stroke-linecap="round"/>
        <path d="M 38 46 Q 48 38 52 32" stroke="#c9a877" stroke-width="2.5" fill="none" stroke-linecap="round"/>
        <path d="M 31 64 L 24 68 M 35 52 L 26 50 M 45 36 L 54 32" stroke="#8b6f3a" stroke-width="1"/>
        <circle cx="44" cy="24" r="9" fill="#4a8e5e" opacity="0.9"/>
        <circle cx="52" cy="30" r="7" fill="#2e6b3f" opacity="0.85"/>
        <circle cx="34" cy="40" r="6" fill="#4a8e5e" opacity="0.9"/>
      </svg>
      <p class="desc-general">Árbol pequeño y ostensiblemente achaparrado (3-5 m), tronco retorcido. Posee el récord mundial como uno de los árboles adaptados a mayor altitud en el planeta.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, compuestas imparipinnadas diminutas (2-3 cm total), con 3-5 folíolos elípticos densos. Haz verde cenizo opaco, envés cubierto de una densa felpa pilosa-plateada protectora.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> **La característica más distintiva**: pardo-rojiza clara, desprendible en múltiples láminas extremadamente finas como papel o pergamino. Actúa como abrigo térmico.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores diminutas, solitarias o en racimos breves péndulos, carentes de pétalos, verde-amarillentas. Fruto seco aquenio, velloso y espinescente, dispersado mecánicamente.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Polylepis</b>: del griego <i>polýs</i> (muchas) + <i>lepís</i> (escama), por su inconfundible tronco laminado en capas concéntricas de aspecto papiláceo. <b>tarapacana</b>: epíteto geográfico descriptivo de la Región de Tarapacá, donde Rodulfo Philippi recolectó el ejemplar tipo.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>El término <b>queñoa</b> o <b>queñua</b> proviene de las lenguas quechua y aymara del norte grande. No guarda relación con el mapudungun central, dado que su ecosistema se ubica a miles de kilómetros del Wallmapu histórico.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Exclusivo del altiplano andino de las regiones de Arica y Parinacota, Tarapacá y Antofagasta. Prospera en laderas de volcanes y grietas rocosas entre los 4.000 y 5.200 msnm.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>La queñoa desafía todas las leyes forestales conocidas: en las faldas del volcán Sajama, crece vigorosamente a 4.800 metros de altitud, donde la presión atmosférica y el oxígeno disponible se reducen a la mitad. Su corteza exfoliante, que se deshace entre los dedos como hojas de libro, retiene colchones de aire estanco entre sus láminas. Esto le permite aislar el fuste de las brutales oscilaciones térmicas diarias del desierto de altura, que caen bajo los -20°C cada noche.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Polylepis%20tarapacana" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Polylepis%20tarapacana&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Polylepis%20tarapacana" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="prosopis-chilensis" data-buscable="prosopis chilensis algarrobo algarrobo blanco fabaceae arica y parinacota tarapaca antofagasta atacama coquimbo valparaiso arbol mediano espinoso hasta 15 m copa muy amplia y aparasolada vainas comestibles nativo no endemico de chile en mapudungun se llama huilco o kuri en quechua se llama tacu la palabra algarrobo que usamos en castellano viene del arabe al jarruba la algarroba" data-zonas="Norte,Centro">
  <header class="ficha-header">
    <div class="ficha-num">N° 36 · <span class="familia-tag">Fabaceae</span></div>
    <h2 class="nombre-cientifico"><em>Prosopis chilensis</em> <span class="autor">(Molina) Stuntz</span></h2>
    <div class="nombres-comunes">Algarrobo, Algarrobo blanco</div>
    <div class="status-badge status-nativo" title="Habita en Chile, Argentina, Bolivia y Perú.">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Prosopis chilensis">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 72 L 40 46" stroke="#5a4d20" stroke-width="3" stroke-linecap="round"/>
        <path d="M 40 46 Q 15 42 12 30 M 40 46 Q 65 42 68 30" stroke="#5a4d20" stroke-width="2" fill="none"/>
        <ellipse cx="40" cy="30" r="24" ry="10" fill="#6b9c4a" opacity="0.85"/>
        <ellipse cx="22" cy="32" r="12" ry="7" fill="#2e6b3f" opacity="0.9"/>
        <ellipse cx="58" cy="32" r="12" ry="7" fill="#2e6b3f" opacity="0.9"/>
        <path d="M 36 34 Q 38 48 35 56" stroke="#f0d96a" stroke-width="2" fill="none" stroke-linecap="round"/>
      </svg>
      <p class="desc-general">Árbol mediano espinoso (hasta 15 m), copa sumamente amplia, extendida y aparasolada. Gran proveedor de vainas nutricionales.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Caducas, compuestas bipinnadas largas (10-25 cm), con numerosos folíolos lineales verde-claro. Armado con fuertes espinas axilares cónicas y blanquecinas de hasta 5 cm de largo dispuestos en pares.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Castaño-grisácea oscura, gruesa, agrietada de forma profunda y longitudinal con placas rectangulares duras.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores amarillo-verdosas diminutas, dispuestas en densos racimos espiciformes cilíndricos colgantes (aretes). Fruto en legumbre lineal indehiscente arqueada (10-20 cm), amarillo-pálida, de pulpa dulce rica en azúcares.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Prosopis</b>: del griego antiguo, voz confusa asignada por Dioscórides a una planta espinosa perenne. <b>chilensis</b>: descriptor geográfico de Chile.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>huilco</b> o <b>kuri</b>. En lengua quechua se conoce como <b>tacu</b> ('el árbol' por excelencia). El término castellano <b>algarrobo</b> proviene de la voz árabe norteafricana <i>al-jarruba</i>, usada para denominar al algarrobo europeo mediterráneo debido a la semejanza visual de sus vainas alimenticias.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Quebradas profundas, fondos de valles fluviales y llanos semiáridos desde Arica hasta la región de Valparaíso. Excelente bioindicador de aguas subterráneas.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El algarrobo de Chile central posee un sistema de raíces pivotantes verdaderamente asombroso, capaz de taladrar el subsuelo seco y descender más de 20 metros de profundidad en busca de napas freáticas confinadas. Gracias a esta arquitectura hidráulica, sobrevive de manera perenne en valles semiáridos donde no cae lluvia durante años. Sus vainas dulces fueron el pilar alimenticio indispensable para los pueblos prehispánicos Diaguita y Atacameño, quienes las muelen en morteros de piedra para confeccionar el pan de 'patay' y la bebida ceremonial fermentada 'aloja'.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Prosopis%20chilensis" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Prosopis%20chilensis&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Prosopis%20chilensis" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="prosopis-tamarugo" data-buscable="prosopis tamarugo tamarugo fabaceae tarapacá antofagasta arbol mediano espinoso hasta 15 m copa amplia y densa sobrevive en uno de los desiertos mas aridos del planeta nativo endemico de chile el nombre tamarugo no es mapuche proviene probablemente del kunza lengua atacamena hoy extinta quechua o aymara" data-zonas="Norte">
  <header class="ficha-header">
    <div class="ficha-num">N° 37 · <span class="familia-tag">Fabaceae</span></div>
    <h2 class="nombre-cientifico"><em>Prosopis tamarugo</em> <span class="autor">Phil.</span></h2>
    <div class="nombres-comunes">Tamarugo</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. Restringido a la Pampa del Tamarugal en el desierto de Atacama. En peligro.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Prosopis tamarugo">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 72 L 40 48" stroke="#5a4d20" stroke-width="3" stroke-linecap="round"/>
        <path d="M 40 48 Q 25 40 22 28 M 40 48 Q 55 40 58 28" stroke="#5a4d20" stroke-width="1.8" fill="none"/>
        <circle cx="40" cy="26" r="16" fill="#2e6b3f" opacity="0.9"/>
        <circle cx="24" cy="26" r="11" fill="#1f4e2c" opacity="0.85"/>
        <circle cx="56" cy="26" r="11" fill="#1f4e2c" opacity="0.85"/>
        <path d="M 24 72 Q 40 64 56 72 Z" fill="#e8e4d4" stroke="#d4c9a8" stroke-width="0.5"/>
        <path d="M 40 38 Q 44 46 41 52 T 44 58" stroke="#f0d96a" stroke-width="1.8" fill="none" stroke-linecap="round"/>
      </svg>
      <p class="desc-general">Árbol mediano sumamente espinoso (hasta 15 m), de copa esférica muy tupida y densa. Habita en costras de sal pura del desierto absoluto.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes (en presencia de acuíferos constantes), compuestas bipinnadas pequeñas (2-5 cm), folíolos verde-grisáceos diminutos. Ramas tortuosas cubiertas con espinas agudas y delgadas de hasta 3 cm.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-oscura parduzca, gruesa, agrietada de forma profunda e irregular en crestas longitudinales duras que se desprenden.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores amarillas brillantes pequeñas, agrupadas en racimos espiciformes axilares densos. Fruto inconfundible: legumbre corta (3-5 cm) cilíndrica, **fuertemente curvada y retorcida sobre sí misma en espiral**, amarillo-dorada. Pulpa nutritiva.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Prosopis</b>: voz griega clásica (ver algarrobo). <b>tamarugo</b>: epíteto vernáculo tomado directamente del léxico de los pueblos originarios nortinos para designar a este árbol de la Pampa.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>El nombre <b>tamarugo</b> carece de raíz en mapudungun. Proviene muy probablemente del kunza (la lengua extinta del pueblo Atacameño), o de variantes fonéticas del aymara y quechua costero del norte grande.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Estrictamente endémico de la provincia del Tamarugal (Región de Tarapacá). Sobrevive en salares secos y llanos del desierto de Atacama.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El tamarugo realiza un prodigio ecológico mundial: prospera de forma endémica en la Pampa del Tamarugal, una faja desértica donde el promedio de lluvias anuales es inferior a 5 mm (pudiendo no llover en décadas). Capta el agua extendiendo sus raíces pivotantes verticales a través de duras costras salinas (caliche) hasta tocar napas subterráneas de agua salobre a más de 20 metros. Durante el auge de la minería del salitre en el siglo XIX, los bosques nativos de tamarugales fueron talados de forma masiva para alimentar las calderas de vapor de las oficinas salitreras, empobreciendo el ecosistema; la reforestación del siglo XX salvó la especie de la extinción total.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Prosopis%20tamarugo" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Prosopis%20tamarugo&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Prosopis%20tamarugo" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="prumnopitys-andina" data-buscable="prumnopitys andina lleuque uva de la cordillera pino amarillo podocarpaceae biobio la araucania los rios conifera mediana hasta 15 m copa angosta frutos carnosos comestibles lo opuesto a tipicas coniferas nativo endemico de chile y argentina en mapudungun se llama lleuque o lliwke palabras raiz sin descomposicion conocida" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 38 · <span class="familia-tag">Podocarpaceae</span></div>
    <h2 class="nombre-cientifico"><em>Prumnopitys andina</em> <span class="autor">(Poepp. ex Endl.) de Laub.</span></h2>
    <div class="nombres-comunes">Lleuque, Uva de la cordillera, Pino amarillo</div>
    <div class="status-badge status-endemico-region" title="Habita en Chile y un sector adyacente de Argentina. Especie relativamente escasa.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Prumnopitys andina">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 15 48 L 65 35" stroke="#8b6f3a" stroke-width="1.8" fill="none"/>
        <g stroke="#2e6b3f" stroke-width="2" stroke-linecap="round">
          <line x1="22" y1="44" x2="18" y2="36"/>
          <line x1="30" y1="42" x2="26" y2="34"/>
          <line x1="38" y1="40" x2="34" y2="32"/>
          <line x1="46" y1="38" x2="42" y2="30"/>
          <line x1="54" y1="36" x2="50" y2="28"/>
          <line x1="26" y1="49" x2="30" y2="57"/>
          <line x1="34" y1="47" x2="38" y2="55"/>
          <line x1="42" y1="45" x2="46" y2="53"/>
        </g>
        <circle cx="58" cy="46" r="4.5" fill="#f0d96a" stroke="#8b6f3a" stroke-width="0.5"/>
        <path d="M 50 37 Q 54 44 58 46" stroke="#8b6f3a" stroke-width="1" fill="none"/>
      </svg>
      <p class="desc-general">Conífera siempreverde mediana (hasta 15 m), de copa angosta y follaje esbelto. Excepcional por producir frutos carnosos comestibles parecidos a uvas.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, lineales y planas cortas (1-2.5 cm), dispuestas de forma pectinada (dos hileras paralelas en un plano a los lados de la ramilla). Verde oscuro opaco por arriba, azulado por abajo. No punzantes.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Grisácea a pardo-rojiza, lisa y suave en ejemplares jóvenes; agrietada de forma longitudinal irregular en placas rectangulares en la vejez.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta dioica con conos masculinos reunidos en espigas axilares breves. Fruto (semilla modificada) cubierto enteramente por un arilo carnoso globoso o elíptico grande (2 cm), **verde-amarillento, mucilaginoso y dulce**, comestible.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Prumnopitys</b>: del griego <i>proúmnos</i> (ciruelo) + <i>pítys</i> (pino), aludiendo de forma descriptiva a sus semillas carnosas parecidas a ciruelas en una conífera. <b>andina</b>: relativo a su cordillerano hábitat andino.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>lleuque</b> o <b>lliwke</b>. Es un vocablo primario raíz tradicional del pueblo mapuche y de las comunidades cordilleranas del centro-sur.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Especie escasa y discontinua. Habita laderas de la precordillera y cordillera de los Andes desde Linares (Maule) hasta Cautín (Araucanía), sobre suelos volcánicos pedregosos.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El lleuque constituye una hermosa paradoja botánica planetaria: pertenece a las coníferas (el grupo evolutivo de los pinos y alerces), cuyos frutos son conos o piñas secas y leñosas. Sin embargo, para asegurar su dispersión, el lleuque rodeó su semilla de una pulpa carnosa, jugosa y dulce que asemeja a una uva de parra, invitando a las aves y zorros a consumirlo para dispersar sus semillas en el bosque. Los indígenas Pehuenches recolectaban este codiciado fruto en otoño como postre energético y complemento del piñón.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Prumnopitys%20andina" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Prumnopitys%20andina&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Prumnopitys%20andina" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="quillaja-saponaria" data-buscable="quillaja saponaria quillay quillajaceae coquimbo valparaiso metropolitana o higgins maule nuble biobio la araucania arbol siempreverde mediano hasta 20 m copa redondeada y densa emblematico del bosque esclerofilo nativo no endemico de chile en mapudungun se llama cullay kullay o quillay palabra raiz que paso directo al nombre cientifico" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 39 · <span class="familia-tag">Quillajaceae</span></div>
    <h2 class="nombre-cientifico"><em>Quillaja saponaria</em> <span class="autor">Molina</span></h2>
    <div class="nombres-comunes">Quillay</div>
    <div class="status-badge status-nativo" title="Habita en Chile y Argentina (extremo oeste).">Nativo (no endémico de Chile)</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Quillaja saponaria">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <g transform="translate(40,40)">
          <path d="M 0 0 L -4 -16 L 4 -16 Z" fill="white" stroke="#6b6b6b" stroke-width="0.8"/>
          <path d="M 0 0 L 15 -7 L 11 -14 Z" fill="white" stroke="#6b6b6b" stroke-width="0.8"/>
          <path d="M 0 0 L 10 13 L 16 7 Z" fill="white" stroke="#6b6b6b" stroke-width="0.8"/>
          <path d="M 0 0 L -10 13 L -16 7 Z" fill="white" stroke="#6b6b6b" stroke-width="0.8"/>
          <path d="M 0 0 L -15 -7 L -11 -14 Z" fill="white" stroke="#6b6b6b" stroke-width="0.8"/>
          <circle cx="0" cy="0" r="5" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="0.5"/>
          <circle cx="-2" cy="-10" r="1.2" fill="#f0d96a"/><circle cx="9" cy="-7" r="1.2" fill="#f0d96a"/>
          <circle cx="7" cy="6" r="1.2" fill="#f0d96a"/><circle cx="-7" cy="6" r="1.2" fill="#f0d96a"/>
        </g>
        <path d="M 12 20 Q 20 12 25 22 Z" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol siempreverde mediano (hasta 20 m), copa redondeada densa y frondosa. Especie emblemática del bosque esclerófilo.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovado-elípticas (2-5 cm), duras (coriáceas), de color verde oscuro brillante, con bordes provistos de dientes espaciados y glandulares sutiles.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, gruesa, agrietada longitudinalmente en profundas placas cuadradas. **Rica en saponinas naturales de alta capacidad espumosa** e industrial.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Flores blanco-cremosas estrelladas de 5 pétalos y gran disco central verdoso nectarífero. Fruto leñoso inconfundible: cápsula de dehiscencia estrellada en 5 brazos, que asemeja una estrella de mar rígida al abrirse en otoño. Semillas aladas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Quillaja</b>: latinización del vocablo mapuche tradicional <i>cüllay</i>. <b>saponaria</b>: del latín <i>sapo, saponis</i> (jabón), otorgado por la gran cantidad de glucósidos saponínicos de su corteza que generan abundante espuma detergente al contacto con agua.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>cüllay</b>, <b>küllay</b> o <b>quillay</b>. La raíz original denota la acción de limpiar o lavar, debido al uso ancestral de su madera e infusión para la higiene textil y corporal.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Exponente dominante del bosque esclerófilo de Chile central. Abunda en laderas de exposición norte (solanas), cerros e islas de valles desde Coquimbo hasta la Araucanía.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Las saponinas purificadas extraídas de la corteza del quillay chileno constituyen uno de los ingredientes biológicos secretos más valiosos del planeta: actúan como un adyuvante inmunológico de alta fidelidad indispensable para la elaboración de vacunas humanas de última generación (como la fórmula Novavax contra el COVID-19 y vacunas contra la malaria). Este compuesto purificado potencia exponencialmente la respuesta del sistema inmune humano. Los antiguos Mapuches ya aprovechaban esta sofisticada química natural hace siglos: machacaban trozos de corteza de küllay para lavar los ponchos de lana cruda y como champú capilar medicinal, manteniendo el cabello fuerte y libre de caspa.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Quillaja%20saponaria" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Quillaja%20saponaria&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Quillaja%20saponaria" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="saxegothaea-conspicua" data-buscable="saxegothaea conspicua manio de hojas cortas manio hembra maniu podocarpaceae biobio la araucania los rios los lagos aysen conifera primitiva mediana hasta 20 m unico miembro del genero fosil viviente nativo endemico de chile y argentina en mapudungun se llama manio o maniu palabra raiz aplicada a varias coniferas similares" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 40 · <span class="familia-tag">Podocarpaceae</span></div>
    <h2 class="nombre-cientifico"><em>Saxegothaea conspicua</em> <span class="autor">Lindl.</span></h2>
    <div class="nombres-comunes">Mañío de hojas cortas, Mañío hembra, Maniú</div>
    <div class="status-badge status-endemico-region" title="Habita el bosque valdiviano de Chile y zonas adyacentes de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Saxegothaea conspicua">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <g transform="translate(40,42)">
          <circle cx="0" cy="0" r="14" fill="#2e6b3f" stroke="#1f4e2c" stroke-width="1"/>
          <path d="M -10 -8 L 0 -18 L 10 -8" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="0.8"/>
          <path d="M -14 2 L -22 -6 L -10 -8" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="0.8"/>
          <path d="M 10 -8 L 22 -6 L 14 2" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="0.8"/>
          <path d="M -12 6 L 0 16 L 12 6" fill="#4a8e5e" stroke="#1f4e2c" stroke-width="0.8"/>
          <circle cx="0" cy="0" r="4" fill="#8b6f3a"/>
        </g>
        <path d="M 12 60 Q 24 55 32 62" stroke="#1f4e2c" stroke-width="1.8" fill="none"/>
      </svg>
      <p class="desc-general">Conífera siempreverde mediana (hasta 20 m), de copa densa y cónica. Constituye un género monotípico considerado un fósil viviente del bosque austral.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, lineales-lanceoladas cortas (1-2 cm), dispuestas de forma espiralada densa pero retorcidas basalmente para simular dos hileras opuestas. No punzantes. Dos líneas blancas nítidas en el envés.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-rojiza oscura, delgada, desprendible en placas o escamas rectangulares pequeñas e irregulares en fustes adultos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Planta monoica (rasgo evolutivo único en su grupo). Conos masculinos pequeños axilares; conos femeninos ovoides carnosos esféricos pequeños (1 cm) formados por escamas coalescentes espinescentes verde-azuladas que encierran semillas asimétricas.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Saxegothaea</b>: género erigido por John Lindley en homenaje formal al Príncipe Alberto de Sajonia-Coburgo-Gotha (<i>Saxe-Coburg-Gotha</i>), príncipe consorte de la Reina Victoria del Reino Unido. <b>conspicua</b>: del latín, 'notable, conspicua, visible'.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama de forma genérica <b>mañío</b> o <b>mañiu</b>, compartiendo la voz raíz con los parientes del género Podocarpus debido a la similitud estructural de sus maderas y agujas foliares.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Áreas sombrías profundas, microclimas húmedos de ambas cordilleras desde el Biobío hasta los fiordos isleños de Aisén. Asociado a bosques puros de Nothofagus.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Saxegothaea constituye un linaje monotípico relicto absoluto: existe una sola especie de este género en todo el planeta, y se refugia de manera exclusiva en los densos y lluviosos bosques templados chilenos. Se cataloga científicamente como un verdadero 'fósil viviente' debido a que la anatomía íntima de sus conos femeninos conserva estructuras primitivas de articulación leñosa que desaparecieron en el resto de las coníferas modernas hace más de 100 millones de años, durante el período Cretácico.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Saxegothaea%20conspicua" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Saxegothaea%20conspicua&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Saxegothaea%20conspicua" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="schinus-latifolius" data-buscable="schinus latifolius molle huingan de hojas anchas anacardiaceae coquimbo valparaiso metropolitana o higgins maule nuble biobio arbol o arbusto siempreverde 4 10 m copa amplia y densa resinoso aromatico nativo endemico de chile el nombre molle proviene del quechua mulli no del mapudungun esto refleja la influencia del imperio inca en chile central en mapudungun original se le decia huingan" data-zonas="Norte,Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 41 · <span class="familia-tag">Anacardiaceae</span></div>
    <h2 class="nombre-cientifico"><em>Schinus latifolius</em> <span class="autor">(Gillies ex Lindl.) Engl.</span></h2>
    <div class="nombres-comunes">Molle, Huingán de hojas anchas</div>
    <div class="status-badge status-endemico-chile" title="Exclusivo de Chile. Especie del bosque esclerófilo central.">Nativo · Endémico de Chile</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Schinus latifolius">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 18 52 C 20 28, 44 24, 60 28 C 50 50, 35 58, 18 52" fill="#4a8e5e" stroke="#2e6b3f" stroke-width="1.5"/>
        <path d="M 18 52 Q 38 40 60 28" stroke="#2e6b3f" stroke-width="1" fill="none"/>
        <circle cx="24" cy="58" r="2.5" fill="#8b5a8b" stroke="#4a1a4a" stroke-width="0.5"/>
        <circle cx="29" cy="56" r="2" fill="#8b5a8b" stroke="#4a1a4a" stroke-width="0.5"/>
        <circle cx="27" cy="62" r="2.2" fill="#8b5a8b" stroke="#4a1a4a" stroke-width="0.5"/>
      </svg>
      <p class="desc-general">Árbol o arbusto siempreverde (4-10 m), de copa globosa, amplia y muy sombreada. Notoriamente resinoso y aromático.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, alternas, ovadas u ovado-oblongas, notablemente **anchas para su género** (3-7 cm de largo), duras y de bordes ondulados o ligeramente aserrados. Liberan intenso olor resinoso dulce al estrujarse.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca, agrietada longitudinalmente en cordones fibrosas firmes. Exuda resinas gomosas aromáticas al sufrir heridas.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, unisexuales (planta dioica), blanco-amarillentas, reunidas en densas panículas axilares y compactas. Fruto en drupa globosa pequeña (5-7 mm), de color rojo-violáceo o purpúreo oscuro al madurar en otoño.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Schinus</b>: tomado del nombre griego antiguo <i>schînos</i> asignado al árbol del lentisco mediterráneo, debido a la gran semejanza y aroma de las resinas gomosas que exudan ambos árboles. <b>latifolius</b>: del latín, compuesto por <i>latus</i> (ancho) + <i>folium</i> (hoja), denotando el ancho de sus láminas foliares.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>El nombre popular **molle** no es mapuche; constituye una adaptación de la voz quechua andina <i>mulli</i> introducida a Chile central durante la expansión histórica del Imperio Inca. En mapudungun original precolombino se le denomina **huingán**.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Estrictamente endémico de Chile. Laderas asoleadas, llanos semiáridos y quebradas secas del bosque esclerófilo mediterráneo desde Coquimbo hasta la provincia de Concepción.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>El molle de hojas anchas es primo directo del célebre pimiento ornamental (<i>Schinus molle</i>) cultivado en las plazas urbanas. Sus drupas purpúreas otoñales poseen una cutícula resinosa y dulce que los antiguos pueblos andinos prehispánicos recolectaban minuciosamente; tras lavarlas para remover la resina amarga, fermentaban los azúcares de la pulpa para confeccionar la tradicional 'chicha de molle', una bebida alcohólica ceremonial de gran valor ritual en el área andina.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Schinus%20latifolius" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Schinus%20latifolius&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Schinus%20latifolius" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="tepualia-stipularis" data-buscable="tepualia stipularis tepu tepa myrtaceae biobio la araucania los rios los lagos aysen magallanes arbol o arbusto siempreverde 3 15 m tronco retorcido forma tepuales impenetrables nativo endemico de chile y argentina en mapudungun se llama tepu o tepu palabra raiz que paso directamente al nombre cientifico de ahi tambien proviene la palabra tepual bosque de tepu que se usa para describir los matorrales densos casi impenetrables formados por esta especie" data-zonas="Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 42 · <span class="familia-tag">Myrtaceae</span></div>
    <h2 class="nombre-cientifico"><em>Tepualia stipularis</em> <span class="autor">(Hook. &amp; Arn.) Griseb.</span></h2>
    <div class="nombres-comunes">Tepú, Tepa</div>
    <div class="status-badge status-endemico-region" title="Habita en el sur de Chile y un sector adyacente de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Tepualia stipularis">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <g stroke="#5a4d20" stroke-width="3" stroke-linecap="round" fill="none">
          <path d="M 15 72 Q 32 50 20 30 T 45 14"/>
          <path d="M 65 72 Q 45 54 58 35 T 32 16"/>
          <path d="M 25 50 L 55 45"/> </g>
        <circle cx="45" cy="14" r="3" fill="#1f4e2c"/>
        <circle cx="32" cy="16" r="2.5" fill="#2e6b3f"/>
        <circle cx="20" cy="30" r="3" fill="#1f4e2c"/>
      </svg>
      <p class="desc-general">Árbol o arbusto siempreverde (3-15 m), cuyos troncos durísimos crecen de forma extraordinariamente intrincada, retorcida y horizontal. Da origen a los espesos 'tepuales'.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, simples, opuestas, elíptico-ovadas y notablemente **pequeñas** (1-2 cm de largo), duras, enteras, verde oscuro brillante. Provistas de estípulas lineares muy notorias en el nudo (de ahí <i>stipularis</i>). Aroma mirtáceo resinoso al estrujarse.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Pardo-rojiza oscura, delgada, desprendible en placas longitudinales delgadas. Madera de color rojo púrpura, de una dureza y densidad mineral extrema.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Blancas, pequeñas, solitarias o agrupadas en las axilas, caracterizadas por lucir un denso penacho central de numerosos estambres salientes largos. Fruto en cápsula leñosa pequeña coronada por los restos del cáliz.</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Tepualia</b>: latinización directa tomada del vocablo mapuche primario <i>tepú</i>. <b>stipularis</b>: del latín <i>stipula</i> (estípula), asignado debido a la inusual presencia de escamas estipulares muy visibles e identificables en la inserción de los pecíolos.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se llama <b>tepú</b> o <b>tepu</b>. De esta voz nativa se acuñó el término geográfico y ecológico chileno **tepual**, usado para definir a las indomables asociaciones boscosas anegadas dominadas por esta especie en los archipiélagos del sur.</p>
  </div>
  
  <div class="bloque cambio-color-dist distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Terrenos pantanosos, suelos saturados de agua, turberas y márgenes fluviales anegados desde la provincia de Arauco hasta Magallanes. Alcanza su máximo desarrollo en la Isla Grande de Chiloé.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Los <b>tepuales</b> constituyen uno de los ecosistemas más hostiles e impenetrables del mundo: los troncos de los tepúes no crecen rectos, sino que se doblan, se arrastran horizontalmente y se trenzan entre sí a pocos centímetros del agua estancada, formando un andamiaje leñoso laberíntico. Caminar por un tepual exige avanzar haciendo equilibrio sobre estos troncos resbaladizos cubiertos de musgo, ya que dar un paso en falso significa hundirse en el lodo ácido del pantano subterráneo. De ahí nace el dicho chilote 'meterse en un tepual', equivalente a involucrarse en un problema enredado y confuso. Su madera purpúrea es tan densa que no flota en el agua y posee un poder calorífico tan alto que quema intensamente incluso estando recién cortada y empapada de lluvia.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Tepualia%20stipularis" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Tepualia%20stipularis&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Tepualia%20stipularis" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>

<article class="ficha" id="weinmannia-trichosperma" data-buscable="weinmannia trichosperma tineo palo santo maden cunoniaceae maule nuble biobio la araucania los rios los lagos aysen arbol siempreverde grande hasta 30 m tronco recto especie melifera muy apreciada nativo endemico de chile y argentina en mapudungun se llama tineo maden o palo santo son palabras raiz sin descomposicion clara" data-zonas="Centro,Sur">
  <header class="ficha-header">
    <div class="ficha-num">N° 43 · <span class="familia-tag">Cunoniaceae</span></div>
    <h2 class="nombre-cientifico"><em>Weinmannia trichosperma</em> <span class="autor">Cav.</span></h2>
    <div class="nombres-comunes">Tineo, Palo santo, Maden</div>
    <div class="status-badge status-endemico-region" title="Habita el bosque valdiviano de Chile y un sector adyacente de Argentina.">Nativo · Endémico de Chile y Argentina</div>
  </header>
  
  <div class="bloque">
    <div class="bloque-titulo">🌿 Descripción</div>
    <div class="desc-flex-container">
      <svg class="ilustracion-botanica" width="75" height="75" viewBox="0 0 80 80" xmlns="http://www.w3.org/2000/svg" aria-label="Ilustración de Weinmannia trichosperma">
        <circle cx="40" cy="40" r="38" fill="#fdfbf4"/>
        <path d="M 40 72 L 40 14" stroke="#8b6f3a" stroke-width="2" stroke-linecap="round" fill="none"/>
        <path d="M 40 55 L 34 48 L 40 41 L 46 48 Z" fill="#4a8e5e" opacity="0.8"/>
        <path d="M 40 41 L 35 34 L 40 27 L 45 34 Z" fill="#4a8e5e" opacity="0.8"/>
        <path d="M 40 27 L 36 21 L 40 15 L 44 21 Z" fill="#4a8e5e"/>
        <path d="M 34 48 L 22 48 M 46 48 L 58 48" stroke="#1f4e2c" stroke-width="1.8" stroke-linecap="round"/>
        <path d="M 35 34 L 24 32 M 45 34 L 56 32" stroke="#1f4e2c" stroke-width="1.8" stroke-linecap="round"/>
      </svg>
      <p class="desc-general">Árbol siempreverde grande (hasta 30 m), de fuste recto, cilíndrico y esbelto. Especie melífera de extraordinario valor para la apicultura del sur.</p>
    </div>
    <div class="desc-items">
      <div class="desc-item"><span class="desc-label">Hojas:</span> Perennes, compuestas imparipinnadas medianas (5-10 cm total), con 7-15 pares de folíolos sésiles aserrados de color verde brillante. **Raquis inconfundible provisto de alas membranosas ensanchadas en forma de rombo** entre cada par de folíolos.</div>
      <div class="desc-item"><span class="desc-label">Corteza:</span> Gris-parduzca oscura, rugosa, agrietada longitudinalmente en profundos cordones ásperos en árboles adultos. Madera densa de tonos rojizos oscuros muy decorativos.</div>
      <div class="desc-item"><span class="desc-label">Flores/Frutos:</span> Pequeñas, blanco-amarillentas, agrupadas en densos racimos cilíndricos terminales erectos y vistosos (aretes). Florecen a principios de verano. Fruto en cápsula pequeña coriácea marrón-rojiza que libera semillas provistas de apéndices pelosos (de ahí <i>trichosperma</i>).</div>
    </div>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">📖 Etimología científica</div>
    <p><b>Weinmannia</b>: género dedicado a Johann Wilhelm Weinmann, célebre farmacéutico y botánico alemán del siglo XVIII, director de una de las primeras obras ilustradas a color de la flora europea. <b>trichosperma</b>: del griego <i>thríx, trichós</i> (pelo) + <i>spérma</i> (semilla), haciendo alusión directa a sus características semillas pilosas dispersadas por el viento.</p>
  </div>
  
  <div class="bloque">
    <div class="bloque-titulo">🪶 Nombre en mapudungun</div>
    <p>En mapudungun se conoce bajo los nombres tradicionales de <b>tineo</b> o <b>maden</b>. La denominación rural campesina de *palo santo* obedece a la gran resistencia e incorruptibilidad que muestra su madera expuesta a la intemperie en estructuras pesadas.</p>
  </div>
  
  <div class="bloque distribucion">
    <div class="bloque-titulo">📍 Dónde encontrarlo</div>
    <p>Bosques siempreverdes lluviosos de la cordillera de la Costa y faldas andinas bajas desde la provincia de Cauquenes (Maule) hasta los canales australes de la región de Aisén.</p>
  </div>
  
  <div class="bloque curiosidad">
    <div class="bloque-titulo">💡 Dato curioso</div>
    <p>Las hojas compuestas del tineo presentan un diseño anatómico único en el bosque chileno: el raquis central está provisto de pequeñas expansiones de tejido verde en forma de diamantes o rombos perfectos alineados entre cada folíolo, funcionando como una huella dactilar botánica infalible para reconocerlo en terreno. Al igual que el ulmo, es un árbol de altísima reputación apícola; las abejas producen a partir de su néctar la cotizada 'miel de tineo', un producto monofloral nativo oscuro, denso y de un sabor silvestre complejo con notas que recuerdan a maderas tostadas y resinas de montaña.</p>
  </div>
  
  <div class="bloque-fotos">
    <span class="fotos-label">📷 Ver fotos:</span>
    <a href="https://www.inaturalist.org/search?q=Weinmannia%20trichosperma" target="_blank" rel="noopener">iNaturalist</a>
    <a href="https://www.google.com/search?q=Weinmannia%20trichosperma&tbm=isch" target="_blank" rel="noopener">Google</a>
    <a href="https://es.wikipedia.org/wiki/Weinmannia%20trichosperma" target="_blank" rel="noopener">Wikipedia</a>
  </div>
</article>
