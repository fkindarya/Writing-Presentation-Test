# Writing & Presentation Test - Week 7
## MySQL Basic
- **Database** merupakan kumpulan data yang disimpan secara sistematis di dalam komputer yang dapat diolah dan dimanipulasi.
- **Database Management System (DBMS)** merupakan software untuk user berkomunikasi dengan data yang ada dalam media penyimpanan.
- **Tipe utama** pada **DBMS** yaitu :
    - Hierarchical
    - Network
    - Relational
    - Non Relational
    - Object Oriented
- **Table** adalah kumpulan value terbuat dari baris dan kolom yang berisi atribut dari sebuah data.
- **Field** adalah kolom dari sebuah table dengan tiap field memiliki tipe data masing - masing.
- **Record** adalah kumpulan nilai yang saling terkait atau bisa dibilang **isi** dari sebuah table.
- **Structured Query Language (SQL)** merupakan suatu bahasa untuk melakukan interaksi di **Relational Database Management System (RDBMS)**. Interaksi yang dilakukan :
    - Membuat, menampilkan dan menghapus data.
    - Mengatur "Permission".
    - Membuat dan menghapus database.
- **Data Definition Language (DDL)** merupakan kumpulan perintah SQL yang digunakan untuk berinteraksi dengan struktur dan definisi metadata dari objek - objek database.
    - **Membuat table pada database** :
        ```
        CREATE TABLE mahasiswas (
            id int NOT NULL,
            fullName varchar(255) NOT NULL,
            age int,
            PRIMARY KEY (id)
        );
        ```
    - **Alter** digunakan untuk mengubah struktur dari table yang sudah ada. Contoh :
        ```
        Menambah Primary Key

        ALTER TABLE mahasiswas ADD PRIMARY KEY (id)

        Menambah Field

        ALTER TABLE mahasiswas ADD phoneNumber varchar(12)

        Mengubah Struktur Tabel

        ALTER TABLE mahasiswas ALTER COLUMN phoneNumber varchar(13)
        ```
    - **DROP** digunakan untuk menghapus suatu database, table dan view atau index. Contoh :
        ```
        Menghapus Database

        DROP DATABASE data_sma

        Menghapus Table

        DROP TABLE mahasiswas
        ```
- **Data Manipulation Language (DML)** merupakan kumpulan perintah SQL yang digunakan untuk berinteraksi dengan data data yang ada dalam database.
    - **SELECT** digunakan untuk menyeleksi data berdasarkan syarat yang diberikan. Contoh :
        ```
        SELECT * FROM mahasiswas

        SELECT fullName FROM mahasiswas

        SELECT DISTINCT age FROM mahasiswas

        // DISTINCT digunakan untuk menhgilangkan duplikasi dari hasil query.
        ```
    - **INSERT** digunakan untuk menambahkan data pada kolom yang terdapat pada table. Contoh :
        ```
        INSERT INTO mahasiswas VALUES ("Fabyan Kindarya", 21)

        INSERT INTO mahasiswas (fullName, age, phoneNumber) VALUES ("Fabyan Kindarya", 21, "0851xxxxxx74")
        ```
    - **WHERE**, **AND**, **OR**, **NOT**, **LIKE** digunakan untuk memberikan syarat dalam menampilkan data. Contohnya :
        ```
        SELECT fullName, phoneNumber
        FROM mahasiswas
        WHERE id >= 1 AND age >= 21 OR age < 23 NOT id > 4

        SELECT * FROM mahasiswas WHERE fullName LIKE "%ya"
        SELECT * FROM mahasiswas WHERE fullName LIKE "fa%"
        SELECT * FROM mahasiswas WHERE fullName LIKE "%aby%"
        ```
    - **UPDATE** digunakan untuk melakukan perubahan dari kolom yang dipilih. Contoh :
        `UPDATE mahasiswas SET age = 22 WHERE id = 1`
    - DELETE digunakan untuk menghapus data dalam table yang dipilih. Contoh :
        `DELETE FROM mahasiswas WHERE fullName = "Fabyan Kindarya"`