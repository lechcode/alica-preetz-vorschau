# alica-preetz.de — Projektkontext (für Claude Code)

Single-File-Website (kein Build), Modus **AUFTRAG**, gebaut nach dem Lechcode-Master-Prompt v1.7.

## Seiten
- `index.html` — Startseite (Hero, Vertrauensleiste, Über-mich-Teaser, Angebote-Übersicht, Podcast, Testimonials, Presse, FAQ, Kontakt-CTA)
- `ueber-mich.html`, `coaching.html` (3 Kernangebote als Anker-Sektionen `#coaching`/`#evolve`/`#mentoring`), `kontakt.html`
- `impressum.html`, `datenschutz.html` (gemeinsames `assets/legal.css`), `404.html`

## Seiten (Ergänzung)
- `vorschau.html` — persönliches Enthüllungs-Deckblatt („Hallo Alica") + cookiefreies Lechcode-Kalender-Band (Termin buchen, Lennys Google-Terminseite, öffnet neuen Tab). noindex.

## Token-Sync (wichtig!)
Der CSS-Token-Block (`:root{...}`, Farben/Typo/Spacing) ist **identisch in jeder Seite** inline im `<style>`-Block dupliziert (Stack-Standard: kein externes Stylesheet außer `fonts.css`/`legal.css`). Der Block ist bewusst ein **Superset** (definiert sowohl `--clay*` als auch `--rose*` auf dieselbe Palette), damit index (nutzt `--clay*`) und die Unterseiten (nutzen `--rose*`) mit **einem identischen** Block auskommen. Änderst du eine Farbe/einen Token, in **allen** HTML-Dateien synchron nachziehen: index/ueber-mich/coaching/kontakt (+ `legal.css`, `404.html`).

## Branding — Redesign „Sanfte Autorität" (02.07.2026)
Neue Design-Richtung (löst das erste Terrakotta-Redesign ab): **Elfenbein `#f6f0e6`**, **Pflaume** (Buttons `#5a2f42`, Akzenttext `#7c3a50`, dekorativ/Rosé `#b57286`), **Altgold `#b98f43`**, dunkle Bänder Pflaum-Espresso `#2a2028`. Schriften **Fraunces** (Display-Serife, Headings) + **Jost** (UI-Sans, Body) — beide lokal (`assets/fonts/*.woff2`, SIL OFL), cookiefrei. Typografie: Body = Sans, Headings = Serife (weight 400/500). Wirkung: edel, warm, feminin, nahbar — „Ruhe statt Hype". (Alte Fonts Lora/Lato/LaBelleAurore entfernt.)

## Offene Pflichten vor Go-Live (s. auch `_projekt/OFFENE-FRAGEN.md`, 21 Punkte)
1. **Web3Forms-Access-Key** eintragen (`kontakt.html`, Suche `PLATZHALTER-FORM`).
2. **E-Mail-Adresse final klären** (info@ vs. team@alica-preetz.de) — aktuell überall `info@alica-preetz.de` gesetzt (Impressums-Adresse), Kommentar „HIER" markiert die Stelle.
3. **Impressum vervollständigen:** Telefonnummer, Rechtsform, USt-IdNr. (`[VOM KUNDEN ZU BESTÄTIGEN]`).
4. **Preise EVOLVE-Aufpreis „Private Edition"** und **1:1-/Business-Mentoring-Preise** bestätigen (`[KLÄREN]`-Marker in `coaching.html`).
5. **Bildrechte der 3 Kundenfotos** (Hero, Porträt, Rooftop-Event) klären — s. `_projekt/ASSETS-LIZENZEN.md`.
6. **Vertrauensleiste-Kennzahl** („[KLÄREN]" begleitete Klientinnen) mit Kundin auf eine belegte Zahl einigen.
7. Presse-Logoleiste: aktuell Text-Chips statt Logos — echte Presselogos nachreichen.
8. **Lighthouse-/PageSpeed-Lauf nachholen** (in dieser Bau-Session nicht verfügbar, s. `_projekt/QA-CHECKLISTE.md`).
9. `noindex` erst entfernen, wenn Impressum/Datenschutz final freigegeben sind — dann auf **allen** Seiten gleichzeitig.

**MX-Records beim Go-Live niemals anfassen.**

## Deploy
GitHub Pages, Repo `lechcode/alica-preetz-vorschau`, Branch `main`/root. Deployt wird nur `website/` (ohne `_projekt/`, ohne `material/` — s. `.gitignore`).
