# HTML Basics
HTML steht für "Hypertext Markup Language" und ist im Internet das Standardformat für das Layout von Websiten. Mit HTML beschreibt man, wo welche Elemente auf einer Webseite erscheinen sollen. Dafür schreibt man sein HTML in eine `.html` Datei und öffnet sie in einem beliebigen Browser (Chrome, Edge, Internet Explorer, etc). Der Browser weiß dann, welche Elemente er darstellen soll und wo er sie zu platzieren hat. Wichtig: HTML definiert keine Farben oder wie breit ein Element sein soll. Wie das geht, kommt in den CSS Basics. Auch kann HTML keine Dinge wie Popups darstellen oder Bilder hochladen. Dafür verwendet man Javascript, was wir ebenfalls später behandeln werden. HTML ist ausschließlich für die Formatierung und Elemente der Webseite zuständig.

## Grundgerüst einer Webseite
Kopiere folgenden Text in eine `.html` Datei und öffne sie mit einem Browser:
```
<!doctype html>
<html>
    <head>
        <title>
            Willkommen zu Simons Gästebuch
        </title>
    </head>
    <body>
        Hallo Seminar
    </body>
</html>
```

Das ergibt dann:

![VSCode](pictures/Basics.JPG)

herzlichen Grlückwunsch, du hast deine erste Webseite erstellt =) :clap::clap::clap:

### HTML - Elemente
Wie du oben siehst, besteht HTML aus vielen Textstücken, die mit `<>` eingeschlossen sind. Diese Elemente nennt man "HTML-tags". Ein tag hat immer einen Anfang und ein Ende. Das Ende wird mit einem `/` vor dem Tag gekennzeichnet. Alles dazwischen liegt in dem Element und wir vom Browser dann in diesem Element dargestellt. In unserem Beispiel ist das einfach ein Text in dem `<body>` tag.

```
<body> --> Start
    Hallo Seminar
</body> --> Ende
```

In manchen Fällen kann man den tag auch direkt wieder schließen, wenn man keine Elemente in dem Element darstellen will. Dafür kommt das `/` ans Ende des ersten tags. Das sieht dann so aus:
```
<body />
```
ist dasselbe wie
```
<body>
</body>
```
Natürlich sieht man hier nicht wirklich etwas, wir werden diese Art von tags später öfter sehen, deswegen stelle ich sie euch hier vor.

### `<!doctype html>` und `<html>`
Diese beiden ersten tags teilen dem Browser mit, dass der Text in der Datei html enthält. Es gibt auch andere formate, aber für diesen Workshop beschäftigen wir uns nur mit html. Am besten merken, dass die Datei immer mit diesen beiden tags beginnen sollte ;) 

### `<head>`
Im head tag teilt man dem Browser ein paar verstecket Informationen mit, die der User nicht direkt auf der Webseite sieht. Zum Beispiel kann man im head tag Farben für buttons definieren oder den Titel definieren, wie man oben in dem Beispiel sieht. Man kann den head auch komplett weglassen, aber gewöhnlich verwendet man ihn fast immer, weswegen ich ihn hier nicht weglassen wollte. Merkt euch fürs erste, dass ihr hier den Titel des Browser Tabs definieren könnt.

### `<body>`
Der Body ist der komplette Inhalt der WEbseite. Hier werdet ihr Text, Bilder und alles weitere anzeigen, was ihr von einer Webseite gewöhnt seid.

## Container (`<div>` und `<span>`)
In HTML gibt es ein paar unterschiedliche Container, von denen div und span die wichtigsten sind. Ein Container ist ein Block, in dem ihr andere Elemente, wie Bilder oder Text darstellen könnt. Normalerweiße ist eine Webseite aus extrem vielen divs und spans aufgebaut, die in einander verschachtelt sind und somit dann menüs, bildergalerien oder andere komplexere Dinge darstellen. Das div ist dabei das häufigst verwendete element. Der unterschied von div zu span ist im Grunde nur der, dass das div immer die ganze Seite des Browsers einnimmt, während das span hintereinandergereiht und mit Leerzeichen abgetrennt wird. Mit einem div generiert man also eine neue Zeile, während man mit einem span in derselben Zeile weitermachen kann.

Das hier:
```
<div>
    div und spans
</div>
<div>
    Das ist ein neuer Block
</div>
<div>
    <span>Das ist in</span>
    <span>derselben Zeile</span>
    <span>Block 3</span>
</div>
```

ergibt dann das hier (die Farben habe ich hinzugefügt um es klarer zu machen, wie genau das geht, kommt im CSS Teil):

![VSCode](pictures/divs-spans.JPG)


## Überschriften (`<h1>` etc)


## `<button>`

## `<link>`

## `<table>`

## `<select>`

## `<input>`

## invalides HTML


## Nützliche Links
https://www.w3schools.com/



