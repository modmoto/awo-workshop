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