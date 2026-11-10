# Anweisungen an den Agenten

## Vorschau (Technik, bitte stehen lassen)
- Die App ist index.html im Hauptordner und lädt ihre Daten per fetch aus daten/ (relativer Pfad).
- htmlpreview.github.io führt nur Skripte aus, die in der Seite selbst stehen. Bibliotheken (SheetJS, three.js, rhino3dm.js) per document.createElement('script') nachladen und erst nach onload benutzen. Kein <script src>, kein type="module", kein window.onload.
- Nach jedem Schritt committen, pushen und den Link mit Commit-Hash geben:
  https://htmlpreview.github.io/?https://github.com/BENUTZER/REPO/blob/COMMIT/index.html

<!-- Alles ab hier schreibt ihr selbst, gern zusammen mit dem Agenten:
     „Frag mich nacheinander, was in diese Datei gehört.“
     Was hinein gehört, steht auf https://tae-workshop.netlify.app
     im Abschnitt „Anweisungen an den Agenten“. -->

## Ziel

## Arbeitsweise

## Zahlen

## Entscheidungsleiter

## KI-Stufe

## Fakten zu den Daten
Siehe daten/DATEN.md.

## Unsere Entscheidungen
- Mengenliste-Viewer (index.html): lädt daten/mengenliste/Mengenliste_Beispielprojekt.xlsx automatisch, andere .xlsx per Upload/Drag & Drop.
- Funktionen: Suche (Pos., Kurztext), Filter nach Einheit, Sortieren per Spaltenkopf, Gruppierung nach Titel (Teil der Pos. vor dem ersten Punkt).
- Nur Anzeige 1:1 wie in der Excel-Datei: keine Prüfhinweise, keine Summen (gemischte Einheiten).
- Zusatzspalten Material, Volumen [m³], Tonnage [t] aus dem Kurztext (Regeln in index.html, Funktion auswerten). Rechenweg je Zeile sichtbar.
- Rohdichten Beton/Holz aus faktoren_oekobaudat.csv (kg_je_deklarierte_einheit je m³); Stahl 7850 kg/m³ als sichtbare Annahme.
- Volumen für m² (Dicke bzw. Querschnitt/Achsabstand), Stk und lfm/m (Querschnitt, Länge), m³ übernommen, t/kg über Dichte.
- Stahlprofile in Stk: Stück × Länge × Metergewicht aus profile.csv.
- „Stahlbeton“ bei tragenden Bauteilen auch ohne Textangabe (als Interpretation markiert); Fundamente, Aufbeton, Sauberkeitsschicht = Beton.
- Stahlbeton-Tonnage nur Beton; Bewehrung steht in eigenen Positionen.
- 07.02 Bewehrung Attika: 10,08 m³ × 120 kg/m³ aus dem Text (Interpretation).
- Nicht raten: fehlende Angaben (Klasse, Dicke, Rohdichte Mauerwerk/C12/15, Hohldielen, Trapezblech, psch) bleiben „offen“ mit Grund.
