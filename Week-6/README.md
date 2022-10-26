# Writing & Presentation Test - Week 6
## Web Server & REST API
### Web Server
- **Web server** terdiri dari **2 komponen** penting :
    1. Hardware
    2. Software
- **Hardware** adalah komputer yang menyimpan software web server dan komponen file situs web.
- **Software** adalah web server yang mengontrol bagaimana pengguna mengakses file yang di hosting.
- **Static Web Server** adalah web server yang mengirim file yang di hosting kepada pengguna sama seperti yang ada pada server.
- **Dynamic Web Server** adalah web server yang mengirim file yang di hosting kepada pengguna yang selalu update.
- **Server Side Programming** adalah web server yang menunggu client request message, melakukan proses ketika request sampai, lalu memberikan response ke web browser dengan HTTP response message.
    #### Hal - Hal yang dapat dilakukan pada Server-Side
    - Efisiensi penyimpanan dan pengiriman informasi.
    - Menyesuaikan user experience.
    - Mengontrol akses pada content.
    - Menyimpan informasi sesi / status.
    - Pemberitahuan dan komunikasi.
    - Analisa Data
### REST API
- **REST (Representational State Transfer)** adalah gaya arsitektur untuk menyediakan standar antara sistem komputer di web sehingga memudahkan sistem untuk berkomunikasi satu sama lain.
    #### Komunikasi antara Client dengan Server
    ##### Membuat Requests
    **REST** memerlukan request yang dibuat oleh client yang bertujuan untukmendapatkan atau mengubah data pada server. Sebuah request biasanya terdiri dari :
        - **HTTP Verb**, menentukan operasi apa yang akan dilakukan.
        - **Header**, memperbolehkan client untuk mengirim informasi tentang request yang dikirim.
        - **Path** terhadap resource tujuan.
        - **Message body** opsional yang mengandung data.
    ##### HTTP Verbs
    Terdapat 4 **HTTP verb dasar** yang digunakan dalam request untuk berinteraksi dengan resource pada REST system :
        - **GET** digunakan untuk mendapatkan data spesifik (dengan id) atau koleksi data.
        - **POST** digunakan untuk membuat data baru.
        - **PUT** digunakan untuk mengupdate data spesifik (dengan id).
        - **DELETE** digunakan untuk menghapus data spesifik (dengan id).
    ##### Headers and Accept Parameters
    Tipe umum yang biasa digunakan :
        - **Image** - image/png, image/jpeg, image/gif
        - **Audio** - audio/wav, audio/mpeg
        - **Video** - video/mp4, video/ogg
        - **Application** - application/json, application/pdf, application/xml, application/octet-stream
    ##### Paths
    Request harus mengandung path pada resource yang akan dilakukan operasinya. Seperti contoh `myapi.com/customers/15/orders/9` yang artinya kita mengakses customer dengan id 15 melakukan order barang/hal dengan id 9.
    ##### Response Codes
    Macam - macam response codes :
        - **200** (OK)
        - **201** (CREATED)
        - **204** (NO CONTENT)
        - **400** (BAD REQUEST)
        - **403** (FORBIDDEN)
        - **404** (NOT FOUND)
        - **500** (INTERNAL SERVER ERROR)
    Response codes sesuai HTTP verb :
        - **GET** - 200 (OK)
        - **POST** - 201 (CREATED)
        - **PUT** - 200 (OK)
        - **DELETE** - 204 (NO CONTENT)
## Intro Node JS
### Definisi
**Node.js** adalah platform JavaSCript yang dapat berjalan di backend atau server-side di komputer secara langsung. Node.js berjalan menggunakan **V8 engine** pada Chrome, **SpiderMonkey** engine pada Mozilla, dan **Chakra** engine pada Microsoft Edge.
### Instalasi
```
Ubuntu / Debian
$sudo apt-get install nodejs

Fedora / Centos
$sudo yum install node

Windows
https://nodejs.org/en/download/
```
### Running / Executing
```
-------------------------
app.js

console.log("Halo Dunia")
--------------------------

node app // Output : Halo Dunia
node app.js // Output : Halo Dunia
```
### Built-in Modules
1. **Console**  `console.log("Halo Dunia")`
2. **Process**  `process.argv`
3. **OS**       `os.platform()`
4. **Util**     `let result = util.format(Halo %s saldo anda %d, 'Fabyan', 1000);`
5. **Events**   
    ```
    let fs = require('fs');
    let rs = fs.createReadStream('./demofile.txt');
    rs.on('open', function () {
        console.log('The file is open');
    });
    ```
6. **Errors**
    ```
    try {
        require('node:vm').runInThisContext('binary ! isNotOk');
    } catch (err) {
        // 'err' will be a SyntaxError.
    }
    ```
7. **FS**
    ```
    fs.readFile('/etc/passwd', (err, data) => {
    if (err) throw err;
        console.log(data);
    });
    ```
8. **HTTP**
    ```
    const server = http.createServer((req, res) => {
        res.setHeader('Content-Type', 'text/html');
        res.setHeader('X-Foo', 'bar');
        res.writeHead(200, {'Content-Type': 'text/html'});
        res.end('ok');
    });
    ```
## Express JS
### Definisi
**Express** adalah salah satu **package NodeJS** yang memungkinkan kita untuk **membuat HTTP REST API** ataupun aplikasi web dengan mudah.
- RESTFUL API emiliki 4 komponen penting yaitu :
    - URL Design
    - HTTP Verbs
    - HTTP Response Code
    - Format Response
    ```
    GET http://localhost:8080/hello

    # response
    status : OK
    status code : 200
    body : application/json
    {
        "name" : "fabyan",
        "age" : 21,
        "greeting" : "hello salam kenal"
    }
    ```
### Instalasi
- **Express** merupakan modules atau package yang dikembangkan menggunakan bahasa javascript.
    ```
    npm init -y
    npm install express --save
    ```
- **Nodemon** merupakan modules atau package yang mempermudah develope server side application yaitu automatis menjalankan server ketika ada perubahan.
    `npm install -g nodemon`
### Routing
#### Basic Syntax ExpressJS
```
const express = require('express')
const app = express()
const port = 3000

app.get('/', (req, res) => {
    res.send('Hello World!')
})

app.listen(port, () => {
    console.log('Server is running on port 3000')
})
```
#### Basic Routes
##### Routes
- **Routes** adalah sebuah **endpoint yang dapat kita akses menggunakan URL di website**. Didalam routes kita perlu menentkan method API, alamat dan response apa saja yang akan dikeluarkan.
    ```
    app.get('/', (req, res) => {
        res.send('Hello World')
    })
    ```
- Untuk menjalankannya kita dapat mengetikkan di terminal `node nama_file.js` lalu membuka browser dengan URL `https://localhost:3000/`
##### Method
Dalam **REST API** terdapat **method** :
- **POST**
- **PUT**
- **PATCH**
- **DELETE**
##### Response
Dalam route kita dapat mengirim response menggunakan perintah `res.write()` untuk mengirim plain text ketika mengakses route tersebut. Contohnya seperti berikut :
```
app.get('/hello', (req, res) => {
    res.status(200).json({
        "name" : "fabyan,
        "age' : 21,
        "greeting" : "Halo salam kenal"
    })
})
```
##### Query
Query merupakan parameter yang digunakan untuk membantu menentukan tindakan yang lebih spesifik. Contoh query melalui URL `https://localhost:3000/hello?name=fabyan&age=23`, pada file js seperti :
```
app.get('/hello', (req, res) => {
    let name = req.query.name
    let age = req.query.age

    res.status(200).json({
        name : name,
        age : age,
        greetings : "Halo salam kenal"
    })
})
```
##### Parameter
Parameter merupakan value yang digunakan untuk membantu menentukan tindakan yang lebih spesifik yang ditulis melalui URL `https://localhost:3000/hello/fabyan/23`, pada file js seperti :
```
app.get('/hello/:name/:age', (req, res) => {
    let name = req.params.name
    let age = req.params.age

    res.status(200).json({
        name : name,
        age : age,
        greetings : "Halo salam kenal"
    })
})
```
##### Nested Route
```
Sebelum :

app.get('/hello/fabyan', (req, res) => {
    res.send("Halo saya fabyan")
})

app.get('/hello/kindarya', (req, res) => {
    res.send("Halo saya kindarya")
})

app.get('/hello/pimiming', (req, res) => {
    res.send("Halo saya pimiming")
})

---------------------------------------------

Sesudah :

app.use("/hello", hello)

const express = require('express')
const hello = express.Router()

hello.get('/fabyan', (req, res) => {
    res.send("Halo saya fabyan")
})

app.get('/kindarya', (req, res) => {
    res.send("Halo saya kindarya")
})

app.get('/pimiming', (req, res) => {
    res.send("Halo saya pimiming")
})
```
### Middleware
**Middleware function** adalah sebuah fungsi yang memiliki akses ke **object request (req)**, **object response (res)**, dan sebuah **fungsi next** didalam request-response cycle.
#### Fungsi Middleware
##### Menjalankan Kode Selanjutnya
```
const express = require('express')
const app = express()

const skilvulLogger = function (req, res, next) => {
    console.log("Halo skilvul, request diterima")
    next()
}

app.use(skilvulLogger)

app.get('/', function (req, res) {
    res.send('Hello Skilvul!')
})

app.listen(3000)
```
##### Memodifikasi Object Request dan Object Response
```
const express = require('express')
const app = express()

const addRequestTime = function (req, res, next) => {
    req.requestTime = Date.now()
    next()
}

app.use(addRequestTime)

app.get('/', function (req, res) {
    let responseText = 'Hello World<br>'
    responseText += '<small>Requested at: ' + req.requestTime + '</small>'
    res.send(responseText)
})

app.listen(3000)
```
##### Menghentikan Request-Response Cycle
```
const express = require('express')
const app = express()

const stopHere = function (req, res, next) => {
    res.send("<p>request stop from middleware</p>")
}

app.use(stopHere)

app.get('/', function (req, res) {
    let responseText = 'Hello Skilvul!'
    res.send(responseText)
})

app.listen(3000)
```
#### Cara Penggunaan
##### Application Level Middleware
```
const addRequestTime = funtion (req, res, next) {
    req.requestTime = Date.now()
    next()
}

app.user(addRequestTime)
```
##### Router Level Middleware
```
const express = require('express')
const UserRouter = express.Router()
const AdminRouter = express.Router()

const logUserAction = function(req, res, next) {
    const username = req.body.username

    console.log(`username ${username} access the API`)

    next()
}

userRouter.use(logUserAction)

UserRouter.get('/users', function(req, res) {
    res.send('all user data')
})

AdminRouter.get('/admins', function(req, res) {
    res.send('all admin data')
})
```
##### Error Handling Middleware
```
const express = require('express')
const app = express()

const errorHandling = function(err, req, res, next) {
    console.error(err.stack)
    res.status(500).send('Something broke')
}

app.use(errorHandling)
```