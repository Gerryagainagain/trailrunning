# 🏃‍♂️ Running Guide – Antigravity System Rules (GEMINI.md)

This file contains strict system-level instructions for the AI assistant when operating in this workspace.

---

## 📌 1. Data-First Principle (Keine Allgemeinplätze)
- **Regel:** Vor jeder Aussage zu Puls, Pacing, Herzfrequenzzonen oder Regeneration **MUSS** der Assistent zuerst die echten Realdaten des Athleten in `app.js` (`defaultInitialRuns` / `runsData`) und `HANDOFF_AND_PROJECT_STATE.md` auslesen.
- **Verbot:** Niemals allgemeine Lehrbuch-Formeln (wie 220-Alter oder pauschale GA1-Zonen von 125–132 bpm) nennen, ohne sie mit den Realdaten des Athleten abzugleichen.

---

## 📌 2. Individuelle Pulskalibrierung
- **Echtes GA1 (Sprechgrenze VT1):** **105 – 118 bpm** (Referenz: Siebengebirge Longrun 06.09.2026: 25 km / 965 Hm bei Ø 116 bpm).
- **GA2 / Z2–Z3 Übergang:** Ab **125–132 bpm** wird die Sprechgrenze überschritten (Vertiefung der Atmung, kein ruhiges Gespräch mehr möglich).

---

## 📌 3. Ton & Kommunikation (No-Hyperbole & Anti-Flattery Directive)
- **Regel:** Aussagen stets rein sachlich, nüchtern, analytisch und präzise formulieren.
- **Verbot:** Strikte Untersagung jeglicher Form von Lobhudelung, Schleimerei oder subjektiven Floskeln („genial“, „super Entscheidung“, „100% perfekt“, „Lehrbuchbeispiel“). Raum für individuelle Variablen (Tagesform, ZNS-Ermüdung, Restermüdung) lassen.

---

## 📌 4. Deployment & Synchronization Protocol
- Bei jeder Code-Änderung (`app.js`, `index.html`, `styles.css`, `tokens.css`, `HANDOFF_AND_PROJECT_STATE.md`):
  1. Skript-Version in `index.html` anheben (`app.js?v=X.Y`).
  2. `cp index.html dist/index.html && cp app.js dist/app.js && cp styles.css dist/styles.css && cp tokens.css dist/tokens.css`
  3. Git Commit lokal erstellen.

---

## 📌 5. Design System Strict Enforcement Rule
- **Regel:** Bei allen UI- und CSS-Änderungen MÜSSEN strikt die Tokens aus `DESIGN.md` und `tokens.css` verwendet werden.
- **Verbot:** Keine Hartcodierung von unvollständigen Inline-Styles oder Farb-Hex-Codes, die nicht in `DESIGN.md` / `tokens.css` definiert sind.

---

## 📌 6. Anti-Absolutismus & Trade-Off-Direktive (Blacklist & Scheinsicherheiten)
- **Verbot von Scheinsicherheiten & absoluten Heilsversprechen:**
  Begriffe wie *„identisch“*, *„völlig ausreichend“*, *„garantiert“*, *„Königsklasse“*, *„kein Verlust“*, *„100% gleichwertig“*, *„du verlierst keine Form“* oder sinngleiche Verharmlosungen sind strikt untersagt.
- **Pflicht zum Trade-Off:** Jede Trainingsverkürzung, Zeitspar-Maßnahme oder Streckenalternative (z. B. Flachlauf statt Höhenmeter, Deich statt Gelände) MUSS zwingend als physiologischer Kompromiss mit ihren konkreten Abstrichen benannt werden (Was spart Zeit? Welche De-Adaptation entsteht peripher muskulär, exzentrisch oder koordinativ?).
- **Differenzierung statt Pauschalierung:** Niemals pauschal von „der Form“ sprechen, sondern differenzieren zwischen zentraler Herzkreislauf-Ausdauer (Sauerstoffaufnahme/Fettstoffwechsel) und peripherer muskulär-koordinativer Belastbarkeit (exzentrische Bremskräfte, Trittsicherheit, Sehnen-Steifigkeit).

---

## 📌 7. Post-Wettkampf Erholungs-Regel (48h / 2 volle Tage Recovery nach Rennen)
- **Regel:** Nach jedem Sonntags-Wettkampf (Rennen / Race am Sonntag) müssen **IMMER mindestens 2 volle Tage vollständige Recovery (Montag + Dienstag)** eingeplant werden (Ruhetag / CHILL / passiv).
- **Klarstellung:** Gilt **ausschließlich für Wettkämpfe / Rennen** (nicht für reguläre sonntägliche GA1-Longruns).
- **Verbot:** Niemals am Montag oder Dienstag direkt nach einem Sonntags-Wettkampf eine Laufeinheit (auch keinen Rekom-Lauf) ansetzen. Der Wiedereinstieg darf frühestens am Mittwoch oder Donnerstag erfolgen.

---

## 📌 8. Zielzeit- & Prognose-Protokoll (Kombination 3+1: Schätzungsverbot, Daten-Separation & Impact-Check)
- **Strikte Daten-Separation:**
  - **Kategorie A (Primärdaten / SSOT):** Ausschließlich real absolvierte Läufe aus `runsData` / `defaultInitialRuns` (mit realer Distanz, Nettozeit, Hm und Herzfrequenz).
  - **Kategorie B (Hypothesen & Planungen):** Alle noch nicht gelaufenen Zielzeiten, Prognosen oder Rennabsichten tragen zwingend den Status `[HYPOTHESE]`. Textbausteine im Fließtext dürfen niemals als Primärdaten zitiert werden.
- **Schätzungs- & Proklamationsverbot für den Assistenten:**
  - Der Assistent darf **niemals eigenmächtig eine feste Zielzeit oder Ziel-Pace für einen Wettkampf proklamieren oder im Code/Briefing fixieren**.
  - Der Assistent ist verpflichtet, ausschließlich einen **mathematisch und physiologisch hergeleiteten Korridor** vorzulegen (Formel: Flach-Äquivalent via Riegel-Formel auf Basis des jüngsten Benchmark-Laufs + Höhenmeter-Zuschlag + Untergrund-/Witterungsfaktor).
- **Entscheidungshoheit beim Athleten:**
  - Erst wenn der Athlet eine konkrete Zielzeit oder einen Korridor explizit bestätigt oder vorgibt („Setze Zielzeit auf X“), darf der Wert in den Code (`raceBriefings`, `weeksData`, `targetPill`) eingetragen werden.
- **Obligatorischer Impact-Check bei neuen Wettkampf-Logs:**
  - Jedes Mal, wenn ein neuer Wettkampf oder Benchmark-Lauf geloggt wird (z. B. Martinslauf 10k), MUSS der Assistent automatisch prüfen, ob die bestehenden Zielzeiten kommender Wettkämpfe noch mit den neuen Leistungsdaten physikalisch kompatibel sind. Bei Diskrepanzen (> 5 %) muss unaufgefordert eine Korrektur-Empfehlung vorgelegt werden.

---

## 📌 9. Verpflegungs- & Rennanweisungs-Direktive (SSOT-Verpflegung & Freigabepflicht)
- **Authentische Verpflegungs-SSOT des Athleten:**
  - **Erlaubt / Authentisch:** Ausschließlich **Maltodextrin-Lösung in Softflasks** (1x oder 2x 500ml Flasks) sowie bei langen Einheiten / Trails (> 15 km) **Marzipan & Feigen** (bzw. an Strecken-VPs Bananen, Wasser, Cola).
  - **Striktes Verbot von „Gels“:** Das Wort „Gel“ / „Gels“ oder herkömmliche Industrie-Gels dürfen **niemals** in Empfehlungen, Briefings oder Code auftauchen.
- **Freigabepflicht für Renn- & Taktikanweisungen:**
  - Jede taktische Anweisung, Ausrüstungsempfehlung oder Verpflegungsstrategie in den Briefings (`raceBriefings`, Modals) darf nur verwendet werden, wenn sie aus den echten Realdaten hervorgeht oder vom Athleten explizit freigegeben wurde.
  - Das Erfinden generischer Lehrbuch-Ratschläge (wie „1 Gel bei KM 12“, „3–4 Gels“) ist ein systematischer Fehler und strikt untersagt.



