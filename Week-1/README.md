# Writing & Presentation Test - Week 1
## Unix Command Line
- **Shell** merupakan program yang digunakan untuk berkomunikasi atau memerintah sistem.
- **Command Line Interface** merupakan jenis shell yang berbasis teks. Contohnya seperti *sh*, *bash*, *zsh*, *cmd*.
- Pada **Windows** cara mengakses CLI adalah dengan **Windows + R** lalu mengetikkan **CMD** dan menekan **Enter**.
- Contoh **sintaksis** di Command Prompt :
    - Mengubah direktori menggunakan **CD** 
    `CD C:\Program Files (x86)`
    - Mengganti nama file menggunakan **REN [drive:] [path] [nama sekarang] [target]** 
    `REN D:untitled.txt renamed.txt`

### File System Structure 
- **Filesystem** mengatur bagaimana data disimpan dalam sebuah system.
- Sistem operasi **Windows & Unix-like** menyusun file dan direktori menggunakan struktur yang bentuknya mirip tree.

    #### Command untuk Navigasi
    - **pwd** untuk melihat *current working directory*.
    - **ls** untuk melihat isi file yang ada di sebuah direktori.
    - **cd [direktori]** untuk berpindah direktori.

    #### Command untuk Manipulasi Files dan Directory
    - **head** untuk melihat beberapa *line* awal dari sebuah *file text*.
    - **tail** untuk melihat beberapa *line* terakhir dari sebuah *file text*.
    - **cat** untuk melihat isi sebuah *file*.
    - **touch** untuk membuat sebuah *file*.
    - **mkdir** untuk membuat sebuah *directory*.
    - **cp** untuk meng-*copy file* atau *directory*.
    - **mv** untuk memindahkan *file* atau *directory*. Dapat digunakan juga untuk *rename*.
    - **rm** untuk menghapus *file* atau *directory*.

## Git & GitHub Dasar
- **Git** merupakan *tools* untuk *programmer* yang digunakan sebagai *Version Control System*. *Version Control System* bertugas **mencatat** setiap **perubahan** pada **_File_** pada suatu proyek yang dikerjakan secara **individu** maupun **tim**.
- **Vendor Git** yang paling umum digunakan sebagai tempat penyimpanan **_Git Repository_** yaitu **GitHub**, **GitLab**, **BitBucket**, dll.
- **Alur kerja** **_Git_** dan **_GitHub_** adalah **berkolaborasi** mengerjakan proyek yang sama tanpa harus repot *copy* *paste* *folder aplikasi* yang ter-*update*. Hal tersebut menguntungkan bagi *programmer* karena dapat menyelesaikan proyek dengan lebih efektif.

### Instalasi Git
1. Download [Git](https://git-scm.com/downloads) dan lakukan instalasi.
2. Setup Awal.
    ```
    git config --global user.name "Nama Kalian"
    git config --global user.email contoh@email.com

    Note : Email harus sama dengan email yang digunakan pada GitHub.
    ```
3. Cek Apakah Setup Berhasil.
    `git config --list`

### Membuat Repository pada GitHub
1. Melakukan **init** pada direktori.
    ```
    git init .

    Note : proses ini dilakukan di dalam direktori yang sudah kalian buat.
    ```
2. Lakukan sebuah **perubahan** pada direktori lalu **menyimpan** perubahan tersebut pada **_staging area_** menggunakan **perintah** :
    `git add .`
3. **Cek** perubahan yang telah dilakukan dengan perintah :
    `git status`
4. **Menyimpan** perubahan dari **_staging area_** ke **_local repository_** menggunakan perintah :
    `git commit -m "Pesan perubahan yang dilakukan"`
5. **Menyimpan** perubahan dari **_local repository_** ke **_remote repository_** menggunakan perintah :
    `git push origin master`

### Cloning GitHub Repository ke Local
1. **Buka** *repository* **_GitHub_** yang ingin di **clone**.
2. **Klik** tombol **_Code_** lalu **_copy_ HTTPS _link_** dari *repository*. Contoh **_link_**-nya seperti berikut :
    `https://github.com/namaAkun/contoh-aplikasi.git`
3. **Ketikkan** *code* berikut pada **_direktori_** tempat kita ingin menyimpan **_repository_** :
    `git clone https://github.com/namaAkun/contoh-aplikasi.git`

## HTML
- **HTML** adalah **singkatan** dari **_Hypertext Markup Language_**. HTML **digunakan** untuk **menampilkan konten** pada **browser**. **Konten** yang dimaksud seperti **Text**, **Video**, **Link**, **Image**, dll.
- **Dua tools utama** untuk membuat **HTML** :
    1. Browser : [Chrome](https://www.google.com/intl/id_id/chrome/)
    2. Code Editor : [Visual Studio Code](https://code.visualstudio.com/)

### Struktur HTML Sederhana
```
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>My Blog</title>
    </head>
    <body>
        Hi! This is my HTML
    </body>
</html>
```

### Menjalankan HTML
- Terdapat beberapa cara menjalankan HTML yang kita buat, yaitu :

    #### Manual
    1. **Klik kanan** pada file **HTML** buatan kita di **Visual Studio Code**.
    2. **Klik copy path** lalu **paste** pada **browser**.

    #### Live Server
    1. **Klik** icon **Extension** atau **Klik Ctrl + Shift + X** pada **keyboard**.
    2. Tulis **Live Server** lalu klik **Install**.
    3. **Setelah selesai**, balik ke **file HTML** dan **klik di pojok bawah kanan** tulisan **Go Live**.
    
### Implementasi tag HTML yang Populer digunakan
```
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>My Blog</title>
    </head>
    <body>
        <h1>Hi This is My Blog</h1>
        <p>I Like To Express My Feelings Here</p>
        <br>

        <h2>My Profile</h2>
        <ul>
            <li>Name : Fabyan Kindarya</li>
            <li>Age : 21</li>
            <li>City : Sidoarjo</li>
            <li>youtube : <a href="www.youtube.com/pimimingkindarya">Pimiming</a></li>
        </ul>

        <img src="contoh-gambar.png" alt="gambarku">
        <video controls>
            <source src="contoh-video.mp4" type="video/mp4">
        </video>

            <table>
            <tr>
                <th>Company</th>
                <th>Contact</th>
                <th>Country</th>
            </tr>
            <tr>
                <td>Alfreds Futterkiste</td>
                <td>Maria Anders</td>
                <td>Germany</td>
            </tr>
            <tr>
                <td>Centro comercial Moctezuma</td>
                <td>Francisco Chang</td>
                <td>Mexico</td>
            </tr>
        </table> 

        <form>
            <label for="fname">First name:</label><br>
            <input type="text" id="fname" name="fname" value="John"><br>
            <label for="lname">Last name:</label><br>
            <input type="text" id="lname" name="lname" value="Doe"><br><br>
            <input type="submit" value="Submit">
        </form> 
    </body>
</html>
```

### Semantic HTML
- Artinya kita **menggunakan element html** yang **sesuai dengan kebutuhan konten**. Jadi daripada kita menuliskan `<div class ="header">`, kita dapat menuliskan `<header>`. Contoh lainnya yaitu:
    - `<article>`
    - `<aside>`
    - `<details>`
    - `<figcaption>`
    - `<figure>`
    - `<footer>`
    - `<header>`
    - `<main>`
    - `<mark>`
    - `<nav>`
    - `<section>`
    - `<summary>`
    - `<time>`

### Deployment HTML dengan Netlify
1. **Masuk** ke [netlify](https://app.netlify.com/)
2. **Login** menggunakan **akun _GitHub_**
3. Klik **_New site from Git_**
4. **_Link_** dengan **akun _GitHub_**
5. **_Authorize Netlify_**
6. **Pilih** **_repository_** yang akan di **_publish_**
7. Klik **_Deploy Site_**

## CSS
- CSS adalah **bahasa** yang **digunakan** untuk **mendesain halaman website**.
- Dengan CSS kita bisa **mengubah warna**, **menggunakan font custom**, **editing text format**, **mengatur tata letak**, dan lainnya.
- Membuat **_design website_** kita **_responsive_** dengan **menyertakan kode** `<meta name="viewport" content="width=device-width, initial-scale=1.0">` **didalam _file HTML_** pada **bagian** `<head></head>`.

### Tiga Cara Menggunakan CSS
#### Inline Styles
- Inline styles adalah **menambahkan CSS** pada **_attribute element HTML_**.
    `<p style="color:red">Merah</p>`
#### Internal Styles
- Internal styles adalah **menggunakan tag** `<style></style>` pada **_file HTML_**.
    ```
    <style>
        p {
            color: red;
        }
    </style>

    <p>Merah</p>
    ```
#### External Styles
- External styles adalah **menyimpan _code CSS_** yang **terpisah** dari **_file HTML_**.
    ```
    index.html

    <link href="styles.css" type="text/css" rel="stylesheet">
    <p>Merah</p>

    styles.css

    p {
        color: red;
    }
    ```

### Penggunaan Sintaks Dasar CSS
#### Tag Name
- Merubah **_styling element HTML_** dengan menuliskan **_tag_** nya.
    ```
    index.html

    <link href="styles.css" type="text/css" rel="stylesheet">
    <p>Merah</p>

    styles.css

    p {
        color: red;
    }
    ```

#### Class Name
- Merubah **_styling element HTML_** dengan menuliskan **nama _class_** dari **_tag_** nya.
    ```
    index.html

    <link href="styles.css" type="text/css" rel="stylesheet">
    <p class="tulisan">Merah</p>

    styles.css

    .tulisan {
        color: red;
    }
    ```
#### ID Name
- Merubah **_styling element HTML_** dengan menuliskan **nama _ID_** dari **_tag_** nya.
    ```
    index.html

    <link href="styles.css" type="text/css" rel="stylesheet">
    <p id="paragraph">Merah</p>

    styles.css

    #paragraph {
        color: red;
    }
    ```

#### Flexbox
- Flexbox adalah suatu cara untuk mengatur layout atau tata letak
- Flexbox terdiri 1 parent (container) dan bisa beberapa child
- Flex direction digunakan untuk mengatur letak child
- Flex wrap mengatur tata letak child pada 1 line
- Flex flow yaitu digunakan sebagai shortcut untuk set up flex-direction dan flex-wrap secara bersamaan
- Order digunakan untuk ordering item yang ingin diatur posisinya
- Justify - content digunakan untuk mengatur tata letak antar item child secara horizontal
- Align - content digunakan untuk mengatur tata letak antar item child secara vertikal atau cross axis
- Flex-grow digunakan untuk mengatur size suatu item child pada flexbox
- Flex-shrink digunakan untuk memperkecil size suatu item child secara relatif terhadap item child lainnya
- Flex-basis digunakan untuk mengatur width setiap item child

## Algoritma
- **Algoritma** adalah **deskripsi** berupa **_step - step_** yang **dibutuhkan** untuk **menyelesaikan suatu masalah**.
- **Programming** adalah **algoritma** dan **struktur data**. Data struktur **digunakan** untuk **mengelola / manajemen** sebuah **data**. Algoritma **digunakan** untuk **menyelesaikan suatu permasalahan** menggunakan **data** tersebut.

### Algoritma Sederhana
- **Pseudocode** adalah **menuliskan algoritma** dengan **umumnya bahasa inggris** **sebelum** kita **implementasikan ke bahasa pemograman** tertentu.
- **Jenis** Pseudocode :
    - **Procedural** : cara berpikir runtut.
    - **Conditional**: jika dibutuhkan suatu percabangan masalah (if else).
    - **Looping** : sebuah perintah yg diulang-ulang.
    - **Recursive** : sebuah perintah yang memanggil method/function didalam sebuah function.

    ```
    Pseudocode:
    If student's grade is greater than or equal to 60
        Print "passed"
    else
        Print "failed"

    Javascript Code :
    if (student.grade >= 60){
        console.log("passed")
    } else {
        console.log("failed")
    }
    ```

## Javascript Dasar
### Intro Javascript
- **_Javascript_** adalah **bahasa pemrograman** yang **sangat _powerful_** yang **digunakan** untuk **_logic_** pada **sebuah website**.
- **Javascript** juga dapat **membuat website** menjadi **interaktif** dan **dinamis**.

#### Menjalankan Javascript
- Alert()
- Prompt()
- Confirm()
- Console Log
    - **Console Log** adalah **tempat** kita **mengecek logic pemrograman** yang kita kembangkan, dapat **digunakan** juga sebagai **tempat melakukan debugging**.
- Comments
    - **Sintaks** yang **digunakan** untuk **memberi keterangan** tentang **suatu statement** **menggunakan bahasa inggris** atau **bahasa indonesia**.
    - Terdapat **dua tipe** comments :
        1. **Single Comments** `//`
        2. **Multiline Comments** `/* */`

#### Tipe Data Javascript
- **Number**, mengandung semua angka termasuk angka desimal.
- **String**, grup karakter yang ada pada keyboard yaitu huruf, angka, spasi, simbol, dan lainnya.
- **Boolean**, mengandung 2 nilai yaitu TRUE atau FALSE.
- **NULL**, tipe data pada variabel / data yang tidak memiliki nilai.
- **Undefined**, tipe data yang merepresentasikan variabel / data yang tidak memiliki nilai.
- **Object**, koleksi data yang saling berhubungan.

#### Operator
- **Assignment Operator (=)**, menyimpan nilai pada sebuah variabel. Contoh :
    `let name = "Nama Anda"`
- **Mathematical Assignment Operator**
    ```
    let number = 15
    number += 1
    console.log(number) // Output: 16
    ```
- **increment and Decrement**, menambah atau mengurangi sebesar 1 nilai. Contoh :
    ```
    let number = 15
    number++
    console.log(number) // Output: 16

    let number = 15
    number--
    console.log(number) // Output: 14
    ```
- **Arithmetic Operator**
    - Pertambahan (+)
    - Pengurangan (-)
    - Perkalian (*)
    - Pembagian (/)
    - Modulus (%)
- **Comparison Operator**
    - Lebih Besar (>)
    - Lebih Kecil (<)
    - Lebih besar atau sama dengan (>=)
    - Lebih kecil atau sama dengan (<=)
    - Sama dengan (===)
    - Tidak Sama dengan (!==)
- **Logical Operator**
    - AND operator (&&)
    - OR operator (||)
    - NOT operator (!)

#### Conditional
- **Statement percabangan** yang **menggambarkan** suatu **kondisi**.
- **Mengecek kondisi spesifik** dan **menjalankan perintah** berdasarkan kondisi tersebut.
    ##### IF Statement
    ```
    if (true){
        console.log("This will run")
    }
    ```
    ##### IF ... ELSE Statement
    ```
    let capek = true
    
    if (capek) {
        console.log("Istirahat")
    } else {
        console.log("Lanjut")
    }
    ```
    ##### Truthy and Falsy
    ```
    let capek
    
    if (capek) {
        console.log(capek)
    } else {
        console.log("Variabel kosong")
    }
    ```
    ##### Switch Case Statement
    ```
    switch(mood) {
        case "Senang":
            console.log("Senyum")
            break
        case "Marah":
            console.log("Menggerutu")
            break
        case "Bingung":
            console.log("Melongo")
            break
        default:
            console.log("Poker Face")
    }
    ```
    ##### Ternary Operator
    ```
    let capek = true

    capek ? console.log("Istirahat") : console.log("Lanjut")
    ```

#### Looping
- **Statement** yang **mengulang** sebuah **instruksi** hingga **kondisi terpenuhi** atau jika kondisi **stop / berhenti tercapai**.
    ##### For Loop
    ```
    let angka = 0

    for (angka; angka <= 10; angka++){
        console.log(angka)
    }
    ```
    ##### While Loop
    ```
    let angka = 0

    while (angka <= 10){
        console.log(angka)
        angka++
    }
    ```
    ##### Do While Loop
    ```
    let angka = 0

    do{
        console.log(angka)
        angka++
    }while (angka <= 10)
    ```
    ##### Nested Loop
    ```
    for (let i = 0; angka <= 10; angka++){
        for (let j = 0; angka <= i; angka++){
            console.log(`Baris ${i}`)
            console.log(`Kolom &{j}`)
        }
    }
    ```

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