# Umsetzung eines HTML-Formulars in  Bootstrap

## Einleitung

In diesem Tutorial soll das Konzept eines Eingabeformulars in HTML umgesetzt werden.
Hierfür wird das CSS-Framework _Bootstrap_ in der Version 3.3 verwendet [1].

Bootstrap ist eine Sammlung von vorgefertigten CSS-Komponente bzw. Elementen, die bereits so in CSS umgesetzt sind, dass diese in einer Vielzahl an Browser identisch dargestellt werden [2].
Die einzelnen Komponenten bedarfen einer speziellen Struktur in Form von Standard-HTML-Tags.

## Formulargestaltung
Bootstrap sieht für die Darstellung von Formularen vor, dass alle Formularelemente in logische Gruppen eingeteilt werden:
Eine Gruppe besteht daher in der Regel aus einem Eingabefeld `input`, `select` oder `textarea`, sowie einem dazugehörigen Label.
Grundsätzlich können Label auch ausgelassen werden, jedoch beinhalten diese die Bezeichnung des folgenden Eingabefeldes.
Ein `label` sollte mit Hilfe des `for`-Attributs immer eine eindeutige Referenz auf ein Element im Formular haben.
Hierfür muss die ID des jeweiligen Formularelements verwendet werden:

```
<label for="myCoolInputField">Mein cooles Inputfeld:</label>
<input id="myCoolInputField" type="text">
```

Für Checkboxen oder Radiobuttons gibt es Ausnahmen, da diese meist innerhalb eines Labels definiert werden und die Beziehung durch die Eltern-Kind-Beziehung geschaffen wird:

```
<label>
	<input type="checkbox">
	Check me, if you can!
</label>
```

Dies erlaubt es einem Benutzer durch klick auf das Label, das zugehörige Eingabefeld zu aktivieren. 

### Einfaches Formular
In diesem Abschnitt wollen wir ein einfaches Formular in HTML umsetzen.
Die gewünschte Struktur ist in folgender Abbildung skizziert.
Ziel dieses Abschnitts ist es, die abgebildete Skizze mit Hilfe vom Bootstrap umzusetzen.

![alt text][simple_form_stacked]

Aus der Abbildung wird ersichtlich, dass wir jeweils ein Label, sowie ein Eingabefeld für die verschiedenen Daten erstellen möchten.
Daher brauchen wir in jedem Fall ein `label` sowie `input`-Element.
Eine erste Umsetzung in HTML sieht wie folgt aus:

```HTML
<label for="name">Vor- und Nachname:</label>
<input type="text" id="name">
```

Ruft man das Formular mit einem Browser auf, wird man bereits ein Eingabefeld mit Label sehen, jedoch ist die Darstellung abhängig vom verwendeten Browser.
Da wir die Darstellungform jedoch über Bootstrap realisieren möchten, müssen wir den Elementen CSS-Klassen zuweisen.
Bootstrap sieht für `input`, `select` oder `textarea` Felder vor, die Klasse `form-control` zuzuweisen. 
Das `label` Element erhält das Attribut `control-label`.

```HTML
<label for="name" class="control-label">Vor- und Nachname:</label>
<input type="text" id="name" class="form-control">
```

Da diese zwei Elemente eine Gruppe darstellen, sieht Bootstrap vor, dass diese Elemente in einen DIV-Container zusammengefasst werden, welcher mit der CSS-Klasse `form-group` versehen ist. 
Setzt man die zu Anfang gegebene Skizze für alle Felder um, erhält man folgenden HTML-Code:

```HTML
<form action="/adresses" method="POST">
	<!-- Field: Name -->
    <div class="form-group">
        <label for="name" class="control-label">Vor- und Nachname:</label>
        <input type="text" class="form-control" id="name">
    </div>
    <!-- Field: Straße + Hausnummer -->
    <div class="form-group">
        <label for="street" class="control-label">Straße und Hausnummer:</label>
        <input type="text" class="form-control" id="street">
    </div>
    <!-- Field: Stadt -->
    <div class="form-group">
        <label for="city" class="control-label">City:</label>
        <input type="text" class="form-control" id="city">
    </div>
    <!-- Field: PLZ -->
    <div class="form-group">
        <label for="plz" class="control-label">PLZ:</label>
        <input type="text" class="form-control" id="plz">
    </div>
</form>
```

### Horizontales Formular
![alt text][simple_form_horizontal]

### Erweitertes horizontales Formular
![alt text][simple_form_horizontal_advanced]

[simple_form_stacked]: simple_form_stacked.png "Simples Adress-Formular (Stacked)"
[simple_form_horizontal]: simple_form_horizontal.png "Simples Adress-Formular"
[simple_form_horizontal_advanced]: simple_form_horizontal_advanced.png "Erweitertes Adress-Formular"

[1]: http://www.getbootstrap.com
[2]: http://getbootstrap.com/getting-started/#support


