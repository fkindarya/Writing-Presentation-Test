# Writing & Presentation Test - Week 8
## MongoDB
### Definisi
- MongoDB adalah salah satu database NoSQL menggunakan dokumen berformat JSON dengan skema opsional.
### Perbedaan SQL dengan NoSQL
- SQL menyimpan data menggunakan relasi tabel, NoSQL menggunakan dokumen dengan format JSON.
### Kelebihan dan Kekurangan NoSQL
#### Kelebihan
- Tidak membutuhkan Tabel.
- Menggunakan JSON sehingga mempermudah integrasi dengan JavScript.
- Performa lebih cepat dengan kemampuan menampung banyak data yang bervariasi.
#### Kekurangan
- Tidak mendukung transaksi.
- Masalah konsistensi data.
- Hanya bisa menampung maksimal 16MB tiap document.
### Anatomi Database MongoDB
- Database adalah wadah unuk menyimpan berbagai macam Collection.
- Collection adalah tempat kumpulan dari berbagai macam document.
- Document adalah data yang disimpan dalam Collection.
### Instalasi
- **Download** [MongoDB Server](https://www.mongodb.com/try/download/community) beserta [MongoDB Compass](https://www.mongodb.com/try/download/compass).
- Setelah proses download dan instalasi selesai, **buka MongoDB Compass**.
- **Klik New Connection** lalu langsung **klik Connect** tanpa merubah URI yang tertera.
- **Klik _MONGOSH** di pojok kiri bawah untuk membuka MongoDB Shell apabila ingin melakukan perintah untuk mengatur database.
- MongoDB siap digunakan.
## Mongoose
### Definisi
- Mongoose adalah library sebagai Object Modelling MongoDB untuk NodeJS.
### Instalasi
- Install Mongoose
    `npm install mongoose`
- Konfigurasi koneksi (buat folder config, didalamnya buat file db.js)
    ```
    const mongoose = require('mongoose')

    const db_url = 'mongodb://localhost:27017/{nama_db}'

    const db = mongoose.connect(db_url)

    module.exports = db
    ```
### Membuat Schema
- Contoh membuat User Schema (buat folder models, didalamnya buat file user.js)
    ```
    const mongoose = require("mongoose");

    const { Schema } = mongoose

    const userSchema = new Schema({
        fullName: String,
        email: {
            type: String,
            required: true
        },
        password: {
            type: String,
            required: true
        }, {
            timestamps: true
        }
    })

    const User = mongoose.model('User', userSchema)

    module.exports = User
    ```
### CRUD Mongoose
- GET data tanpa menampilkan field yang dipilih
    ```
    let getAllUser = async(req, res) => {
        const users = await User.find({}, '-__v -password')

        res.status(200).json(users)
    }

    let getUserByID = async(req, res) => {
        const id = await req.params.id
        const user = await User.findById(id).select("-__v -password")

        res.status(200).json(user)
    }
    ```
- POST data
    ```
    let addUser = (req, res) => {
        const data = req.body
        const user = new User(data)
        user.save()

        res.status(201).json({message: "Data created"})
    }
    ```
- UPDATE data
    ```
    let updateUserByID = async(req, res) => {
        const id = await req.params.id
        const data = await req.body

        await User.updateOne({_id: id}, {
            fullName: data.fullName,
            email: data.email,
            password: data.password
        })
        
        res.status(201).json({message: "Data updated"})
    }
    ```
- DELETE data
    ```
    let updateUserByID = async(req, res) => {
        const id = await req.params.id
        const data = await req.body

        await User.updateOne({_id: id}, {
            fullName: data.fullName,
            email: data.email,
            password: data.password
        })
        
        res.status(201).json({message: "Data updated"})
    }
    ```