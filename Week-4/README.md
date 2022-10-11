# Writing & Presentation Test - Week 4
## Javascript Intermediate
### Asynchronous - Lanjutan
#### Async - Await & Fetch
- **Async - await** adalah salah satu **fitur baru** dari **javascript** yang digunakan untuk **menangani** hasil dari sebuah **Promise**.
- **Await** berfungsi untuk **menunda** sebuah **kode** dijalankan **sampai** proses **asynchronous berhasil**.
- **Fetch** adalah **native web API** untuk melakukan **HTTP calls** dari external network.
    ```
    let getDataDigimon = asnyc() => {
        let URL = "https://digimon-api.vercel.app/api/digimon";
        let response = await fetch(URL);
        let digimons = await response.json();

        digimons.slice(0, 10).forEach(item => {
            console.log(item);
        });
    }

    getDataDigimon();
    ```
## Git & GitHub Lanjutan
### Git Log
- Perintah `git log` dapat **digunakan** untuk **melihat** catatan log dari **commit** yang pernah **dilakukan**.
- Untuk git log yang lebih pendek, bisa menggunakan perintah `git log --oneline`.
    #### Melihat log menggunakan nomor version - commit.
    ` git log 890d53dfa2d1e2ca7c6fcd684bb1cf0e297daaff`
    #### Melihat log file tertentu
    `git log index.html`
    #### Melihat log berdasarkan author
    `git log --author='Fabyan Kindarya'`
### Membatalkan Perubahan
- Jika perubahan yang sedang dilakukan terjadi kesalahan dan kita ingin mengembalikan keadaan seperti sebelumnya maka dapat dilakukan menggunakan beberapa perintah git.
    #### Kondisi Belum Staged dan Belum Commit
    - Belum di git add.
        `git checkout index.html`
    #### Kondisi Sudah Staged dan Belum Commit
    - Sudah di git add.
        `git reset index.html` lalu melakukan `git checkout index.html`.
    #### Kondisi Sudah Commit
    - Kita bisa mengembalikan commit hanya pada file tertentu.
        `git checkout 890d53dfa2d1e2ca7c6fcd684bb1cf0e297daaff index.html` lalu melakukan `git reset index.html`.
    - Kita bisa mengembalikan commit untuk semua file.
        `git checkout 890d53dfa2d1e2ca7c6fcd684bb1cf0e297daaff`
    - Jika ingin mengembalikan 3 commit sebelumnya
        `git checkout HEAD~3 index.html`
- Git Revert membatalkan semua perubahan yang ada tanpa menghapus commit terakhir. 
    `git revert -n <nomor commit>`
### Git Branch
- Fitur yang WAJIB digunakan jika berkolaborasi dengan developer atau dalam tim. Untuk menghindari conflict code yang dikembangkan, kita tidak boleh berkolaborasi dalam project di satu branch yang sama.
    - Untuk membuat branch, gunakan perintah :
        `git branch <branch>`
    - Melihat list branch, gunakan perintah :
        `git branch`
    - Pindah ke branch tertentu, gunakan perintah :
        `git checkout <branch>` atau `git switch <branch>`
    - Delete branch, gunakan perintah :
        `git branch -d <branch>`
### Git Merge
- Setelah membuat branch baru dan melakukan commit. Saatnya menyatukan pekerjaan ke master file / branch utama. Untuk menyatukan branch yang telah kita buat, gunakan perintah :
    1. `git checkout main`
    2. `git merge <branch>`