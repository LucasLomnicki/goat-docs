---
sidebar_position: 4
---


# Filter

Der **Filter** kann verwendet werden, um die auf der Karte sichtbaren Daten zu begrenzen. Sie können entweder nach **logischem Ausdruck** (z.B. nur Supermärkte mit einem bestimmten Namen visualisieren) oder nach **räumlichem Ausdruck** filtern (z.B. nur Punkte innerhalb eines bestimmten Begrenzungsrahmens anzeigen).

<div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center' }}>

  <img src={require('/img/map/filter/filter_clicking.gif').default} alt="Filterwerkzeug in GOAT" style={{ maxHeight: "auto", maxWidth: "auto", objectFit: "cover"}}/>

</div> 

## 1. Erklärung

Der **Filter** <img src={require('/img/map/filter/filter_icon.png').default} alt="Filtersymbol" style={{ maxHeight: "20px", maxWidth: "20px"}}/> ermöglicht es den Nutzern, **nur bestimmte Elemente** aus einem größeren Datensatz basierend auf spezifischen Kriterien anzuzeigen. Dieses Tool hilft, ausgewählte Elemente aus einem großen georäumlichen Datensatz zu visualisieren und ermöglicht es den Nutzern, sich auf die für sie relevantesten Informationen zu konzentrieren.

Logische und räumliche Ausdrücke können basierend auf den Attributen von **Punktlayern** und **Polygonlayern** mit unterschiedlichen Datentypen (`number` und `string`) hinzugefügt werden.

:::info

Die **Filteroperation verändert nicht die Originaldaten**. Sie kann auf jedem Layer verwendet werden, um die für die Visualisierung und Analyse verwendeten Daten zu begrenzen, ohne den zugrunde liegenden Datensatz zu ändern. Wenn der Filter zurückgesetzt wird, werden alle ursprünglichen Daten, die dem Layer zugeordnet sind, wieder sichtbar.

:::

## 2. Anwendungsbeispiele

- Alle Städte in Deutschland anzeigen, die mehr als 50.000 Einwohner haben.
- Alle Carsharing-Stationen eines bestimmten Betreibers anzeigen.
- Die Regionen anzeigen, die mehr als einen Flughafen haben.

## 3. Wie benutzt man den Filter?

### Einzel-Ausdrucksfilterung

<div class="Schritt">
  <div class="Schritt Nummer">1</div>
  <div class="Inhalt">Wählen Sie den Layer aus, auf den Sie den Filter anwenden möchten.</div>
</div>

<div class="Schritt">
  <div class="Schritt Nummer">2</div>
  <div class="Inhalt">Klicken Sie auf <code>Filter</code> <img src={require('/img/map/filter/filter_icon.png').default} alt="Filtersymbol" style={{ maxHeight: "20px", maxWidth: "20px"}}/>. </div>
</div>

<div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center' }}>
  <img src={require('/img/map/filter/filter.png').default} alt="Filterwerkzeug in GOAT" style={{ maxHeight: "auto", maxWidth: "auto", objectFit: "cover"}}/>
</div> 

<p></p>
<div class="Schritt">
  <div class="Schritt Nummer">3</div>
  <div class="Inhalt">Der <code>Aktiver Layer</code> zeigt den aktuell ausgewählten Layer an, auf den der Filter angewendet wird.</div>
</div>

<div class="Schritt">
  <div class="Schritt Nummer">4</div>
  <div class="Inhalt">Klicken Sie auf <code>+ Ausdruck hinzufügen</code>.</div>
</div>

<div class="step">
  <div class="step-number">5</div>
  <div class="content">Wählen Sie, ob Sie basierend auf einem <b>logischen Ausdruck</b> oder einem <b>räumlichen Ausdruck</b> filtern möchten.</div>
</div>

<div class="Schritt">
  <div class="Schritt Nummer">6</div>
  <div class="Inhalt">Wählen Sie das <code>Feld</code>, d.h. das Attribut, das Sie für die Filterung verwenden möchten.</div>
</div>

<div class="Schritt">
  <div class="Schritt Nummer">7</div>
  <div class="Inhalt">Wählen Sie den konkreten <code>Operator</code>, den Sie anwenden möchten. <i>Tipp: Die verfügbaren Optionen variieren je nach Datentyp des in Schritt 6 ausgewählten Attributs.</i></div>
</div>

Die **Filterausdrücke** für `number` (numerische Daten) und `string` (Textdaten) sind unten angegeben:

| Ausdrücke für `number` | Ausdrücke für `string` |
| -------|----|
| ist  | ist |
| ist nicht  | ist nicht |
| enthält  | enthält  |
| schließt aus  | schließt aus |
| ist mindestens  | beginnt mit |
| ist weniger als | endet mit |
| ist höchstens | enthält den Text |
| ist größer als | enthält den Text nicht |
| ist zwischen | ist leer |
|  | ist nicht leer |


:::tip Tipp
Für die Ausdrücke **"enthält"** und **"schließt aus"** können mehrere Werte ausgewählt werden.
:::

<div class="Schritt">
  <div class="Schritt Nummer">8</div>
  <div class="Inhalt">Legen Sie Ihre Filterkriterien fest. Die Karte wird automatisch mit Ihren gefilterten Daten aktualisiert und das Filtersymbol wird auf dem gefilterten Layer erscheinen.</div>
</div>

<div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center' }}>
  <img src={require('/img/map/filter/filter_atlayer.webp').default} alt="Filterergebnis in GOAT" style={{ maxHeight: "auto", maxWidth: "auto", objectFit: "cover"}}/>
</div> 

### Mehrfachausdrucksfilterung

Falls gewünscht, können Sie **mehrere Filter kombinieren** für eine Mehrfachausdrucksfilterung. Wiederholen Sie dazu einfach die Schritte 4-8 oben für jeden zusätzlichen Ausdruck. Im Feld <code>Logikoperator</code> können Sie zwischen den Logikkombinationen **UND** und **ODER** wählen.  
<div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center' }}>

  <img src={require('/img/map/filter/filter-results.png').default} alt="Logikoperatoren" style={{ maxHeight: "300px", maxWidth: "300px", objectFit: "cover"}}/>

</div> 

Wenn Sie **UND** wählen, werden nur die Elemente angezeigt, für die alle Filterausdrücke wahr sind. Wenn Sie **ODER** wählen, werden Elemente angezeigt, wenn einer der Filterausdrücke wahr ist. 

:::tip Tipp
Mehrfachausdrucksfilterung sollte sorgfältig und logisch angewendet werden, um das beste Ergebnis zu erzielen.
:::

### Ausdrücke und Filter löschen

Sie können entweder **einzelne Ausdrücke** aus dem Filter entfernen, indem Sie auf die drei Punkte <img src={require('/img/map/filter/3dots_horizontal.png').default} alt="Optionen" style={{ maxHeight: "25px", maxWidth: "25px", objectFit: "cover"}}/> neben dem Ausdruck klicken und dann auf `Löschen` klicken.

<div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center' }}>
  <img src={require('/img/map/filter/filter_delete.webp').default} alt="Löschen" style={{ maxHeight: "300px", maxWidth: "300px", objectFit: "cover"}}/>
</div> 

Oder Sie können **den gesamten Filter** entfernen, indem Sie unten im Filtermenü auf `Filter löschen` klicken.

<div style={{ display: 'flex', flexDirection: 'column', alignItems: 'center' }}>

  <img src={require('/img/map/filter/clear_filter.webp').default} alt="Filter löschen" style={{ maxHeight: "300px", maxWidth: "300px", objectFit: "cover"}}/>

</div>




