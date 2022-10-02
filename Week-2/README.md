# Writing & Presentation Test - Week 2
## Javascript Dasar - Lanjutan
### Scope and Function
#### Scope
- **Konsep** dalam **_flow data variabel_**.
- **Menentukan** suatu **variabel** **bisa diakses** pada **scope tertentu** atau **tidak**.
    ##### Blocks
    - **Code** yang berada **didalam _curly braces_** `{}`. Yaitu **_Conditional_**, **_Function_**, **_Looping_**.
    ##### Global Scope
    - **Variabel** yang **dapat diakses dimanapun** dalam **suatu file**. Variabel **dideklarasikan diluar _Blocks_**.
    ```
    let name = "Pimiming"

    let greetings = () => {
        return name
    }

    greetings()
    ```
    ##### Local Scope
    - **Variabel** yang dapat **diakses didalam blocks saja**. Variabel **dideklarasikan didalam _Blocks_**.
    ```
    let greetings = () => {
        let name = "Pimiming"
        return name // Pimiming
    }

    console.log(name) // Error
    ```

#### Function
- Sebuah **blok kode dalam sebuah grup** untuk **menyelesaikan suatu task**.
    ##### Membuat Function
    ```
    let greetings = () => {
        return "Hello World"
    }
    ```
    ##### Memanggil Function
    ```
    let greetings = () => {
        return "Hello World"
    }

    greetings()
    ```
    ##### Parameter dan Argumen
    ```
    let pengurangan = (parameterSatu, parameterDua) => {
        return parameterSatu - parameterDua
    }

    pengurangan(70, 1)
    ```
    ##### Default Parameters
    ```
    let greetings = (name = 'People') => {
        return `Hello ${name}`
    }

    greetings() // "Hello People"
    greetings('World') // "Hello World"
    ```
    ##### Function Helper
    ```
    let greetings = () => {
        return "Hello"
    }

    let callMyName = (name) => {
        return greetings() + " " + name
    }

    callMyName('Pimiming') // "Hello Pimiming"
    ```

### DOM Manipulation
#### Mencari Element HTML
```
index.html
<p id="paragraph"></p>
<p class="tulisan"></p>

script.js
document.getElementById("paragraph")
document.getElementByClassName("tulisan")
```
#### Mengubah Konten Element
- `Element.textContent`
    ```
    index.html
    <p id="paragraph"></p>
    <p class="tulisan"></p>

    script.js
    document.getElementById("paragraph").textContent = "Paragraf Pertama"
    document.getElementByClassName("tulisan").textContent = "Paragraf Kedua"
    ```
- `Element.innerHTML`
    ```
    index.html
    <p id="paragraph"></p>
    <p class="tulisan"></p>

    script.js
    document.getElementById("paragraph").innerHTML = "<span>Paragraf Pertama</span>"
    document.getElementByClassName("tulisan").innerHTML = "<span>Paragraf Kedua</span>"
    ```
#### Membuat Element HTML
```
index.html
<p id="paragraph"></p>

script.js
const tulisan = document.createElement("span")
tulisan.textContent = "Ini Span didalam Paragraf"
document.getElementById("paragraph").appendChild(tulisan)
```
#### Menangkap Interaksi User
- `Element.addEventListener("event")`
- `Element.onevent`
#### HTML DOM Event
- Change
- Focus
- Hover
- Click
- Blur
- Scroll
- Submit
#### EventListener
- Dengan cara `Element.addEventListener("event")`
    - Bisa dihilangkan
    - Bisa ada beberapa event listener yang sama untuk 1 element
    - Memiliki argument tambahan {options}
    ##### EventListener - Click
    ```
    index.html
    <input id="user-input">
    <button id="alert-button">Show</button>

    script.js
    const input = document.getElementById("user-input")
    const button = document.getElementById("alert-button")

    button.addEventListener("click", function() {
        alert(input.value)
    })
    ```
    ##### EventListener - Blur
    ```
    index.html
    <input id="user-input">

    script.js
    const input = document.getElementById("user-input")

    input.addEventListener("blur", () => {
        if (input.value.length < 6>) {
            alert("Panjang user-input minimal 6")
        }
    })
    ```
    ##### EventListener - Form Submission
    ```
    index.html
    <form id="form-daftar" action="submit()">
        <input type="text" name="email">
        <input type="password" name="password">
    </form>

    script.js
    const form = document.getElementById("form-daftar")

    let submit = () => {
        form.addEventListener("submit", (event) => {
            event.preventDefault()

            const formData = new FormData(form)
            const values = Object.fromEntries(formData)
        })
    }
    ```