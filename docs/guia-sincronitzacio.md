# Guia de Sincronització al PC de Sobretaula (Empatik)

Aquest document resumeix els passos exactes per sincronitzar el rebateig d'**Ikonikus** a **Empatik** al teu PC de sobretaula sense trencar la sincronització d'AGY Sync.

---

## Estat previ (ja completat al portàtil i al núvol)
- El repositori privat a GitHub ja s'ha reanomenat a: **`elCordones/empatik`**.
- La nova adreça oficial és: `https://github.com/elCordones/empatik.git`.
- El mapa canònic d'AGY Sync (`projects-map.json`) ja està actualitzat al núvol amb el nom canònic `JOC - Empatik`.

---

## Procediment al PC de Sobretaula

Tens dues maneres de fer-ho: l'**Automàtica** (aprofitant el teu script de sincronització) o la **Manual**.

### Mètode A · Automàtic via AGY Sync (Recomanat)

El teu script `agy-sync.ps1` està programat per auto-reconciliar i rebatejar carpetes si detecta que el remote coincideix amb el mapa.

1. **Tanca Antigravity / VS Code** al sobretaula (perquè cap procés tingui fitxers bloquejats).
2. Obre una finestra de **PowerShell** dins de la carpeta del projecte:
   ```powershell
   cd "$HOME\Desktop\ANTIGRAVITY\JOC - Ikonikus"
   ```
3. Actualitza la URL remota del repositori cap a Empatik:
   ```powershell
   git remote set-url origin https://github.com/elCordones/empatik.git
   ```
4. Ves a l'Escriptori del sobretaula i fes doble clic a:
   **`Sincronitzar AGY.bat`**

   *Què passarà?*
   - L'script descarregarà la darrera versió de `projects-map.json`.
   - Veurà que la carpeta té el remote d'Empatik.
   - Mostrarà el missatge: `[~] Unificant nom de carpeta: 'JOC - Ikonikus' -> 'JOC - Empatik'`.
   - Reanomenarà la carpeta automàticament i en farà el `git pull`.

---

### Mètode B · Manual (Alternatiu)

Si prefereixes controlar el canvi de nom tu mateix:

1. **Tanca Antigravity / VS Code**.
2. A l'Explorador de fitxers de Windows (`Desktop\ANTIGRAVITY`), canvia el nom de la carpeta:
   - De: `JOC - Ikonikus`
   - A: `JOC - Empatik`
3. Obre PowerShell a la nova carpeta:
   ```powershell
   cd "$HOME\Desktop\ANTIGRAVITY\JOC - Empatik"
   git remote set-url origin https://github.com/elCordones/empatik.git
   git pull
   ```
4. Fes doble clic a **`Sincronitzar AGY.bat`** a l'Escriptori per confirmar que tot queda verd i al dia.

---

## Verificació Final
Per comprovar que tot ha quedat perfecte, dins de `JOC - Empatik` pots executar:
```powershell
git remote -v
git status
```
Hauràs de veure la nova URL (`https://github.com/elCordones/empatik.git`) i l'arbre net (`nothing to commit, working tree clean`).
