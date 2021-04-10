# Vue
Jetzt kennen wir einige Dinge aus Javascript und sind gewappnet für die Details aus Vue, also beginnen wir mit ein paar Erklärungen:

## Erstes Setup
Lade dir zuerst dieses Projekt herunter und befolge die Installationsanleitungen dort

https://github.com/modmoto/workshop-website-vue

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

## Eigene Komponenten erstellen
Wenn man nun immer weiter programmiert, wird die App.vue Datei schnell sehr groß und desto mehr man in der Datei hat, desto unübersichtlicher wird es. Deswegen kann man in Vue einzelne Teile auslagern und kann diese dann wieder verwenden. Zum Beispiel könnte ich für den Seminarteilnehmer oben eine eigene Komponente machen, damit die Liste etwas übersichtlicher wird. Dafür legt man folgende `TeilnehmerListEelement.vue` Datei an:

```
<template>
  <div class="teilnehmer-border">
    <div class="name-header">{{ name }}:</div>
    <div class="teilnehmer-detail">wohnt in {{ adresse }}</div>
    <div class="teilnehmer-detail">arbeitet in {{ einsatzort }}</div>
  </div>
</template>

<script lang="ts">
import { Component, Prop, Vue } from 'vue-property-decorator';

@Component({})
export default class TeilnehmerListElement extends Vue {

  @Prop()
  name!: string;
  @Prop()
  adresse!: string;
  @Prop()
  einsatzort!: string;
}

</script>

<style scoped>
  .teilnehmer-border {
    border: 1px solid lightgray;
  }
  
  .name-header {
    font-size: 20px;
    padding: 10px;
  }

  .teilnehmer-detail {
    font-size: 14px;
    padding: 6x;
  }
</style>
```

Die Datei sieht sehr ähnlich zu der `App.vue` Datei, wir haben ein paar Divs, ein paar Attribute in der Klasse und ein paar Styles, die das alles etwas ansehnlicher machen. Neu dazu gekommen ist das `@Prop()` über den Attributen der Klasse. Das ist wieder ein Vue feature, das man verwenden kann um der Komponente von außen Daten zu übergeben, wie in unserem Beispiel die Daten des einzelnen Teilnehmers. Ich zeige, wie wir diese Komponente nun in unserer App verwenden können:

```
<template>
  <div>
    <TeilnehmerListElement 
      v-for="teilnehmer in seminarTeilnehmer" 
      :key="teilnehmer.name" 
      :name="teilnehmer.name"
      :adresse="teilnehmer.adresse"
      :einsatzort="teilnehmer.einsatzort" 
    />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import TeilnehmerListElement from './TeilnehmerListElement.vue';

@Component({
  components: {
    TeilnehmerListElement
  }
})
export default class App extends Vue {
  seminarTeilnehmer = [
      new Freiwilliger('simon', 'Pfinztal', 'AWO Karlsruhe'), 
      new Freiwilliger('kevin', 'Berghausen', 'AWO Durlach')
    ]
}
```

Lasst uns erstmal den oberen Teil im HTML ansehen. Hier habe ich das div mit dem `TeilnehmerListElement` getauscht. Weil wir das `TeilnehmerListElement` als Vue Komponente definiert haben, können wir es nun wie ein normales HTML Element verwenden. Auch die Styles von der Komponente sind nun verfügbar. So können wir sehr einfach kleinere Teile unserer Webseite in einzelne Komponenten unterteilen und überall wieder verwenden. Wir könnten auch Buttons oder Menüelemente so in einzelne Elemente aufteilen, damit wir möglichst wenig Arbeit doppelt machen müssen. Die `@Prop()` Anweisung in der Teilnehmer komponente ermöglicht es uns auserdem, dass wir über `:name`, `:adresse` und `:einsatzort` die Daten an die Teilnehmerkomponente weitergeben können. Bei einem Button könnte man sich vorstellen, dass man ein Attribut `buttonText` hat, das dann den text des Buttons bekommen kann.

Nun shauen wir uns den rest der Klasse im Javascript teil an. Hier ist die Zeile `import TeilnehmerListElement from './TeilnehmerListElement.vue';` dazugekommen. Das sagt Vue, dass wir hier in unserer App die Komponente `TeilnehmerListElement` verwenden wollen. Also importieren wir sie. Nun kommt auch die `@Component` Anweisung ins Spiel, bei der wir der App Komponente das `TeilnehmerListElement` aktiv übergeben. Dieser Schritt macht es uns möglich im HTML einen `<TeilnehmerListElement>` tag zu verwenden, der ja eigentlich kein richtiges HTML ist. Am besten merkt ihr euch einfach, dass ihr diese beiden Zeilen so braucht, wenn ihr eine neue Komponente in eurer App verwenden wollt. 

Man kann das alles natürlich auch weitertreiben und in dem `TeilnehmerListElement` andere Komponenten importieren und verwenden, wenn diese wieder zu groß werden sollte. 