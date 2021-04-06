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

## `<head>`

## `<body>`

## `<div>` und `<span>`
`<div>` und `<span>` 

## `<h1>` etc


## `<button>`

## `<link>`

## `<table>`

## `<select>`

## `<input>`

## invalides HTML


## Nützliche Links
https://www.w3schools.com/



