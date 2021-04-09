# Javascript Basics
Nun können wir schon ein recht ansehnliche Webseite bauen, allerdings kann diese noch nichts. Buttons zu klicken bringt noch nichts, wir können nichts einblenden oder sonst irgendwie mit der Seite interagieren. Für das alles kommt dann Javascript ins Spiel. Javascript ist eine Programmiersprache, die im Web sehr verbreitet ist und durch eine große Community extrem viele Tools bietet, mit denen das Webseiten bauen einfacher gemacht wird. Diese Tools nennt man im Programmierumfeld "libraries" oder "frameworks". Man kann diese für seine Webseite runterladen und dann Funktionen wie Bilder verkleinern oder Musik abspielen nutzen. Man kann sich merken: Bei Javascript gibt es für fast alles eine Library.

Eine dieser bekannten Frameworks ist "Vue" (View ausgesprochen) und bietet allerlei tools, die eine dynamische Webseite einfach programmierbar machen. Wenn du noch keine Erfahrung mit Webseiten programmieren hast, wird dir vermutlich nicht auffallen, was hier alles im Hintegrund passiert und das ist auch gut so. Aber ob du nun "reines" Javascript oder Vue lernst, sollte keinen Unterschied machen. Heutzutage wird kaum noch reines Javascript programmiert, sonder immer auf Frameworks wie Vue, Angular (Google) oder React (Facebook) gesetzt. Vue hat zum Ziel Webentwicklung einfacher zu machen und bekommt das meiner Meinung nach von den drei großen Frameworks am besten hin. Wenn du schon mit Javascript auf Webseiten gearbeitet hast, bin ich mir sicher, dass du einige Verbesserungen sehen wirst.

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

## Klassen
Da man sich bei den Objekten nun merken müsste, wie diese Teilnehmerstruktur aussieht, kann man sich von diesem Objekt eine sogenannte Klasse bauen. Mit der Klasse kann man dann sehr einfach wieder sein Objekt erstellen und muss sich nicht merken, dass jeder Freiwillige einen Namen, eine Adresse und eine Einsatzstelle hat. Das sieht dann so aus:

```
class Freiwilliger {
  name: string;
  adresse: string;
  einsatzort: string;

  constructor(name, adresse, einsatzort) {
    this.name = name;
    this.adresse = adresse;
    this.einsatzort = einsatzort;
  }
}
```

nun kann ich mir immer neue Freiwillige erstellen, indem ich diese Klasse mit `new` so aufrufe:

```
const freiwilliger1 = new Freiwilliger('simon', 'Pfinztal', 'AWO Karlsruhe')
const freiwilliger2 = new Freiwilliger('kevin', 'Berghausen', 'AWO Durlach')

console.log(freiwilliger1.name) --> gibt simon aus
```

Das ist noch einmal um einiges kürzer uns damit sehr praktisch.

Aber lass mich noch einmal schnell die Klasse von oben erklären, da gibt es noch ein paar Dinge die man wissen muss:

```
name: string;
adresse: string;
einsatzort: string;
```
Dieser Teil der Klasse definiert, dass die Klasse diese drei Attribute hat. Der Doppelpunkt danach bedeutet, dass die attribute nur strings sein dürfen. Wenn ich also `name = 1` schreiben würde, würde sich javascript beschweren. Ich kann natürlich auch andere typen wählen, wie `geburtsjahr: number`.

Der nächste Block ist der sogenannte `constructor`:
```
constructor(name, adresse, einsatzort) {
    this.name = name;
    this.adresse = adresse;
    this.einsatzort = einsatzort;
}
```

Der `constructor` ist die Funktion einer Klasse, die aufgerufen wird, wenn ich den `new` Befehl von oben verwende. Wie bei normalen Funktionen muss ich die Parameter angeben um den constructor aufrufen zu können. Ein kleiner Unterschied ist, dass ich im constructor nichts mit `return` zurückgeben muss, dass passiert im Hintergrund automatisch. Ich bekomme also ein neues Objekt hirvorn zurück.

Fehlt nur noch das `this.`, das vor den Attributen im Konstruktor steht. `this.` macht dem browser klar, dass er das Attribut der Klasse verwenden soll und nicht eine andere variable. Das wirkt etwas seltsam, weil man hier nun zwei gleichnamige Variablen haben kann (eine mit `this.` und eine ohne), diese aber unterschiedliche Werte haben können. Merkt euch einfach, dass ihr in Klassen imemr mit `this.` arbeiten müsst, wenn ihr etwas ändern wollt.

Weiterhin kann man Klassen mit Funktionen erweitern, die einem das Leben leichter machen. Zum Beispiel:

```
class Freiwilliger {
  name: string;
  adresse: string;
  einsatzort: string;

  constructor(name, adresse, einsatzort) {
    this.name = name;
    this.adresse = adresse;
    this.einsatzort = einsatzort;
  }

  getCompleteInfo() {
      return `${this.name} ${this.adresse} ${this.einsatzort}`
  }
}
```

Wie die Funktionen weiter oben kann ich nun an meinen Freiwilligen diese Hilfsfunktion aufrufen und muss mir diese nicht überall neu erstellen:
```
const freiwilliger1 = new Freiwilliger('simon', 'Pfinztal', 'AWO Karlsruhe')

console.log(freiwilliger1.getCompleteInfo()) --> gibt 'simon Pfinztal AWO Karlsruhe' aus
```

Auch das erspart einem auf Dauer extrem viel Code und deswegen werden Klassen zusammen mit Funktionen sehr häufig verwendet.

# Vue
Jetzt kennen wir einige Dinge aus Javascript, also beginnen wir mit ein paar Erklärungen zu Vue:

## .vue Dateien
In Vue erstellt man keine .html Dateien, sondern .vue Dateien. Eine .vue Datei vereint HTML, CSS und Javascript in einem und sieht so aus:

```
<template>
  <div class="hallo-welt" @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class CounterComponent extends Vue {

  counter = 0;

  countUp() {
    this.counter = this.counter + 1;
  }
}

</script>

<style scoped>
  .hallo-welt {
    background-color: aqua;
    text-align: center;
    padding: 10px;
    cursor: pointer;
  }
</style>
```

Bei Vue gilt das sogenannte "Komponenten" Prinzip und alle .vue Dateien sind für sich abgeschlossene Komponenten. Ich könnte mir also in Vue einen Button stylen und mit Funktionen versehen und diesen dann in jedem anderen Vue Projekt wieder verwenden. Wenn du genau hinsiehst, wirst du HTML, CSS und Javascript in der .vue Datei von oben wiedererkennen. Der erste Teil ist unser HTML:

```
<template>
  <div class="hallo-welt" @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
  </div>
</template>
```

Das `<template>` tag ist ein spezielles tag, das Vue dazu verwendet dem Browser zu sagen, dass es hier eine Komponente definiert. Merkd dir einfach, dass bei Vue um das HTML immer ein `<template>` tag gemacht werden muss. Wenn du dann weiterlist siehst du, dass die Komponente nur einen div container ausgibt, in dem "Hallo zusammen" steht. Zum `@click` komme ich später, aber grundsätzlich ist das alles sehr ähnlich zu normalen HTML. Du kannst nun in das div wie gewohnt buttons, andere divs, Tabellen und so weiter einfügen und Vue wird diese Elemente wie in HTML ausgeben.

Weiter kann man in Vue auch Styles definieren. Das ist der letzte Teil des Beispiels und sollte dir sehr bekannt vorkommen:

```
<style scoped>
  .hallo-welt {
    background-color: aqua;
    text-align: center;
    padding: 10px;
    cursor: pointer;
  }
</style>
```

Auch hier kannst du alle möglichen CSS Eigenschaften verwenden, die du sonst in normalen CSS auch verwenden würdest. Und da diese CSS Eigenschaften in derselben Datei stehen, kannst du diese Datei wo anders hinkopieren und es wird exakt so aussehen, wie du es dir vorgestellt hast. Das Attribut `scoped` bedeutet, dass der Style nur in dieser Datei gilt, also musst du dir keine Sorgen machen, dass du eine Klasse zwei mal definierst und auf einmal ein anderes Element anders aussieht.

Der etwas speziellere Teil ist der Javascript teil in der Mitte:

```
<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class Counter extends Vue {

  counter = 0;

  countUp() {
    this.counter = this.counter + 1;
  }
}

</script>
```

Alles was zwischen dem `<script>` tag steht ist der Programmcode, der Vue ausühren kann. Wie ihr von oben noch wisst, gibt es in Javascript Klassen. Was wir hier definieren ist eine Klasse mit Namen "App" und definieren mit `extends Vue`, dass es sich hierbei um eine Vue Komponenten handeln soll. Das `@Component({})` über der Klasse ist von Vue so vorgegeben, kopiert es einfach und nehm hin, dass es nötig ist, das kommt in bestimmten Fällen noch anders zu Geltung. Der Teil dazwischen sollte uns nun wieder sehr vertraut vorkommen, denn es ist nicht anderes als eine Klasse, wie unsere Freiwilligen Klasse von oben. Ich habe ein Attribut `counter` und eine Funktion `countUp()`. `counter` wird hier gleich auf den Wert 0 gesetzt, also braucht man ihn nicht im `constructor` beschreiben.

## HTML und Javascript verbinden

### Eventhandler

Jetzt nochmal zurück zum HTML und dem ominösen `@click` Attribut im `div`:
```
<div @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
</div>
```
Hier kommt nun die Verbindung zwischen HTML und unserem Programm. Und zwar gibt es für alle HTML Elemente sognenannte "EventHandler". In unserem Fall ist das der "ClickEventHandler". Vielleicht kannst du es dir schon denken, aber dieser Eventhandler wird ausgeführt, sobald jemand auf das div klickt. Was dann passiert ist, dass der EventHandler unsere `countUp()` Funktion aufruft, die unsere `counter` Variable um eines erhöht. Es gibt noch sehr viel mehr dieser EventHandler, wie `@drag` oder `@mouseenter`, die beim ziehen eines elementes oder wenn die Maus das Element erreicht ausgelöst werden. Diese Händler sind der Grundbaustein für eine interaktive Webseite. Am häufigsten verwendet man allerdings `@click`.

### Databinding
Die Rückrichtung von unserere `counter` Variable in unser HTML kannst du dir vermutlich auch schon denken. Im `div` gibt es mitten im Text diesen Teil: `{{ counter }}`. Wenn man in Vue im HTML `{{  }}` verwendet, wird alles dazwischen zu javascript. Ich kann also dazwischen auf meine Attribute der Klasse weiter unten zugreifen und diese Anzeigen. Ich könnte hier auch kurze Javascript Statements schreiben oder strings zusammenpacken, wie `{{ counter + " mal" }}`. Dann würde im HTML "3 mal" an der Stelle auftauchen. Diesen Vorgang nennt man dann "Databinding", da man die Daten an das HTML bindet.

### Databinding an HTML Attribute
Es gibt noch eine weiter Art und Weise, wie man das HTML vom Javascript aus verändern kann. Das HTML oben kann man so erweitern

```
<div @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
    <button :disabled="counter > 5">disabled button</button>
</div>
```
Wie man sieht, wird hier in den "" eine Berechnung gemacht, ob der `counter` größer 5 ist. Stimmt das, wird true zurückgegeben und der button wird disabled. Das funktioniert nur, weil die : vor disabled Vue dazu anhalten, den Wert zwischen "" als Javascript Code anzusehen und auszuwerten. Man kann hier auch auf ein boolean property zugreifen, das man dann noch in der Klasse definieren und befüllen muss. Natürlich kann man auch andere Attribute so dynamisch ändern, wie zum Beispiel `:class` um dann zum Beispiel den Hintergrund des divs auf rot zu ändern, indem man eine neue CSS Klasse dynamisch zuweist, sobald der Counter fünf überschreitet.

## V-If
Vue bringt auch noch ein paar coole Features mit, mit denen man Einfach ins HTML eingreifen kann. Ein beliebtes Element ist `v-if` und es kann so verwendet werden:

```
<div class="hallo-welt" @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
    <div v-if="counter > 5">COUNTER ZU HOCH!!!</div>
</div>
```
Das `v-if` bezieht sich immer auf das Element in das es reingeschrieben wird und blendet das Element aus, wenn die Bediungung in den "" nicht erfüllt ist. In unserem Fall wird die Warnung also erst erscheinen, wenn der Counter größer als 5 ist. Wie bei dem Databinding mit Doppelpunkt von oben, wird alles in den "" als Javascript code ausgewertet.

Wo es ein if gibt, darf ein else nicht fehlen, also ist folgende Sache ebenfalls möglich:

```
<div class="hallo-welt" @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
    <div v-if="counter > 5">COUNTER ZU HOCH!!!</div>
    <div v-else>Alles ok</div>
</div>
```

Ähnlich wie bei unserem Javascript `if-else`, wird hier der zweite Teil nur angezeigt, wenn der erste Teil nicht zutrifft. Am Anfang sieht man nur das div "Alles OK" und wenn der Counter 5 überschreitet, wird das "Alles OK" entfernt und mit der Warnung ersetzt.

Und auch wie bei Javascript gibt es das `else if`, das dann so aussehen könnte:
```
<div class="hallo-welt" @click="countUp()" >
    Hallo zusammen, es wurde {{ counter }} mal geklickt.
    <div v-if="counter > 5">COUNTER ZU HOCH!!!</div>
    <div v-else-if="counter > 3">Gefahr</div>
    <div v-else>Alles ok</div>
</div>
```

## V-For
Wenn man Listen in Vue darstellen will, kann man das mit `v-for` machen:

```
<template>
  <div>
    <div v-for="teilnehmer in seminarTeilnehmer" :key="teilnehmer">
      {{ teilnehmer }}
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class App extends Vue {
  seminarTeilnehmer = ['simon', 'kevin', 'marion']
}
```

Hier haben wir in unserer Klasse eine Liste von strings, die unsere Seminarteilnehmer sind. Mit `v-for` gehe ich nun, wie bei `foreach` in javascript alle elemente der Liste durch und gebe für jedes ein `div` aus, das den teilnehmer sring mit `{{ teilnehmer }}` ausgibt. Das `:key` attribute muss hier immer gesetzt werden, damit vue mit den Listen nicht durcheinander kommt. Über den key kann Vue das einzelne `div` wieder erkennen. Hier einfach merken, dass der key einzigartig sein muss, also einfach "test" als key übergeben wird Probleme bereiten.

Man kann `v-for` auch mit Objekten verwenden. Im Beispiel unserer Freiwilligen Klasse kann ich ein etwas komplexeres Listenelement bauen:
```
<template>
  <div>
    <div v-for="teilnehmer in seminarTeilnehmer" :key="teilnehmer.name">
      <div>{{ teilnehmer.name }}:</div>
      <div>wohnt in {{ teilnehmer.adresse }}</div>
      <div>arbeitet in {{ teilnehmer.einsatzort }}</div>
    </div>
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';

@Component({})
export default class App extends Vue {
  seminarTeilnehmer = [
      new Freiwilliger('simon', 'Pfinztal', 'AWO Karlsruhe'), 
      new Freiwilliger('kevin', 'Berghausen', 'AWO Durlach')
    ]
}
```
