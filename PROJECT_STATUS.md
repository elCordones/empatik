# Empatik - Estat i Documentació

## 1. Descripció i Especificacions del Projecte
- **Objectiu principal**: Aplicació educativa web independent (**Empatik**) per treballar l'educació socioemocional, l'empatia i l'expressió oral a l'aula mitjançant metàfores visuals (inspirada en les dinàmiques associatives de jocs de taula com *Ikonikus* o *Dixit*, amb iconografia Unicode i continguts propis), amb doble modalitat d'ús: **Mode Grups (Pass & Play)** (modalitat competitiva i cooperativa d'equip) i **Mode Assemblea / Pissarra Digital** per a tutories amb tot el grup-classe.
- **Públic destinatari / Usuaris**: Docents i alumnat d'Educació Primària i Secundària.
- **Stack tecnològic**: HTML5 semàntic (`<dialog>` natiu, `<input type="radio">`), CSS3 (variables semàntiques, `:has(:checked)`, `prefers-reduced-motion`, estils d'impressió `@media print`, mode d'alta visibilitat per a pissarra digital) i JavaScript Vanilla (View Transitions API, Fullscreen API, persistència completa en `localStorage`).
- **Arquitectura i fitxers clau**:
  - `index.html` i `Index.html.txt`: Aplicació web completa autocontinguda (**Empatik**, monograma `EM`, 60 cartes base + creador de cartes de l'alumnat en `localStorage` sota claus `empatik_*_v1` amb migració automàtica des d'`ikonikus_*_v1`, 4 àmbits temàtics sense repeticions + banc docent, mode Assemblea amb protagonistes i vots `-1 / +1`, mode Grups competitiu/cooperatiu, temporitzador opcional de debat, bastida de vocabulari emocional i bateig de metàfores, autodesat de sessió, Diari d'Empatia persistent/imprimible/exportable i peu de pàgina de llicenciament AGPL v3 / CC BY-SA 4.0).
  - `index.backup.html`: Còpia de seguretat íntegra de la versió anterior prèvia a l'auditoria i modernització del 2026-11-16.

## 2. Estat Actual i Punt de Control (Darrera sessió: 2026-11-17)
- **Estat general**: Funcional, rebatejat a **Empatik** (sense conflictes de marca comercial) i completat amb totes les millores dels Blocs A (Robustesa Tecnopedagògica), B (Noves Funcionalitats) i C (Modernització Frontend i Bugfixes). Carpeta arrel local actualitzada oficialment a `JOC - Empatik`.
- **Funcionalitats completades**:
  - [x] Còpia de seguretat del codi original desada a `index.backup.html`.
  - [x] Rebateig complet a **Empatik** (`EM`), desvinculació i nota d'inspiració pedagògica dins `#rules-modal`, i migració transparent de claus `localStorage` (`empatik_*_v1` amb *fallback* des d'`ikonikus_*_v1`).
  - [x] **Bloc A · Robustesa Tecnopedagògica i Dinàmica d'Aula**:
    - [x] Autodesat de sessió activa (`empatik_active_session_v1`) i Diari d'Empatia persistent (`empatik_diary_history_v1`) a `localStorage`, amb bàner de recuperació (`Reprendre sessió`) i botó `Buida el Diari` amb confirmació en dos clics.
    - [x] Píndoles clicables de vocabulari emocional (16 matisos DUA) a la Fase 3 i bateig lliure de metàfora (`#custom-metaphor-input`) quan s'activa el mode «Només símbols» (sense revelar etiquetes als `aria-label`).
    - [x] Millores al Mode Assemblea: camp opcional per al nom del Protagonista/Narrador de la ronda i botons de control de vots (`−` / `+`).
    - [x] Generador de situacions sense repeticions dins de cada àmbit (`state.usedPrompts`) i modalitats **Cooperatives d'equip** (`1 volta` i `2 voltes`) al Mode Grups.
  - [x] **Bloc B · Noves Funcionalitats Pedagògiques**:
    - [x] Temporitzador visual opcional de debat (`60s / 90s / 2m`, pausa i reinici) amb barra de progrés suau a les fases de debat d'Assemblea i de reflexió.
    - [x] Creador de cartes personalitzades de l'alumnat (`#custom-cards-modal`, `empatik_custom_cards_v1`) amb selector ràpid d'emojis i integració automàtica a la baralla.
  - [x] **Bloc C · Modernització Frontend (Baseline 1.0, WCAG 2.1 AA i Bugfixes)**:
    - [x] Migració de tots els 6 modals a `<dialog>` HTML5 natiu amb `.showModal()`, `::backdrop`, `closedby="any"` / `closedby="none"` + fallback JS i full d'impressió multipàgina dedicat (`#diary-print-sheet`).
    - [x] Selector de modalitat amb `<input type="radio">` natius i `:has(:checked)` / `:has(:focus-visible)`.
    - [x] Regions `aria-live="polite"` acotades a `#question-area` i `#controls` (amb `aria-live="off"` al rellotge del temporitzador).
    - [x] `View Transitions API` (`runTransition`) respectant `@media (prefers-reduced-motion: reduce)`.
    - [x] Disseny d'alta visibilitat en Mode Assemblea (`148×198px`) + botó de Pantalla Completa (`Fullscreen API`).
    - [x] Correcció dels bugs de baralla duplicada a `dealAssemblyBoardCards()`, reaparició de cartes descartades al *mulligan* (`drawCard` amb `excludedIds`), i typo `active-chooser`.
  - [x] **Infraestructura, Publicació i Sincronització AGY Sync**:
    - [x] Repositori a GitHub reanomenat de forma neta a `elCordones/empatik` i canviat a visibilitat Pública.
    - [x] Desplegament web oficial via **GitHub Pages** actiu a: `https://elcordones.github.io/empatik/`.
    - [x] Nou favicon SVG vectorial propi (`favicon.svg`) creat i enllaçat amb fallback inline i `apple-touch-icon`.
    - [x] Metaetiquetes Open Graph, Twitter Cards, SEO i previsualització afegides a `index.html` i `Index.html.txt`.
    - [x] Documentació de projecte oberta `README.md` amb insígnies, explicació pedagògica, DUA i guia docent d'ús.
    - [x] Fitxer `.gitignore` per a la neteja de fitxers temporals.
    - [x] Remote `origin` actualitzat a `https://github.com/elCordones/empatik.git`.
    - [x] Mapa de projectes `projects-map.json` a `agy-workspace-config` actualitzat a `"https://github.com/elCordones/empatik.git": "JOC - Empatik"` i sincronitzat amb GitHub.
    - [x] Carpeta local reanomenada amb èxit a `JOC - Empatik`.
- **Punt exacte on ens hem quedat**:
  - Web pública viva a `https://elcordones.github.io/empatik/`.
  - Repositori ordenat, documentat i enriquit amb favicon i metadades socials.
  - Al PC de sobretaula, quan hi accedeixis, seguir [GUIA_SOBRETAULA_EMPATIK.md](file:///C:/Users/dcordone/Desktop/ANTIGRAVITY/JOC - Empatik/GUIA_SOBRETAULA_EMPATIK.md) per fer el sync.
  - Opcional: actualitzar el codi incrustat a Google Sites amb el contingut d'`Index.html.txt`.

## 3. Full de Ruta d'Implementació (Roadmap / Propers Passos)
- **Tasques immediates**:
  - [x] Reanomenar la carpeta arrel local en aquest ordinador de `JOC - Ikonikus` a `JOC - Empatik`.
  - [x] Publicar i desplegar l'aplicació web a GitHub Pages (`https://elcordones.github.io/empatik/`).
  - [x] Crear el favicon SVG oficial i documentar el `README.md` per a docents.
  - [ ] Al PC de sobretaula (quan hi accedeixis): executar `Sincronitzar AGY.bat` o actualitzar el remote d'`origin` segons la [GUIA_SOBRETAULA_EMPATIK.md](file:///C:/Users/dcordone/Desktop/ANTIGRAVITY/JOC - Empatik/GUIA_SOBRETAULA_EMPATIK.md).
  - [ ] Substituir el codi HTML incrustat a Google Sites pel contingut d'`index.html` / `Index.html.txt` (o enllaçar directament la URL de GitHub Pages).
- **Millores futures i backlog opcional**:
  - [ ] **Estudi i viabilitat del Mode Multidispositiu (auditat el 2026-11-17)**:
    - Model recomanat: Arquitectura mestre-comandament (tipus Kahoot/Jackbox), amb Pissarra Digital com a tauler i dispositius de l'alumnat només com a comandament per votar o triar carta secreta.
    - Infraestructura tècnica: WebSockets efímers en memòria (sense base de dades) per garantir compatibilitat amb xarxes escolars (que sovint bloquegen WebRTC P2P directe per AP Isolation).
    - Privacitat: Compliment estricte del RGPD escolar, sales efímeres sense emmagatzemar dades personals, registres ni IPs.
  - [ ] Exportació/importació de paquets de cartes i situacions docents en format `.json` per compartir entre docents del mateix centre.
  - [ ] Proves interactives en navegador real (Desktop, tauleta i lector de pantalla) amb sessió d'aula pilot.
