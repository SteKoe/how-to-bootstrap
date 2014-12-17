# Umsetzung eines HTML-Formulars in  Bootstrap

## Einleitung

In diesem Tutorial soll das Konzept eines Eingabeformulars in HTML umgesetzt werden.
Hierfür wird das CSS-Framework _Bootstrap_ in der Version 3.3.1 verwendet [1].

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
Die Struktur des Formulars ist in folgender Abbildung zu sehen.

![alt text][simple_form_stacked]

Aus der Abbildung wird ersichtlich, dass wir jeweils ein Label, sowie ein Eingabefeld für die verschiedenen Daten erstellen möchten.
Daher brauchen wir in jedem Fall ein `label` sowie `input`-Element.
Eine erste Umsetzung in HTML kann wie folgt aussehen:

```
<label for="name" >Vor- und Nachname:</label>
<input type="text" id="name">
```

![alt text][form-html-1]

Ruft man das Formular mit einem Browser auf, wird man bereits ein Eingabefeld mit Label sehen, jedoch ist die Darstellung abhängig vom verwendeten Browser.
Da wir die Darstellungform jedoch über Bootstrap realisieren möchten, müssen wir den Elementen CSS-Klassen zuweisen.
Bootstrap sieht für `input`, `select` oder `textarea` Felder vor, die Klasse `form-control` zuzuweisen:

```
<label for="name" >Vor- und Nachname:</label>
<input type="text" id="name" class="form-control">
```
![alt text][form-html-2]

Da diese zwei Elemente eine Gruppe darstellen, 

```
<form>
	<!-- Field: Name -->
    <div class="form-group">
        <label for="name">Vor- und Nachname:</label>
        <input type="text" class="form-control" id="name">
    </div>
    <!-- Field: Straße + Hausnummer -->
    <div class="form-group">
        <label for="street">Straße und Hausnummer:</label>
        <input type="text" class="form-control" id="street">
    </div>
    <!-- Field: Stadt -->
    <div class="form-group">
        <label for="city">City:</label>
        <input type="text" class="form-control" id="city">
    </div>
    <!-- Field: PLZ -->
    <div class="form-group">
        <label for="plz">PLZ:</label>
        <input type="text" class="form-control" id="plz">
    </div>
</form>
```
![alt text][form-vertical]

### Horizontales Formular
![alt text][simple_form]

### Erweitertes horizontales Formular
![alt text][advanced_form]

[simple_form_stacked]: simple_form_stacked.png "Simples Adress-Formular (Stacked)"
[simple_form]: simple_form.png "Simples Adress-Formular"
[advanced_form]: advanced_form.png "Erweitertes Adress-Formular"

[form-html-1]: form-html-1.png "Erweitertes Adress-Formular"
[form-html-2]: form-html-2.png "Erweitertes Adress-Formular"
[form-vertical]: form-vertical.png "Erweitertes Adress-Formular"

[1]: http://www.getbootstrap.com
[2]: http://getbootstrap.com/getting-started/#support


