- setup
- <script src="./meine-skripts.js"></script>
- window.onload = () => {
    alert('hiho')
}
- ids und classes
- document get by ID
- document get by classes
- document get by tags
- on click on plus
- on click on minus
- on click when over 5 make bg red
- on click add class when over 5
    document.getElementById('plus').classList.add('green')
- on click remove class when below 5 again
    document.getElementById('plus').classList.remove('round')
- add comment - get text

document.getElementById('add-comment').onclick = () => {
    let name = document.getElementById('name-field')
    alert(name.value)
}

- else if
- style prop with visible oder background
    - textAusgabe.style.backgroundColor = 'red'

- oninput 
textField.oninput = () => {
        textAusgabe.textContent = textField.value
    }

- range onchange 
let slider = document.getElementById('range-slider');
slider.oninput = () => {
    textAusgabe.textContent = slider.value
}

- create crazy html for comment

const roll = 12

document.body.insertAdjacentHTML('beforeend', 
`<div id="newChild">
    <h1>${roll}</h1>
</div>`);


- https://developer.mozilla.org/de/docs/Web/API/Element/insertAdjacentHTML

` => geht mit shift neben backspace und dann tippen auf deutscher tastatur
