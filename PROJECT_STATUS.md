# Ikonikus Digital - Estat i Documentació

## 1. Descripció i Especificacions del Projecte
- **Objectiu principal**: Aplicació educativa web per treballar l'educació socioemocional, l'empatia i l'expressió oral a l'aula basada en el joc de taula **Ikonikus**, amb doble modalitat d'ús: **Mode Grups (Pass & Play)** per a tauletes/equips cooperatius i **Mode Assemblea / Pissarra Digital** per a tutories amb tot el grup-classe.
- **Públic destinatari / Usuaris**: Docents i alumnat d'Educació Primària i Secundària.
- **Stack tecnològic**: HTML5, CSS3 (variables semàntiques, disseny *responsive*, estils d'impressió `@media print`, accessibilitat WCAG 2.1 AA) i JavaScript Vanilla amb persistència local (`localStorage`).
- **Arquitectura i fitxers clau**:
  - `Index.html.txt` i `index.html`: Aplicació web completa autocontinguda (60 cartes simbòliques, 4 àmbits temàtics + banc docent en `localStorage`, mode Assemblea i Pass & Play, Diari d'Empatia imprimible/exportable, favicon SVG minimalista i peu de pàgina de llicenciament AGPL v3 / CC BY-SA 4.0).

## 2. Estat Actual i Punt de Control (Darrera sessió: 2026-10-25)
- **Estat general**: Funcional, completat amb les 5 millores tecnopedagògiques avançades.
- **Funcionalitats completades**:
  - [x] Auditoria tecnopedagògica i correcció d'anonimat i barreja de cartes jugades (`shuffle`).
  - [x] Baralla de 60 cartes úniques amb commutador **«🏷️ Cartes: Amb text» vs «🎭 Cartes: Només símbols»** (metàfora visual pura).
  - [x] **Botó de canviar les 5 cartes de la mà** (1 cop per partida i jugador) en el mode per torns.
  - [x] **Selector d'Àmbits Temàtics de Tutoria** (`THEMATIC_PROMPTS`): *Inici de curs i coneixença*, *Convivència i conflictes*, *Estrès i reptes escolars*, *Imaginació i dilemes ètics* i *Situacions del docent*.
  - [x] **Mode Assemblea / Pissarra Digital** (Gran Grup): projecció directa de 6 cartes obertes sense pantalles d'ocultació, amb comptador de vots a mà alçada (`+1 vot`) i botó per generar 6 cartes noves.
  - [x] **Banc de Situacions del Docent** persistent a `localStorage` (`ikonikus_custom_prompts_v1`) amb gestor modal per afegir i eliminar preguntes pròpies de l'aula.
  - [x] **Diari d'Empatia** (`#diary-modal`): registre d'historial de totes les rondes amb camp opcional per anotar la reflexió d'aula, impressió directa a PDF (`window.print()`) i descàrrega en fitxer `.txt`.
  - [x] Instruccions ràpides + Modal d'Instruccions i Guia Docent + Favicon SVG i peu de pàgina de llicenciament resumit (David Cordones · 2026).
- **Punt exacte on ens hem quedat**:
  - Tant `Index.html.txt` com `index.html` tenen totes les propostes 1, 2, 3, 4 i 5 integrades i sincronitzades.

## 3. Full de Ruta d'Implementació (Roadmap / Propers Passos)
- **Millores futures i backlog opcional**:
  - [ ] Temporitzador opcional de debat per a dinàmiques àgils a Secundària.
  - [ ] Creador de cartes personalitzades amb emojis triats pels mateixos alumnes.
