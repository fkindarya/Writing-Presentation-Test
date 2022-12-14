# Writing & Presentation Test - Week 3
## Javascript Intermediate
### Array
- **Array** adalah **tipe data list order** yang dapat **menyimpan berbagai tipe data** baik **String, Number, Boolean, dan lainnya** di dalamnya.
    ```
    let hewanKarnivora = [
        'Beruang',
        'Singa',
        'Macan'
    ];

    console.log(hewanKarnivora);
    ```
    ```
    let randomData = [
        'String',
        15,
        true,
    ];

    console.log(randomData);
    ```
    #### Membuat Array
    - Array **didefinisikan** menggunakan **square brackets** `[]`.
    #### Mengakses / Memanggil Array
    - Array **dimulai** dari **index** data **ke-0**.
        ```
        let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
        console.log(kota[0]); // Sidoarjo
        console.log(kota[1]); // Surabaya
        console.log(kota[2]); // Mojokerto
        ```
    #### Update Array
    ```
    let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
    kota[0] = 'Madiun';
    console.log(kota); // ['Madiun', 'Surabaya', 'Mojokerto']
    ```
    #### Array Properties
    - **Properties** adalah **fitur** yang sudah **disediakan** oleh **Javascipt** untuk **mempermudah developer**.
    - Array memiliki **5 properti** yaitu **constructor**, **length**, **index**, **input**, dan **prototype**.
        ##### Length
        - Mengembalikan **nilai** dari **jumlah panjang** data suatu **array**.
            ```
            let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
            console.log(kota.length); // Output: 3
            ```
    #### Array Method
    - Array memiliki **_built-in methods_** yang artinya **Javascript** sudah **menyediakan** **function** atau **method umum** yang bisa **digunakan**.
        ##### Push
        - Menambahkan item Array pada urutan yang paling akhir
        ```
        let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
        kota.push('Madiun');
        console.log(kota); // ['Sidoarjo', 'Surabaya', 'Mojokerto', 'Madiun']
        ```
        ##### Pop
        - Menghapus item Array index terakhir.
        ```
        let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
        kota.pop();
        console.log(kota); // ['Sidoarjo', 'Surabaya']
        ```
        ##### Shift
        - Menghapus item Array index pertama.
        ```
        let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
        kota.shift();
        console.log(kota); // ['Surabaya', 'Mojokerto']
        ```
        ##### Unshift
        - Menambahkan item Array pada index pertama.
        ```
        let kota = ['Sidoarjo', 'Surabaya', 'Mojokerto'];
        
        kota.unshift('Malang');
        console.log(kota); // ['Malang', 'Sidoarjo', 'Surabaya', 'Mojokerto']
        ```
        ##### Sort
        - Mengurutkan seacara Ascending atau Descending Alphanumeric.
        ```
        const numbers = [1, 9, 4, 5, 6];

        numbers.sort();
        console.log(numbers); // [1, 4, 5, 6, 9]
    #### Looping pada Array
    - Array memiliki **built-in methods** untuk melakukan **looping** yaitu **foreach()** dan **map()**.
        ##### ForEach
        - Melakukan looping pada setiap elemen array.
        ```
        const cumiDarat = ['Fortuner', 'Pajero', 'Innova'];

        cumiDarat.forEach(cumi => {
            console.log(cumi);
        });
        // Output: Fortuner, Pajero, Innova
        ```
        ##### Map
        - Melakukan looping dengan membuat array baru.
        ```
        let desimal = [0.1, 0.2, 0.3];

        let persen = desimal.map(angka => {
            return angka * 100 + "%";
        });

        console.log(persen);
        // Output: 10%, 20%, 30%
        ```
### Multidimensional Array
- disebut juga dengan **Array of Array**.
    ```
    let topSpeedMobil = [
        ['Innova', 180],
        ['Pajero', 190],
        ['Fortuner', 210]
    ];

    console.log(topSpeedMobil);
    ```
    #### Looping Multidimensional Array
    ##### ForEach
    ```
    let topSpeedMobil = [
        ['Innova', 180],
        ['Pajero', 190],
        ['Fortuner', 210]
    ];

    topSpeedMobil.forEach((baris) => {
        baris.forEach((kolom) => {
            console.log(kolom);
        });
    });

    // Output
    // Innova
    // 180
    // Pajero
    // 190
    // Fortuner
    // 210
    ```
    ##### Map
    ```
    let topSpeedMobil = [
        ['Innova', 180],
        ['Pajero', 190],
        ['Fortuner', 210]
    ];

    let kiloMeter = topSpeedMobil.map(akselerasi => {
        akselerasi[1] = akselerasi[1] + " km";
        return akselerasi;
    });

    console.log(kiloMeter);
    // Output: (3) [Arrray(2), Arrray(2), Arrray(2)]
    // 0: (2) ["Innova", "180 km"]
    // 1: (2) ["Pajero", "190 km"]
    // 2: (2) ["Fortuner", "210 km"]
    ```
### Object
- **Object** adalah sebuah **tipe data** pada variabel yang menyimpan **properti** dan **method**.
- **Properti** adalah **data lengkap** dari sebuah object.
- **Method** adalah **action** dari sebuah object.
    #### Membuat Sebuah Object
    - Object dapat diassign kedalam sebuah variabel.
        `let person = {}`
    - Sama seperti array, object dapat menyimpan properti dengan tipe data apapun.
        ```
        let person = {
            name: 'Fabyan',
            age: 21,
            isHandsome: true,
        };
        ```
    - Gunakan single quote pada key jika menggunakan spasi.
        ```
        let person = {
            name: 'Fabyan',
            age: 21,
            isHandsome: true,
            'current address': 'Sidoarjo',
        };
        ```
    #### Mengakses Object dan Property Object
    - Mengakses seluruh object.
        ```
        let person = {
            name: 'Fabyan',
            age: 21,
            isHandsome: true,
        };

        console.log(person); // Output: {name: 'Fabyan', age: 21, isHandsome: true}
        ```
    - Mengakses properti object.
        ```
        let person = {
            name: 'Fabyan',
            age: 21,
            isHandsome: true,
            'current address': 'Sidoarjo',
        };

        console.log(person.name); // Output: Fabyan
        ```
    - Mengakses properti object dengan bracket notation.
        ```
        let person = {
            name: 'Fabyan',
            age: 21,
            isHandsome: true,
            'current address': 'Sidoarjo',
        };

        console.log(person['age']); // Output: 21
        console.log(person['current address']); // Output: Sidoarjo
        ```
    #### Update Object
    - Object dapat **mengupdate** value dari key yang sudah tersedia.
    - Object dapat **menambahkan** key dan value baru.
        ```
        let person = {
            name: 'Fabyan',
            age: 21,
            isHandsome: true,
        };

        //mengupdate value dari key
        person.age = 20;

        //menambahkan key dan value baru
        person.city = 'Sidoarjo';

        console.log(person); // Output: {name: 'Fabyan', age: 20, isHandsome: true, city: 'Sidoarjo'}
        ```
    #### Delete Object Property
    - Menghapus properti dari object menggunakan **delete** operator.
        ```
        let person = {
            name: 'Fabyan',
            age: 20,
            isHandsome: true,
            city: 'Sidoarjo',
        };

        delete person.isHandsome;

        console.log(person); // Output: {name: 'Fabyan', age: 20, city: 'Sidoarjo'}
        ```
    #### Method
    - Jika **value** yang ada pada property berupa **function** maka itu disebut **method**.
        ```
        let greeting = {
            welcome: function () {
                return 'Halo selamat berbelanja';
            },

            exit: function () {
                return 'Terima kasih silahkan datang kembali';
            }
        };

        console.log(greeting.welcome()); // Output: 'Halo selamat berbelanja'
        ```
    #### Nested Object
    - **Nested Object** adalah object yang berasal dari **turunan object** lainnya.
        ```
        let book = {
            title: 'Rich Dad Poor Dad'
            description: 'Rich Dad Poor Dad is a 1997 book.'
            author: {
                people: {
                    name: 'Robert Kiyosaki',
                    age: 75,
                    nationality: 'Japanese',
                }
            }
        };

        console.log(book.title) // Output: Rich Dad Poor Dad
        console.log(book.author.people.name) // Output: Robert Kiyosaki
        ```
    #### Looping Object
    - Menampilkan seluruh object properti dapat dilakukan menggunakan looping.
        ```
        for(let key in object){
            // ..
        }
        ```
        Contoh :
        ```
        let book = {
            title: 'Rich Dad Poor Dad'
            description: 'Rich Dad Poor Dad is a 1997 book.'
            author: {
                people: {
                    name: 'Robert Kiyosaki',
                    age: 75,
                    nationality: 'Japanese',
                }
            }
        };

        for(let key in book){
            console.log(book[key])
        };
        // Output: 
        // Rich Dad Poor Dad
        // Rich Dad Poor Dad is a 1997 book
        // people {...}

        for(let key in book.author.people){
            console.log(book.auhtor.people[key])
        }
        // Output:
        // Robert Kiyosaki
        // 75
        // Japanese
        ```
    #### Array Of Object
    ```
    let users = [
        {
            name: 'Fabyan',
            age: 21,
            city: 'Sidoarjo',
        },
        {
            name: 'Kindarya',
            age: 20,
            city: 'Sidoarjo',
        },
        {
            name: 'Pimiming',
            age: 19,
            city: 'Surabaya',
        }
    ];

    let listUser = users.map(user => {
        return user;
    });

    console.log(listUser);
    // Output:
    // {name: 'Fabyan', age: 21, city: 'Sidoarjo'}
    // {name: 'Kindarya', age: 20, city: 'Sidoarjo'}
    // {name: 'Pimiming', age: 19, city: 'Surabaya'}
    ```
### Modules
- **Modules** adalah **reusable code** yang dapat di **export** dari suatu file javascript dan di **import** ke file javascript yang lain.
- **Reusable Code** adalah data yang dapat digunakan berulang kali.
- **Data** yang dapat di **export** adalah **string**, **object**, **array**, **number**, **class**, hingga **method**.
    #### Membuat Modules
    1. Menambahkan **script attribute type** untuk modules pada file HTML.
        ```
        index.html
        ----------

        <!DOCTYPE html>
        <html lang="en">
        <head>
            <meta charset="UTF-8">
            <meta name="viewport" content="width=device-width, initial-scale=1.0">
        </head>
        <body>
            <script type="module" src="script.js"></script>
        </body>
        </html>
        ```
    2. Membuat javascript untuk melakukan export
        ```
        greetings.js
        ------------

        let shopName = 'Pimiming Garage';

        function welcome(){
            alert("Hello, Welcome to our Shop");
        }

        function exit(name){
            alert(`Thank you for your purchase ${name}`);
        }

        export {
            welcome as greet,
            exit,
        };
        ```
    3. Melakukan import pada file javascript utama
        ```
        script.js
        ---------

        import {
            greet,
            exit as goodBye,
        } from 'greetings.js';

        welcome(); // Output: Hello, Welcome to our Shop
        goodBye('Fabyan); // Output: Thank you for your purchase Fabyan
        ```
    #### Export Default
    - Export default dilakukan jika hanya **1 data** yang di **export**.
        ```
        greetings.js
        -------------

        let sayThanks = () => {
            alert("Thank You, Have a Great Day");
        }

        export default sayThanks;

        script.js
        ---------

        import sayThanks from 'greetings.js';

        sayThanks(); // Output: Thank You, Have a Great Day
        ```
### Recursive
- **Recursive** adalah **function** yang **memanggil dirinya sendiri** sampai kondisi tertentu.
- Recursive biasa **digunakan** untuk **menyelesaikan** permasalahan matematika, fisika, kimia, dan yang **berhubungan** dengan **calculation**.
    #### Struktur Recursive
    ```
    function recursive() {
        // ...
        recursive();
        // ...
    }
    ```
    - Recursive akan berhenti memanggil dirinya sendiri jika kondisi terpenuhi
        ```
        function recursive() {
            if(condition) {
                // stop calling itself
                // ...
            } else {
                recursive();
            }
        }
        ```
    #### Ciri dari Recursive
    1. Base Case, memiliki kondisi yang menyatakan kapan fungsi tersebut berhenti. Kondisi ini harus dapat dibuktikan akan tercapai, karena jika tidak tercapai maka kita tidak dapat membuktikan bahwa fungsi akan berhenti.
    2. Recursive Case, fungsi memanggil dirinya sendiri sambil mengurangi atau memecahkan data masukan setiap panggilannya.
    #### Contoh Kasus Recursive
    1. Menghitung Mundur Number
        ```
        function countDown(fromNumber) {
            console.log(fromNumber);

            let nextNumber = fromNumber - 1;

            if (nextNumber > 0) {
                countDown(nextNumber);
            }
        }

        countDown(3);
        // Output:
        // 3
        // 2
        // 1
        ```
    2. Mencari Hasil dari Nilai Pangkat
        ```
        function pow(x, n) {
            if (n == 1) {
                return x;
            } else {
                return x * pow(x, n - 1);
            }
        }

        pow(2, 3); // Output: 8
        ```
### Asynchronous
- Javascript adalah bahasa pemrograman **single-thread** yang artinya hanya dapat **mengeksekusi** satu task pada satu waktu atau biasa disebut **synchronous**.
- **Asynchronous** mengizinkan komputer memproses **task yang lain sambil menunggu proses yang masih berlangsung**.
- Kita dapat membuat **asynchronous** secara **simulasi** pada javascript dengan :
    1. **Callback**
    2. **Promises**
    3. **Async / Await**
    #### Callback
    - **Callback function** adalah function yang kita letakkan di dalam argumen / parameter pada function, dan function tersebut akan dieksekusi setelah function pertama menyelesaikan tugasnya.
        ```
        cons addFunction = (number1, number2, callBack) => {
            console.log(number1 + number2);
            callBack();
        }

        const finishProcess = () => {
            console.log('Done !');
        }

        addFunction(1, 2, finishProcess); 
        // Output: 
        // 3 
        // Done !
        ```
    - Proses asynchronous identik dengan **delay**, dimana hasil dari proses tersebut membutuhkan **selang waktu tertentu** untuk menghasilkan output.
    - Kita akan menemukan proses asynchronous pada proses **Ajax**, **komunikasi HTTP**, **Operasi file**, **timer**, dsb.
    - Contoh program synchronous :
        ```
        let nama = () => {
            console.log('Halo nama saya Fabyan');
        }

        let umur = () => {
            console.log('umur saya 21');
        }

        let kota = () => {
            console.log('saya tinggal di Sidoarjo');
        }

        nama();
        umur();
        kota();

        // Output:
        // Halo nama saya Fabyan
        // umur saya 21
        // saya tinggal di Sidoarjo
        ```
    - Pada asynchronous kita menggunakan **_setTimeout_** untuk simulasinya. Proses pada umur() kita lewati sambil menunggu selesai, program lanjut ke function kota().
        ```
        let nama = () => {
            console.log('Halo nama saya Fabyan');
        }

        let umur = () => {
            setTimeout(() => {
                console.log('umur saya 21');
            }, 3000)
        }

        let kota = () => {
            nama();
            umur();
            console.log('saya tinggal di Sidoarjo');
        }

        kota();

        // Output:
        // Halo nama saya Fabyan
        // saya tinggal di Sidoarjo
        // umur saya 21
        ```
    #### Promises
    - **Promise** merupakan salah satu fitur baru di **ES6**, biasa digunakan untuk melakukan **http request** / **fetch data** dari **API**.
    - Dalam pengambilan data, promise memiliki 3 kemungkinan state, yaitu :
        1. Pending
        2. Fulfilled
        3. Rejected
        ```
        let nontonFilm = () => {
            new Promise((resolve, reject) => {
                let condition = true;

                if(condition){
                    resolve('Jadi nonton film')
                } else {
                    reject('Tidak jadi nonton film')
                }
            })
            .then(result => console.log(result))
            .catch(error => console.log(error))
        }

        nontonFilm() // Output: Jadi nonton film
        ```
### Web Storage
- **Web Storage** digunakan untuk **menyimpan data pengguna** seperti pencarian, artikel berita, dan lain-lain ke lokal (browser) menggunakan **cookies**, **local storage**, dan **session storage**. Data ini dimanfaatkan oleh situs web tersebut untuk **merekam kebiasaan pengguna** agar dapat **memberikan rekomendasi** sesuai kebiasaan pengguna tersebut.
    #### Cookies
    - Maksimum data yang dapat disimpan adalah 4 KB.
    - Setiap kita mengakses situs web, cookies juga kembali dikirim sehingga memperlambat aplikasi web kamu dengan mengirimkan data yang sama.
    - Cookies disertakan pada setiap _HTTP request_, sehingga mengirimkan data yang tidak dienkripsi melalui internet, maka saat kita ingin menyimpan data dalam cookies kita harus mengenkripsinya terlebih dahulu.
    - Cookies memiliki tanggal kadaluarsa. Tanggal ini telah ditentukan sehingga _web browser_ bisa menghapus cookies jika tanggal sudah kadaluarsa atau tidak dibutuhkan.
    #### Local Storage
    - Menyimpan data tanpa tanggal kadaluarsa.
    - Data tidak akan dihapus ketika _web browser_ ditutup dan akan tersedia seterusnya selama kita tidak menghapus _data local storage_ pada _web browser_.
    - Dapat menyimpan data hingga 5 MB.
    - Hanya dapat menyimpan data _string_.
        ##### Menyimpan Data
        - Untuk menyimpan data pada _local storage_ menggunakan method :
            ```
            localStorage.setItem('key', value);
            ```
        ##### Mengambil Data
        - Untuk mengambil data pada _local storage_ menggunakan method :
            ```
            localStorage.getItem('key');
            ```
        ##### Menghapus Data
        - Untuk menghapus data pada _local storage_ menggunakan method :
            ```
            // Menghapus key tertentu
            localStorage.removeItem('key');

            // Menghapus semua key
            localStorage.clear();
            ```
    #### Session Storage
    - Data yang disimpan pada _session storage_ akan terus tersimpan selama _browser_ terbuka dan tidak hilang jika laman di-reload.
    - Membuka banyak tab/window dengan _URL_ yang sama, akan menciptakan _session storage_ yang berbeda di masing-masing _tab/window_.
    - Menutup _tab/window_ akan mengakhiri _session_ dan menghapus data yang tersimpan di _session storage_ pada _tab/window_ tersebut.
    - Dapat menyimpan data hingga 5 MB.
    - Hanya dapat menyimpan data _string_.
        ##### Menyimpan Data
        - Untuk menyimpan data pada _session storage_ menggunakan method :
            ```
            sessionStorage.setItem('key', value);
            ```
        ##### Mengambil Data
        - Untuk mengambil data pada _session storage_ menggunakan method :
            ```
            sessionStorage.getItem('key');
            ```
        ##### Menghapus Data
        - Untuk menghapus data pada _session storage_ menggunakan method :
            ```
            // Menghapus key tertentu
            sessionStorage.removeItem('key');

            // Menghapus semua key
            sessionStorage.clear();
            ```