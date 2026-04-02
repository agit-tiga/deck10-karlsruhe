# DECKZEHN – Rooftop Bar Karlsruhe · Projektkontext

## Projektübersicht

Statische Website für **DECKZEHN**, eine Rooftop Bar auf Ebene 10 des Galeria Parkdecks in Karlsruhe. Die Website ist rein HTML/CSS/JS – kein Framework, kein Build-Tool, kein Backend.

## Dateistruktur

```
/
├── index.html                        # Hauptseite (One-Pager mit Sektionen)
├── jobs.html                         # Jobs & Karriere mit Bewerbungsformular
├── kontakt.html                      # Kontaktseite mit Formular & Öffnungszeiten
├── assets/
│   ├── css/
│   │   └── styles.css                # Globales Stylesheet (alle Seiten)
│   └── images/
│       ├── deck10_logo.png           # Logo (lokal, als Fallback)
│       ├── deckzehn_background.jpg   # Hero-Hintergrundbild (referenziert in CSS)
│       └── gallery/
│           ├── deck10_insta_1.png
│           ├── deck10_insta_2.png
│           └── deck10_insta_3.png
└── CLAUDE.md
```

## Design-System

**Farben:**
- `--yellow`: `#EAEC19` (Primärfarbe, Akzente, CTAs)
- `--dark`: tiefdunkler Hintergrund
- `--muted`: gedämpftes Creme/Weiß für Sekundärtext
- Sektionen wechseln zwischen `section-bg` (dunkel) und `section-bg-dark` (noch dunkler)

**Schriften (Google Fonts):**
- `Bebas Neue` – Logo, große Headlines
- `Josefin Sans` (100–600) – Navigation, Labels, Buttons (`--sans`)
- `Cormorant Garamond` (Italic, 300–600) – Fließtext, Subtitles (`--serif`)

**Typografie-Klassen:**
- `.section-label` – kleines Uppercase-Label über Titeln
- `.section-title` – große Sektionsüberschrift
- `.gold-line` – gelbe horizontale Trennlinie
- `.hero-title`, `.hero-eyebrow`, `.hero-subtitle-line` – Hero-Bereich

**Animationen:**
- `.fade-in` + `.visible` (via IntersectionObserver) – Einblend-Animation beim Scrollen
- Sticky Nav: `#nav` bekommt Klasse `.scrolled` nach 60px Scroll

## Seitenstruktur (index.html)

Sektionen in Reihenfolge:
1. `#home` – Hero mit CTA-Buttons
2. `#about` – "Unsere Geschichte" + Stats (10. Etage, 360°, ∞)
3. `#galerie` – Bildergalerie (3 lokale Bilder)
4. `#decks` – 4 Bereiche (Rooftop Lounge, Cocktail Bar, Private Events, Sound & Vibes)
5. `#events` – Upcoming Events (3 Karten mit Datum)
6. `#kontakt` – Öffnungszeiten + Anfahrt
7. Instagram-Strip + CTA-Banner + Footer

## Kontaktdaten & Inhalt

**Adresse:** Galeria Parkdeck, Ebene 10, Zähringerstraße 69, 76133 Karlsruhe  
**ÖPNV:** Tram Marktplatz (Linie 1, 2, 3, 4, 5)

**E-Mail-Adressen:**
- Allgemein: info@deckzehn.de
- Reservierungen: reservierung@deckzehn.de
- Events: events@deckzehn.de

**Social Media:**
- Instagram: @deckzehn (instagram.com/deckzehn)
- Facebook: facebook.com/deckzehn
- TikTok: tiktok.com/@deckzehn

**Öffnungszeiten:**
- Mo–Di: Geschlossen
- Mi–Do: 16:00–23:00
- Fr: 15:00–00:00
- Sa: 14:00–00:00
- So: 15:00–23:00

## Formular-Logik (rein clientseitig)

Beide Formulare (jobs.html & kontakt.html) sind **nicht wirklich funktional** – beim Absenden wird nur eine Erfolgsmeldung angezeigt (`#formSuccess` wird sichtbar), es wird keine E-Mail versendet oder API aufgerufen. Validation erfolgt inline via JS.

## Logo

Das Logo wird primär per externem URL geladen (`deckzehn.de/wp-content/uploads/...`). Bei Fehler (`onerror`) wird ein Text-Fallback mit `font-family: Bebas Neue` angezeigt. Die lokale `deck10_logo.png` existiert, wird aber im HTML nicht direkt genutzt.

## Offene Jobs (jobs.html)

- Barkeeper / Bartender (Vollzeit · Teilzeit · Minijob)
- Servicekraft / Kellner·in (Teilzeit · Aushilfe · Minijob)
- Küchenhilfe / Food Prep (Teilzeit · Minijob)
- Schichtleiter·in (Vollzeit)
- Initiativbewerbung (Alle Bereiche)

## Wichtige Hinweise

- Kein CSS-Framework (kein Tailwind, kein Bootstrap) – alles custom in `styles.css`
- Responsive via Media Queries (Breakpoint ca. 768px)
- Hamburger-Menü für Mobile (`#mobileMenu`)
- Die Website gehört zur Domain `deckzehn.de`
- Betreiber: Deckzehn GmbH, Karlsruhe
