# Advanced JS

### js und css file import
```html
<script src="./meine-skripts.js"></script>
<link href="./styles.css" rel="stylesheet" type="text/css" />
```
### erste Zeile in JS
```javascript
window.onload = () => {
    alert('hiho')
}
```
 
### klasse an element
```javascript
// klasse einfügen
document.getElementById('plus').classList.add('green')
document.getElementByClass('primary').classList.add('green')

// entfernen von klasse
document.getElementById('plus').classList.remove('round')
```

### Style editieren
```javascript
document.getElementById('add-comment').style.backgroundColor = 'red'
```
document.getElementById('add-comment').onclick = () => {
    let name = document.getElementById('name-field')
    alert(name.value)
}

### OnClick an element hinzufügen
```javascript
document.getElementById('add-comment').onclick = () => {
    let name = document.getElementById('name-field')
    alert(name.value)
}
```

### OnClick event
```javascript
document.getElementById('comment-text').onchange = (e) => {
    let value = e.target.value.toString()
    alert(value)
}
```

### OnChange Slider
```javascript
let slider = document.getElementById('range-slider');
slider.oninput = () => {
    document.getElementById('comment-text').textContent = slider.value
}
```

### Neues HTML Element erstellen
https://developer.mozilla.org/de/docs/Web/API/Element/insertAdjacentHTML
```javascript
document.body.insertAdjacentHTML('beforeend', 
`<div id="newChild">
    <h1>${roll}</h1>
</div>`);
```

` => geht mit shift neben backspace und dann tippen auf deutscher tastatur

### Audio abspielen
```javascript
let audio = new Audio('cena.mp3')
let audioIsPlaying = false

document.getElementById('#mein-button').click(() => {
    if (audioIsPlaying) {
        audio.pause();
        audio.currentTime = 0;
        audioIsPlaying = false
    } else {
        audio.play()
        audioIsPlaying = true
    }
})
```

# Übungen
## Hoch und runterzählen mit Farbe
folgender Code:

```html
<html>
    <head>
        <script>
            window.onload = () => {
                let meinButton = document.getElementById("button-zum-klicken")
                let textFeld = document.getElementById("text-ausgabe")
                let counter = 0

                meinButton.onclick = () => {
                    counter = counter + 1
                    textFeld.innerText = counter
                }
            }
        </script>
    </head>

    <body>
        <button id="button-zum-klicken">klick mich</button>
        <div id="text-ausgabe"></div>
    </body>
</html>
```

- Erweitert den Code, damit die Hintergrundfarbe des Textfeldes zu gelb wechselt, sobald der `counter` 5 erreicht oder größer ist. Sobald der counter 10 erreicht, soll die hintergrundfarbe auf rot wechseln
- Fügt einen weiteren Button ein, der den counter jeweils um 1 verringert und das Ergebnis im Textfeld anpasst. Stell sicher, dass die Anpassung der Farbe sich noch entsprechend verhält. Bonus: sobald der `counter` unter 5 ist, soll die hintergrundfarbe nicht mehr zu sehen sein.

## Taschenrechner
Folgender Code

```html
<html>
    <head>
        <script>
            window.onload = () => {
                
            }
        </script>
    </head>

    <body>
        <input type="text" id="text-input">
        <button id="button-plus">+</button>
        <button id="button-plus">-</button>
        <button id="button-plus">*</button>
        <button id="button-plus">/</button>
        <button id="button-plus">=</button>
        <div>Ergebnis:</div>
        <div id="text-ausgabe"></div>
    </body>
</html>
```
Es soll ein Taschenrechner implementiert werden, der 2 Zahlen verrechnen kann. Der Ablauf soll folgendermaßen sein:
- Erste Zahl wird im Textfeld eingegeben
- es wird eine Rechenart ausgewählt (`+`, `-`, `*` oder `/`)
- die erste Zahl wird aus dem Textfeld gelöscht
- eine zweite Zahl wird im Textfeld eingegeben 
- mit dem Button für `=` wird das Ergebnis im Feld `text-ausgabe` angezeigt. 
- Danach kann wieder eine erste Zahl eingegeben werden und so weiter
- Bonus 1: Stelle die eingegebenen Zahlen und Rechenarten in einem Extra Feld da, damit der User weiß, was er gerade eingegeben hat
- Bonus 2: Implementiere eine History, die die vergangenen Rechnungen und Ergebnisse sichtbar macht. Zum Beispiel so:
    ```
    Vergangene Ergebnisse:
    1 + 2 = 3
    2 * 7 = 14
    24 / 6 = 4
    ```