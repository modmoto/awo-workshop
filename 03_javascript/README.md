# Javascript Basics
Nun können wir schon ein recht ansehnliche Webseite bauen, allerdings kann diese noch nichts. Buttons zu klicken bringt noch nichts, wir können nichts einblenden oder sonst irgendwie mit der Seite interagieren. Für das alles kommt dann Javascript ins Spiel. Javascript ist eine Programmiersprache, die im Web sehr verbreitet ist und durch eine große Community extrem viele Tools bietet, mit denen das Webseiten bauen einfacher gemacht wird. Diese Tools nennt man im Programmierumfeld "libraries" oder "frameworks". Man kann diese für seine Webseite runterladen und dann Funktionen wie Bilder verkleinern oder Musik abspielen nutzen. Man kann sich merken: Bei Javascript gibt es für fast alles eine Library.

Eine dieser bekannten Frameworks ist "Vue" (View ausgesprochen) und bietet allerlei tools, die eine dynamische Webseite einfach programmierbar machen. Wenn du noch keine Erfahrung mit Webseiten programmieren hast, wird dir vermutlich nicht auffallen, was hier alles im Hintegrund passiert und das ist auch gut so. Aber ob du nun "reines" Javascript oder Vue lernst, sollte keinen Unterschied machen. Heutzutage kaum noch reines Javascript programmiert, sonder immer auf Frameworks wie Vue, Angular (Google) oder React (Facebook) gesetzt. Vue hat zum Ziel Webentwicklung einfacher zu machen und bekommt das meiner Meinung nach von den drei großen Frameworks am besten hin. Wenn du schon mit Javascript auf Webseiten gearbeitet hast, bin ich mir sicher, dass du einige Verbesserungen sehen wirst.

## Erstes Setup
Lade dir zuerst dieses Projekt herunter und befolge die Installationsanleitungen dort

https://github.com/modmoto/workshop-website-vue

Lies am besten auch dort die Einführung zu Vue durch. 

## Grundsätze des Programmierens
Ein Programm ist nichts weiter als eine Datei mit Text, wie html oder css. In diese Datei schreibt man Befehle für den Computer, der diese dann von oben nach unten abarbeitet. Zum Beispiel kann man dem PC in einer Zeile sagen, dass er ein Bild runterladen soll, in der nächsten, dass er das Bild grün einfärben soll und dann in der übernächsten das Bild an eine Email Adresse sendet. Es ist wichtig hier genau zu sein, da der Computer falsch geschriebene Befehle einfach nicht ausführen kann. 

## Variablen
Keine Angst, das hat nichts mit Mathematik zu tun ;)

Variablen sind in jeder Programmiersprache vorhanden und machen es dir möglich Daten während du die Webseite verwendest zu speichern. Wenn du die Webseite neu lädst, sind alle Variablen wieder weg oder leer und die Webseite befüllt sie entsprechend wieder.

Wenn du eine Variable erstellen willst, machst du das mit `const` oder `let`.

```
const name = 'simon'
let nachName = 'heiss'

console.log(name) --> gibt "simon" aus
console.log(nachName) --> gibt "heiss" aus
```

Der Unterschied von `const` zu `let` ist, dass man `const` (steht für constant/Kontante) nur einmal befüllen darf. Also das hier geht nicht:

```
const name = 'simon'
name = 'achne doch nicht' --> Fehler
```

Mit `let` ist das allerdings möglich. Trotzdem hat es sich eingebürgert, dass man wenn möglich const verwendet, da es in sehr großen Programmen sehr kompliziert werden kann, wenn jede Stelle des Programms irgendwelche Variablen ändert. Deswegen legt man sie gerne einmal an und hat sie dann fest. Für unsere Fälle ist das noch nicht relevant, verwendet einfach was euch zuerst einfällt ;)

## Typen
Variablen können in Javascript 7 verschiedene typen haben, die für uns wichtigen sind: 
- `number` => Kommazahlen (1.3) und ganze Zahlen (4)
- `string` => Zeichenketten, wie oben 'simon'. Strings müssen immer in `'` geschrieben werden
- `boolean` => Wahr oder Falsch, in javascript dann `true` oder `false`. Das wird für Dinge verwendet wie "Ist der User eingeloggt? Dann zeige ihm seine Chatnachrichten an, sonst nicht"

Das ist wichtig zu wissen, da man verschiedene Typen nicht mixen sollte. Das hier geht:

```
const a = 2
const b = 5
const summe = a + b
```
Das hier ergibt aber keinen Sinn:
```
const istEingeloggt = true
const summe = 5
const wasAuchImmer = istEingeloggt + summe
```
Da beschwert sich dann javascript und ihr bekommt komische Ergebnisse.

## Stringoperationen
Strings werden häufig verwendet und zusammengesteckt, wenn man Nachrichten an den Nutzer ausgeben möchte. Das geht bei strings auf 2 verschiedene Arten:

```
const name = 'simon'
const nachName = 'heiss'

const vorUndNachname = name + ' ' + nachName
console.log(vorUndNachname) --> gibt "simon heiss" aus

const vorUndNachname2 =`${name} ${nachName}`
console.log(vorUndNachname2) --> gibt ebenfalls "simon heiss" aus
```

mit dem `+` hat man etwas mehr Schreibarbeit, weswegen oft der weg mit den klammern gewählt wird. Wenn man sich daran gewöhnt hat, lässt es sich auch besser lesen, aber das ist Geschmackssache.

## If
Mit einem if kann man bestimmte Teile eines Programmes ausführen, wenn eine bestimtme Bedinung zutrifft. Zum Beispiel hier geben wir je nach Inhalt in der Variable `name` eine andere Nachricht aus.
```
const name = 'simon'

if (name === 'simon') {
    console.log('Hallo simon')
} else {
    console.log('Wir kennen uns noch nicht')  
}
```
Wenn der Teil hinter dem if nicht stimmt, wird der zweig bei `else` ausgeführt.

Man kann auch andere Vergleiche machen, wie `>`, `>==`, `<` oder `<==`. Man kann hier auch eine variable mit boolean wert einfach ohne Vergleich angeben:

```
const istEingeloggt = true
if (istEingeloggt) {
    ....
} 
```

ist dasselbe wie:

```
const istEingeloggt = true
if (istEingeloggt === true) {
    ....
} 
```

## Arrays
In Javascript gibt es neben einzelnen Variablen auch Gruppen vor Variablen, die man `array` nennt. Das kann zum Beispiel ein array von string sein, die alle Namen der Seminarteilnehmer enthält.

```
const seminarTeilnehmer = ['mark', 'ramona', 'kevin']
const noten = [1, 3, 6, 3]
```

Nun kann man auf arrays einzelne Elemente beschreiben oder auslesen, wenn man das Element mit dem `[]` operator ansteuert. Zum Beispiel:

```
seminarTeilnehmer[2] = 'simon'
console.log(seminarTeilnehmer[1]) --> gibt 'ramona' aus
```
Hier ist wichtig zu wissen, dass der erste Eintrag immer mit 0 beginnt und nicht mit eins. Das hat einige Vorteile für Operationen, die wir nicht brauchen werden. Merkt es euch einfach, weil ihr euch sonst wundert, warum euch Elemente fehlen ;)

## For
Ein for kann man verwenden, wenn man für alle Elemente eines Arrays etwas tun möchte. Zum Beispiel kann man so alle Teilnehmer ausgeben:
```
for (let i = 0; i < 3; i++) {
   console.log(seminarTeilnehmer[i]);
}
```

Das for hat einen etwas kompliziert aussehenden ersten Block, den wir gleich behandeln. Was im Grunde aber passiert ist, dass der Teil zwischen den `{}` Klammern so oft ausgeführt wird, bis der Block in den `()` Klammern sagt, es ist Zeit ist aufzuhören.

Im for gibt es drei Teile in den runden Klammern, die folgende Bedeutung haben:
- `let teilnehmerIndex = 0` => fange bei 0 an
- `teilnehmerIndex < 3` => mache solange weiter, bis i nicht mehr kleiner als drei ist (also drei oder größer)
- `i++` => nachdem du alles in den Klammern `{}` ausgeführt hast, zähle i eines nach oben.

Den Befehl oben kann man also ohne for so schreiben:

```
console.log(seminarTeilnehmer[0]); --> i = 0
console.log(seminarTeilnehmer[1]); --> i = 1
console.log(seminarTeilnehmer[2]); --> i = 2
```

Das ist bei 3 Einträgen noch möglich, aber wenn man ein paar tausend Einträge hat, oder nicht weiß, wie viele Teilnehmer kommen, kann man das nur mit einem for programmieren.

Da for manchmal etwas kompliziert sein kann (das i ist schon etwas nervig auf dauer), gibt es eine Möglichkeit, das ohne i zu schreiben, die auch deutlich häufiger angewandt wird:

```
seminarTeilnehmer.forEach(teilnehmer => {
    console.log(teilnehmer)
});
```
Das sieht mit den Pfeilen und Klammern am Anfang etwas wild aus, lässt sich aber auf Dauer sehr viel besser lesen und man vergisst hier keine Elemente mehr, weil man kein i mehr hat. Im Hintergrund funktioniert das auch wie for, nur dass man das Element aus dem Array selber benennen kann und nicht mit i darauf zugreifen muss. 

## Funktionen
Häufig hat man das Problem, dass man ähnliche Probleme merhmals lösen muss und dann immer wieder Code kopieren muss. Um das zu umgehen, kann man sich eigene Funktionen schreiben, die Dinge für einen übernehmen. Zum Beispiel:

```
function fuegeNamenZusammen(vorname, nachname) {
    return `${vorname} ${nachName}`
}

const zusammen1 = fuegeNamenZusammen('simon', 'heiss')
const zusammen2 = fuegeNamenZusammen('ramona', 'müller')
```

Funktionen werden wir nicht allzuoft verwenden, aber so habt ihr es mal gesehen.
## Objekte
Objekte werden in Javascript verwendet um komplexere Datenstrukturen darzustellen. Zum Beispiel hat ein Seminarteilnehmer eine Adresse, einen Namen, ein Geburtsdatum und eine Einsatzstelle. Wenn man nun das alles in Variablen speichern wollen würde, müsste man so etwas programmieren:

```
const name1 = 'simon'
const adresse1 = 'Pfinztal'
const einsatzstelle1 = 'AWO Karlsruhe'

const name2 = 'kevin'
const adresse2 = 'Berghausen'
const einsatzstelle2 = 'AWO Durlach'
```

Hier sieht man sehr schnell, dass das komisch wirkt und man würde am liebsten diese Werte zusammenfassen. Dafür gibt es in javascript objekte:

```
const freiwilliger1 = {
    name: 'simon',
    adresse: 'Pfinztal',
    einsatzstelle: 'AWO Karlsruhe'
}

const freiwilliger2 = {
    name: 'kevin',
    adresse: 'Berghausen',
    einsatzstelle: 'AWO Durlach'
}
```

Wenn ich nun die Daten ausgeben oder ändern möchte, kann ich das, wenn ich die attribute anspreche:

```
console.log(freiwilliger1.name) --> gibt 'simon' aus
freiwilliger1.adresse = 'München' --> ändert die Adresse bei freiwilliger1
```

was daran cool ist, ist dass man diese objekte nun in ein array packen kann, weil sie beide "gleich" sind:

```
const seminarTeilnehmer = [simon, kevin]
```

und nun kann ich mit foreach wieder dinge auf einmal bearbeiten und hier zum Beispiel name und adresse pro teilnehmer ausgeben:

```
seminarTeilnehmer.forEach(teilnehmer => {
    console.log(teilnehmer.name)
    console.log(teilnehmer.adresse)
});
```
## Clickhandler

## Backend Calls