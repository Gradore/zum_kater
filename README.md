# Hotel „Zum Kater" Warnemünde — Website-Relaunch

Umsetzung des Website-Relaunches als Lovable-Projekt (React + TypeScript + Tailwind + shadcn/ui).

## Lovable-Projekt

- **Editor:** https://lovable.dev/projects/18269eb7-2032-402a-8322-ef3c959ecd51
- **Live-Preview:** https://id-preview--18269eb7-2032-402a-8322-ef3c959ecd51.lovable.app
- **Workspace:** Manuel's Lovable
- **Projekt-ID:** `18269eb7-2032-402a-8322-ef3c959ecd51`

Der Anwendungscode liegt im Lovable-Projekt, nicht in diesem Repository. Hier
liegen die Grundlagen (Recherche, Konzept) und der Build-Auftrag.

## Stand der Umsetzung

Gebaut (TanStack Start + TypeScript + Tailwind + shadcn/ui):

- 8 Seiten: Startseite, Zimmer & Preise, Ferienwohnungen, Unser Haus,
  Mit Hund im Kater, Umgebung & Anfahrt, Ausfluege, Kontakt & Anfrage
- Rechtstexte `/impressum` und `/datenschutz` als markierte Entwuerfe (`noindex`)
- „Welches Zimmer passt zu mir?"-Quiz, Anfrageformular mit Saison- und
  Richtpreisberechnung, Saison-Banner, Direktbuchungs-Vorteilsbox,
  Bewertungsbereich, Nachbarschaftskarte, DE/EN-Umschalter
- Echte Hotelfotos (vom Inhaber hochgeladen), waermer gegradet und
  motivgerecht zugeschnitten, als WebP mit `srcset` ausgeliefert

### Gestaltung

Orientiert an refineryhotelnewyork.com, aber bewusst waermer gehalten:
uebernommen sind Struktur und Typo-Rhythmus (Versalien mit weiter Laufweite in
Navigation, Ueberschriften und Buttons; rechteckige Buttons; Vollbild-Hero;
abwechselnde Bild-/Text-Baender; Haarlinien und Kapitaelchen-Eyebrows).
Statt kaltem Schwarz-Weiss traegt die Seite die Farben des Logos.

| Rolle | Wert | Herkunft |
|---|---|---|
| Akzent | `#1E4620` Forstgruen | Schriftzug im Logo |
| Dunkelton (Text, dunkle Baender, Hero-Verlauf) | `#3D2B22` Warmbraun | Katze im Logo |
| Flaeche | Warmes Off-White / Leinen, Sand als zweite Flaeche | |

Die Frakturschrift bleibt **ausschliesslich im Logo** — nicht in Ueberschriften
oder Fliesstext: sie ist in laengeren Texten schwer lesbar und truege eine
historische Konnotation, die dem familiengefuehrten Haus entgegenwirkt.

### Logo-Animation

Das Logo ist als zwei Ebenen aufgebaut (`src/assets/logo-cat.svg` und
`src/assets/logo-wordmark.svg`), damit die Katze eigenstaendig animierbar ist.
Auf der Startseite laeuft sie im Header an ihre Position im Logo, der Schriftzug
folgt kurz darauf. Regeln:

- Laeuft **einmal pro Browser-Sitzung** (`sessionStorage`), nicht bei jedem
  Seitenwechsel
- `prefers-reduced-motion: reduce` springt ohne Bewegung direkt in den Endzustand
- Der Platz ist von Anfang an reserviert, es gibt keinen Layout-Sprung
- Auf allen Unterseiten steht das Logo unbewegt

Austausch der Originaldateien = reiner Dateitausch, ohne Codeaenderung.

Noch offen (Backlog, siehe `docs/lovable-brief.md`): echter E-Mail-Versand des
Anfrageformulars, Live-Verfuegbarkeit, Admin-Dashboard, Google-Places-Feed,
360-Grad-Rundgaenge, englische Fliesstexte, selbst gehostete Schrift.

## Inhalt dieses Repos

| Datei | Inhalt |
|---|---|
| `docs/recherchenotizen.md` | Recherche zum Bestand: Stammdaten, Zimmer, Preise, Bewertungslage |
| `docs/konzept.md` | Relaunch-Konzept: Positionierung, Design-Richtung, Feature-Vorschläge |
| `docs/lovable-brief.md` | Der an Lovable übergebene Build-Auftrag (Scope v1) |

## Vor dem Livegang zu klären

Diese Punkte stehen bewusst **nicht** als Aussage auf der Website und müssen mit
dem Inhaber geklärt werden:

- **Renovierung 2024/2025** — unbestätigte Drittquelle. Erst nach Bestätigung
  darf „frisch renoviert" beworben werden. Es wäre das stärkste Argument gegen
  den einzigen wiederkehrenden Kritikpunkt („Einrichtung etwas älter").
- **Zimmerpreise** — Recherchestand, vor Veröffentlichung verifizieren.
- **Ferienwohnungspreise** — fehlen komplett, stehen aktuell als
  „Preis auf Anfrage".
- **Logodateien** — im Projekt liegen nachgebaute SVG-Platzhalter. Die
  Originaldateien des Hauses muessen `src/assets/logo-cat.svg` und
  `src/assets/logo-wordmark.svg` ersetzen; die Hexwerte `#3D2B22` und
  `#1E4620` sind von einem Screenshot abgelesen und am Original zu pruefen.
- **Bildrechte** — die 34 Originalfotos der bestehenden Website vor
  Weiterverwendung freigeben lassen (v. a. Umgebungsfotos Rostock/Stralsund).
- **Kettenkasten-Kooperation** — bisher nur Idee. Auf der Seite steht das
  Restaurant deshalb nur als Nachbarschaftsempfehlung, nicht als Partnerschaft
  oder Paket.
- **Fotoshooting** — vorhandene Fotos sind ehrlich, aber technisch nicht auf
  Web-Standard. Mindestens Hero- und Zimmerbilder neu, idealerweise nach einer
  eventuellen Renovierung.
