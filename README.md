# Hotel „Zum Kater" Warnemünde — Website-Relaunch

Umsetzung des Website-Relaunches als Lovable-Projekt (React + TypeScript + Tailwind + shadcn/ui).

## Lovable-Projekt

- **Editor:** https://lovable.dev/projects/18269eb7-2032-402a-8322-ef3c959ecd51
- **Öffentlich live:** https://zum-kater-heimat.lovable.app (seit 10.09.2026 bewusst öffentlich geschaltet)
- **Vorschau (Editor-Preview):** https://id-preview--18269eb7-2032-402a-8322-ef3c959ecd51.lovable.app
- **Workspace:** Manuel's Lovable
- **Projekt-ID:** `18269eb7-2032-402a-8322-ef3c959ecd51`

**Wichtig:** Die Seite ist öffentlich erreichbar, enthält aber weiterhin bewusst
unbestätigten Inhalt (siehe „Vor dem Livegang zu klären" unten und
`PLACEHOLDERS.md` im Lovable-Projekt) — u. a. eine geratene E-Mail-Adresse,
Recherchestand-Preise, Platzhalter-Bewertungszitate und ein Entwurfs-Impressum.
Vor einem echten Livegang unter der finalen Domain müssen diese Punkte geklärt sein.

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
  motivgerecht zugeschnitten, als WebP/AVIF mit `srcset` ausgeliefert
- Kompakte Verfuegbarkeitsanfrage im Hero (Anreise/Abreise/Gaeste), reicht die
  Werte an das Kontaktformular durch — **keine** echte Verfuegbarkeitspruefung,
  das ist auf der Seite auch so beschriftet
- Sticky Quick-Action-Leiste im Header: Telefon, WhatsApp (vorausgefuellte
  Nachricht), „Zimmer buchen", „Hotel-Kontakt speichern" (generiert clientseitig
  eine `.vcf` aus den echten Stammdaten). Signal und Instagram sind mangels
  bestaetigter Kontaktdaten bewusst nur als Hinweis bzw. deaktiviert angezeigt,
  nicht als kaputte Links.

### Gestaltung — zweiter Richtungswechsel (10.09.2026)

Auf ausdruecklichen Wunsch wurde die zuvor am Logo ausgerichtete warme Palette
(Warmbraun/Forstgruen, siehe vorherige Fassung dieses Abschnitts) verworfen
zugunsten einer dunklen, hochwertigen Anthrazit-Basis mit Gold/Tuerkis/Rot als
Akzenten:

| Rolle | Wert |
|---|---|
| Basisflaeche | Anthrazit `#111113`–`#161618` |
| Text auf dunkel | Warmes Off-White |
| Akzent (CTAs, Badges) | Gold `#C9A24B` |
| Akzent (Hinweise) | Meeres-Tuerkis `#2FB8AE` |
| Akzent (Fehler/Warnung) | Rot `#B23A3A` |

**Bewusst in Kauf genommen:** Das Logo (Warmbraun `#3D2B22` + Forstgruen
`#1E4620`, transparent) wurde unveraendert gelassen und kontrastiert jetzt
gegen die dunkle Flaeche, statt mit ihr zu harmonieren — im Header steht es
deshalb auf einer eigenen hellen Flaeche fuer Lesbarkeit. Die
Versalien-Typografie und der Aufbau (Vollbild-Hero, Haarlinien-Eyebrows,
rechteckige Buttons) aus der vorherigen Refinery-Anlehnung blieben erhalten,
nur die Farben wurden ausgetauscht. Der Dark-Mode-Schalter wechselt seither
zwischen einem helleren und einem tieferen Anthrazit-Ton, nicht mehr zwischen
hell und dunkel.

**Bewusst nicht uebernommen aus dem breiteren Auftrag vom 10.09.2026:** ein
hoteleigenes italienisches Restaurant „Ristorante im Kater". Laut Recherche hat
das Haus kein eigenes Mittags-/Abendrestaurant und empfiehlt stattdessen extern
das Restaurant „Kettenkasten" — das wurde beibehalten, nicht durch eine
erfundene Amenity ersetzt.

Als Backlog fuer eine spaetere Runde vermerkt (siehe `roadmap.md` im
Lovable-Projekt): Galerie/Lightbox mit Filtern, Jobs-Seite, schwebender
Audioplayer, Footer-Besucherzaehler.

### Logo-Animation

Das Logo ist als zwei Ebenen aufgebaut (`src/assets/logo-cat.svg` und
`src/assets/logo-wordmark.svg`), damit die Katze eigenstaendig animierbar ist.
Am 10.09.2026 wurde das echte Original-Logo geliefert; seine Formen wurden
verlustfrei in die beiden SVG-Ebenen nachgezeichnet, die Farben auf die
bestaetigten Markenwerte (`#3D2B22` / `#1E4620`) vereinheitlicht. Auf der
Startseite laeuft die Katze im Header an ihre Position, der Schriftzug folgt
kurz darauf:

- Laeuft **einmal pro Browser-Sitzung** (`sessionStorage`), nicht bei jedem
  Seitenwechsel
- `prefers-reduced-motion: reduce` springt ohne Bewegung direkt in den Endzustand
- Der Platz ist von Anfang an reserviert, es gibt keinen Layout-Sprung
- Auf allen Unterseiten steht das Logo unbewegt

Noch offen (Backlog, siehe `docs/lovable-brief.md`): echter E-Mail-Versand des
Anfrageformulars, Live-Verfuegbarkeit, Admin-Dashboard, Google-Places-Feed,
360-Grad-Rundgaenge, englische Fliesstexte.

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
