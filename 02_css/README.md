# CSS Basics
CSS steht für "Cascading Style Sheet" und ist auf Webseiten für Farben, Abstände und generelles Design zuständig. Man legt die regeln in einer `.css` Datei fest und importiert diese in seiner `.html` Datei. Zusammen kann der Browser dann erkennen, dass ihr wolltet, dass ein bestimmer Button grün sein soll und einen bestimmten Abstand zu einem anderen Element hat. In CSS gibt es oft sehr viele Möglichkeiten ein bestimmtes Design umzusetzen, also kann alles was hier gezeigt wird auf anderen Hilfeseiten komplett anders gelöst sein. Am Anfang geht es uns aber erst einmal darum, etwas Farbe in unser HTML zu bekommen.

Siehe auch:

https://github.com/modmoto/workshop-html-and-css-examples/tree/CSS

## Importieren
Man importiert das CSS File im head tag der webseite. In diesem Beispiel liegt die html Datei neben der `styles.css` Datei und wird deswegen vom Browser gefunden. Das `./` heißt für den Browser "Schaue hier dabene nach einer styles.css Datei". Man kann es auch in einen Ordner legen, dann wäre der Pfad zum Beispiel `href="./ordner/styles.css"`
```
<head>
    ...
    <link href="./styles.css" rel="stylesheet" type="text/css" />
</head>
```

Einfach kopieren, eine leere `styles.css` Datei erstellen und los gehts =)

## Syntax
Eine CSS Anweisung ist sehr simpel und besteht im Grunde nur aus zwei teilen:
```
h3 {
    color: green;
    font-size: 20px;
}
```

Der Teil vor der `{` nennt man Selektor und er definiert, welche Elemente im HTML mit den Styles versehen werden sollen, die im zweiten Teil der Anweisung zwischen den beiden `{}` stehen. Jede Zeile muss mit einem `;` abgeschlossen werden.  Hier gibt es nun fast endlose Möglichkeiten, wie das Styling der Kanten, Durchsichtigkeit, Farben, Abstände, Schriftgröße, Schriftart, Schatten und so weiter. Wir werden hier nur die nötigsten Anweisungen kennenlernen, geh aber gerne auf die Suche nach Styles, die du interessant findest. Google ist hier unsersättlich. In dem Beispiel oben, färben wir alle `<h3>` tags grün und legen die Schriftgröße auf 20 Pixel fest.

## Selektoren 
Selektoren sind wie oben beschrieben der Text, der vor dem `{` kommt. Hier kann man nicht nur HTML Elemente festlegen (wie `<div>` oder `<table>`), sondern auch präziser sein. Das ist sinnvoll, weil man selten alle Elemente einer Webseite gleich aussehen lassen möchte. Manche Buttons sollen größer oder andersfarbig sein als andere, aber man möchte in beiden Fällen den `<button>` tag verwenden. Hier wird am häufigsten dann der `class` oder `id` selector verwendet. 

### Class selektor
Der class Selektor beginnt immer mit einem `.` vor dem Selektor. Damit sagen wir dem Browser, dass er nach HTML Elemente suchen soll, die die Klasse "primary-button" haben. Der Klassenname kann hier frei gewählt werden und am besten sucht man sich einen aus, der gut zum Element passt, also nicht `a1` und `a2` zum Beispiel.
```
.primary-button {
    color: green;
    font-size: 20px;
}
```

Was ist dann eine Klasse?

Die definiert man einfach im HTML mit dem `class` attribute. Wichtig: Hier braucht man den `.` nicht! Das sieht dann so aus:

```
<button class="primary-button">
    Download
</button>
```

### Id selektor
Der id Selektor funktioniert genauso wie der class Selektor, mit dem Unterschied, dass der Selektor im CSS mit einem `#` beginnt und im HTML das `id` attribute gesetzt werden muss.
```
#main-menu {
    color: blue;
    font-size: 50px;
}
```

```
<div id="main-menu">
    <div>Home</div>
    <div>Impressum</div>
</div>
```

### Unterschied von id und class Selektor
Der wichtige Unterschied zwischen class und id ist, dass die id im HTML nur einmal vergeben werden darf, weswegen man das oft für Menüs nimmt, die nur einmal auf der Webseite vorkommen. Das class attribute darf mehrmals auf einer Webseite verwendet werden. Da die modernen Browser meistens doch mit doppelten ids umgehen können, ist das mehr eine Konvention als eine echte Regel. Allerdings kann es bei manchen Fällen sehr komische Auswirkungen haben, die sehr schwer zu finden sind, also bietet es sich an, sich an diese Konvention zu halten. Im Zweifelsfall alles als Klasse markieren und gut ist ;)

### Multiselektoren
CSS kann auch mehrere Elemete gleichzeitig markieren, das geht dann mit einem Komma:
```
.button, .primary-button {
    color: blue;
}
```
Das wirkt sich nun auf beide Klassen `button` und `primary-button` aus.

### Mehrere Klassen pro Element
Umgekehrt kann man aber auch im HTML einem Element mehrere Klassen zuweisen. Dafür muss man im HTML einfach mehrere Klassen in das class Attribute schreiben:
```
<button class="button primary-button">
    Download
</button>
```

Die Styles könnten so aussehen:
```
.button {
    font-size: 20px;
}

.primary-button {
    color: blue;
}

```

### Nested Selektoren
Man kann Selektoren auch verschachteln. Hierbei nimmt man einfach nur ein Leerzeichen zwischen den selektoren
```
.menu div {
    color: blue;
}
```

Hier wird dann in der Klasse menu alle divs genommen und blau gefärbt. Andere divs, die sich nicht in dem menu container befinden werden igoniert.


## Farben

## Größe

## Abstand

## Position

## Farben in Hex CODE

## CSS direkt in HTML
Man kann auch einen style direkt an einem html element definieren. Man tut das allerdings nur sehr selten, da es schnell sehr unübersichtlich wird. Für schnelles austesten ist es allerdings gut. Hier beachten, dass auch jeder Style mit einem `;` abgeschlossen werden muss. Sobald es also mehr als 2-3 Anweisungen sind, wird es sehr unübersichtlich. Das sieht dann so aus:

```
<div style="border: 1px solid red; background-color: aquamarine;">
    gestyled
</div>
```
