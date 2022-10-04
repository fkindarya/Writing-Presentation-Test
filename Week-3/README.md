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