# JQUerry und advanced JS
- einbinden von css und js
- js import erklären
- jquerry stuff
https://www.w3schools.com/jquery/jquery_dom_get.asp

```html
<script src="https://code.jquery.com/jquery-3.6.0.min.js" integrity="sha256-/xUj+3OJU5yExlq6GSYGSHk7tPXikynS7ogEvDej/m4=" crossorigin="anonymous"></script>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
```

```js
$('document').ready(() => {
    $('#mein-button').click(async () => {
        const response = await axios.get('https://simon-guesbook-backend.herokuapp.com/greetings');

        if (response.data) {
            let meineKommentare = []

            response.data.forEach(element => {
                let neuesKommentar = $(`<div class="kommentar">${element.user} sagte: ${element.greeting}</div>`)
                meineKommentare.push(neuesKommentar)
            });

            $('#data-container').append(meineKommentare)

            const komm = $('#kommentar-feld').val()
            console.log(komm)
        }
    })
})
```
