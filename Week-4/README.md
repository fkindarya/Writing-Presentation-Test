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
## Responsive Web Design
- **Responsive Web Design** (RWD) bertujuan membuat **desain website** kita dapat **diakses** dalam **device apapun** yaitu laptop/PC, smartphone, dan tablet.
    ### Viewport di HTML
    - Menambahkan perintah `<meta name="viewport" content="width=device-width, initial-scale=1.0>"` pada bagian `<head>` html.
    ### Max-Width Element
    - Menambahkan perintah `<img style="max-width: 100%;" src="contoh.png" alt="image">` agar gambar yang ditampilkan menyesuaikan device yang sedang digunakan.
    ### Media Query
    - Media Query umumnya hanya menggunakan 2 jenis, yaitu **_min-width_** dan **_max-width_**.
        ```
        @media screen and (min-width: your pixel){
            // your tag element html and your css
        }

        @media screen and (max-width: your pixel){
            // your tag element html and your css
        }
        ```
    - Terdapat 2 cara dalam menggunakan media query.
        1. Membuat file css berbeda untuk masing - masing device.
            ```
            <link rel="stylesheet" media="screen and (max-width: 500px) href="styles/main.mobile.css">
            ```
        2. Menggabungkan 1 file css untuk setting berbagai device
            ```
            @media screen and (max-width: 500px){
                body {
                    background-color: aquamarine;
                }
            }
            ```
## Bootstrap 5
- **Bootstrap** adalah **framework open source** yang bisa **digunakan** untuk **mengembangkan website**.
- Dengan bootstrap **mempermudah** mengembangkan **website responsive** tanpa perlu coding dari awal.
    ### Layout pada Bootstrap
    - Ada beberapa layout yang dapat digunakan dengan bootstrap.
        #### Breakpoints
        - Bootstrap memiliki 6 breakpoint default yang dapat digunakan.
            ```
            $grid-breakpoints: (
                xs: 0,
                sm: 576px,
                md: 768px,
                lg: 992px,
                xl: 1200px,
                xxl: 1400px
            );
            ```
        #### Containers
        - Container adalah elemen tata letak paling dasar di Bootstrap dan diperlukan saat menggunakan sistem grid.
        - Container digunakan untuk menampung konten di dalamnya.
        - Bootstrap memiliki 3 container, yaitu :
            1. .container, 
            2. .container-fluid
            3. .container-{breakpoint}
            ``` Small   Medium  Large  X-Large
                                X-Small    Small   Medium  Large  X-Large   XX-Large
                                <576px    >=576px >=768px >=992px >=1200px  >=1400px
            .container          100%        540px   720px   960px   1140px  1320px
            .container-sm       100%        540px   720px   960px   1140px  1320px
            .container-md       100%        100%    720px   960px   1140px  1320px
            .container-lg       100%        100%    100%    960px   1140px  1320px
            .container-xl       100%        100%    100%    100%    1140px  1320px 
            .container-xxl      100%        100%    100%    100%    100%    1320px
            .container-fluid    100%        100%    100%    100%    100%    100%
            ```
        #### Grid
        - Sistem grid milik bootstrap menggunakan containers, rows, dan columns untuk menata konten dengan menggunakan flexbox yang speenuhnya responsive.
            ```
            <div class="container">
                <div class="row">
                    <div class="col">
                        Column
                    </div>
                    <div class="col">
                        Column
                    </div>
                    <div class="col">
                        Column
                    </div>
                </div>
            </div>
            ```
    ### Contents pada Bootstrap
    - Ada beberapa content yang dapat digunakan dengan bootstrap.
        #### Typography
        - Headings
            ```
            <h1></h1>
            <h2></h2>
            <h3></h3>
            <h4></h4>
            <h5></h5>
            <h6></h6>
            ```
        - Customize Headings
            ```
            <h3>
                Fancy display heading
                <small class="text-muted">With faded secondary text</small>
            </h3>
            ```
        - Display Headings
            ```
            <h1 class="display-1">Display 1</h1>
            <h1 class="display-2">Display 2</h1>
            <h1 class="display-3">Display 3</h1>
            <h1 class="display-4">Display 4</h1>
            <h1 class="display-5">Display 5</h1>
            <h1 class="display-6">Display 6</h1>
            ```
        - Lead
            ```
            <p class="lead">
                This is a lead paragraph. It stands out from regular paragraphs.
            </p>
            ```
        - Inline Text Elements
            ```
            <p>You can use the mark tag to <mark>highlight</mark> text.</p>
            <p><del>This line of text is meant to be treated as deleted text.</del></p>
            <p><s>This line of text is meant to be treated as no longer accurate.</s></p>
            <p><ins>This line of text is meant to be treated as an addition to the document.</ins></p>
            <p><u>This line of text will render as underlined.</u></p>
            <p><small>This line of text is meant to be treated as fine print.</small></p>
            <p><strong>This line rendered as bold text.</strong></p>
            <p><em>This line rendered as italicized text.</em></p>
            ```
        - Abbreviations
            ```
            <p><abbr title="attribute">attr</abbr></p>
            <p><abbr title="HyperText Markup Language" class="initialism">HTML</abbr></p>
            ```
        - Blockquotes
            ```
            <blockquote class="blockquote">
                <p>A well-known quote, contained in a blockquote element.</p>
            </blockquote>
            ```
        - Naming a Source
            ```
            <figure>
                <blockquote class="blockquote">
                    <p>A well-known quote, contained in a blockquote element.</p>
                </blockquote>
                <figcaption class="blockquote-footer">
                    Someone famous in <cite title="Source Title">Source Title</cite>
                </figcaption>
            </figure>
            ```
        - Alignment
            ```
            <figure class="text-center">
                <blockquote class="blockquote">
                    <p>A well-known quote, contained in a blockquote element.</p>
                </blockquote>
                <figcaption class="blockquote-footer">
                    Someone famous in <cite title="Source Title">Source Title</cite>
                </figcaption>
            </figure>

            <figure class="text-end">
                <blockquote class="blockquote">
                    <p>A well-known quote, contained in a blockquote element.</p>
                </blockquote>
                <figcaption class="blockquote-footer">
                    Someone famous in <cite title="Source Title">Source Title</cite>
                </figcaption>
            </figure>
            ```
        - List
            - Unstyled
                ```
                <ul class="list-unstyled">
                    <li>This is a list.</li>
                    <li>It appears completely unstyled.</li>
                    <li>Structurally, it's still a list.</li>
                    <li>However, this style only applies to immediate child elements.</li>
                    <li>Nested lists:
                        <ul>
                        <li>are unaffected by this style</li>
                        <li>will still show a bullet</li>
                        <li>and have appropriate left margin</li>
                        </ul>
                    </li>
                    <li>This may still come in handy in some situations.</li>
                </ul>
                ```
            - Inline
                ```
                <ul class="list-inline">
                    <li class="list-inline-item">This is a list item.</li>
                    <li class="list-inline-item">And another one.</li>
                    <li class="list-inline-item">But they're displayed inline.</li>
                </ul>
                ```
            - Description List Alignment
                ```
                <dl class="row">
                    <dt class="col-sm-3">Description lists</dt>
                    <dd class="col-sm-9">A description list is perfect for defining terms.</dd>

                    <dt class="col-sm-3">Term</dt>
                    <dd class="col-sm-9">
                        <p>Definition for the term.</p>
                        <p>And some more placeholder definition text.</p>
                    </dd>

                    <dt class="col-sm-3">Another term</dt>
                    <dd class="col-sm-9">This definition is short, so no extra paragraphs or anything.</dd>

                    <dt class="col-sm-3 text-truncate">Truncated term is truncated</dt>
                    <dd class="col-sm-9">This can be useful when space is tight. Adds an ellipsis at the end.</dd>

                    <dt class="col-sm-3">Nesting</dt>
                    <dd class="col-sm-9">
                        <dl class="row">
                            <dt class="col-sm-4">Nested definition list</dt>
                            <dd class="col-sm-8">I heard you like definition lists. Let me put a definition list inside your definition list.</dd>
                        </dl>
                    </dd>
                </dl>
                ```
        #### Images
        - Responsive Images
            `<img src="..." class="img-fluid" alt="...">`
        - Image Thumbnails
            `<img src="..." class="img-thumbnail" alt="...">`
        - Aligning Images
            ```
            <img src="..." class="rounded float-start" alt="...">
            <img src="..." class="rounded float-end" alt="...">

            // Center
            <img src="..." class="rounded mx-auto d-block" alt="...">

            // or

            <div class="text-center">
                <img src="..." class="rounded" alt="...">
            </div>
            ```
        - Pictures
            ```
            <picture>
                <source srcset="..." type="image/svg+xml">
                <img src="..." class="img-fluid img-thumbnail" alt="...">
            </picture>
            ```
        #### Tables
        - Syntax table yang umum digunakan.
            ```
            <table class="table">
                <thead>
                    <tr>
                        <th scope="col">#</th>
                        <th scope="col">First</th>
                        <th scope="col">Last</th>
                        <th scope="col">Handle</th>
                    </tr>
                </thead>
                <tbody>
                    <tr>
                        <th scope="row">1</th>
                        <td>Mark</td>
                        <td>Otto</td>
                        <td>@mdo</td>
                    </tr>
                    <tr>
                        <th scope="row">2</th>
                        <td>Jacob</td>
                        <td>Thornton</td>
                        <td>@fat</td>
                    </tr>
                    <tr>
                        <th scope="row">3</th>
                        <td colspan="2">Larry the Bird</td>
                        <td>@twitter</td>
                    </tr>
                </tbody>
            </table>
            ```
        - Variasi
            ```
            <!-- On tables -->
            <table class="table-primary">...</table>
            <table class="table-secondary">...</table>
            <table class="table-success">...</table>
            <table class="table-danger">...</table>
            <table class="table-warning">...</table>
            <table class="table-info">...</table>
            <table class="table-light">...</table>
            <table class="table-dark">...</table>

            <!-- On rows -->
            <tr class="table-primary">...</tr>
            <tr class="table-secondary">...</tr>
            <tr class="table-success">...</tr>
            <tr class="table-danger">...</tr>
            <tr class="table-warning">...</tr>
            <tr class="table-info">...</tr>
            <tr class="table-light">...</tr>
            <tr class="table-dark">...</tr>

            <!-- On cells (`td` or `th`) -->
            <tr>
            <td class="table-primary">...</td>
            <td class="table-secondary">...</td>
            <td class="table-success">...</td>
            <td class="table-danger">...</td>
            <td class="table-warning">...</td>
            <td class="table-info">...</td>
            <td class="table-light">...</td>
            <td class="table-dark">...</td>
            </tr>
            ```
        - Striped Rows
            ```
            <table class="table table-striped">
                ...
            </table>

            <table class="table table-dark table-striped">
                ...
            </table>
            ```
        - Hoverable Rows
            ```
            <table class="table table-hover">
                ...
            </table>

            <table class="table table-dark table-hover">
                ...
            </table>
            ```
        - Active Tables
            ```
            <table class="table">
                <thead>
                    ...
                </thead>
                <tbody>
                    <tr class="table-active">
                        ...
                    </tr>
                    <tr>
                        ...
                    </tr>
                    <tr>
                        <th scope="row">3</th>
                        <td colspan="2" class="table-active">Larry the Bird</td>
                        <td>@twitter</td>
                    </tr>
                </tbody>
            </table>

            ```
        #### Figures
        - Menampilkan gambar dengan caption disarankan menggunakan figure.
            ```
            <figure class="figure">
                <img src="..." class="figure-img img-fluid rounded" alt="...">
                <figcaption class="figure-caption">A caption for the above image.</figcaption>
            </figure>

            // Caption terletak di kanan
            <figure class="figure">
                <img src="..." class="figure-img img-fluid rounded" alt="...">
                <figcaption class="figure-caption text-end">A caption for the above image.</figcaption>
            </figure>
            ```
    ### Components pada Bootstrap
    - Ada beberapa component yang dapat digunakan dengan bootstrap.
        #### Accordion
        - Membuat tampilan dapat ditampilkan dan di hide.
            ```
            <div class="accordion" id="accordionExample">
                <div class="accordion-item">
                    <h2 class="accordion-header" id="headingOne">
                    <button class="accordion-button" type="button" data-bs-toggle="collapse" data-bs-target="#collapseOne" aria-expanded="true" aria-controls="collapseOne">
                        Accordion Item #1
                    </button>
                    </h2>
                    <div id="collapseOne" class="accordion-collapse collapse show" aria-labelledby="headingOne" data-bs-parent="#accordionExample">
                    <div class="accordion-body">
                        <strong>This is the first item's accordion body.</strong> It is shown by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.
                    </div>
                    </div>
                </div>
                <div class="accordion-item">
                    <h2 class="accordion-header" id="headingTwo">
                    <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseTwo" aria-expanded="false" aria-controls="collapseTwo">
                        Accordion Item #2
                    </button>
                    </h2>
                    <div id="collapseTwo" class="accordion-collapse collapse" aria-labelledby="headingTwo" data-bs-parent="#accordionExample">
                    <div class="accordion-body">
                        <strong>This is the second item's accordion body.</strong> It is hidden by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.
                    </div>
                    </div>
                </div>
                <div class="accordion-item">
                    <h2 class="accordion-header" id="headingThree">
                    <button class="accordion-button collapsed" type="button" data-bs-toggle="collapse" data-bs-target="#collapseThree" aria-expanded="false" aria-controls="collapseThree">
                        Accordion Item #3
                    </button>
                    </h2>
                    <div id="collapseThree" class="accordion-collapse collapse" aria-labelledby="headingThree" data-bs-parent="#accordionExample">
                    <div class="accordion-body">
                        <strong>This is the third item's accordion body.</strong> It is hidden by default, until the collapse plugin adds the appropriate classes that we use to style each element. These classes control the overall appearance, as well as the showing and hiding via CSS transitions. You can modify any of this with custom CSS or overriding our default variables. It's also worth noting that just about any HTML can go within the <code>.accordion-body</code>, though the transition does limit overflow.
                    </div>
                    </div>
                </div>
            </div>
            ```
        #### Alert
        - Variasi
            ```
            <div class="alert alert-primary" role="alert">
                A simple primary alert—check it out!
            </div>
            <div class="alert alert-secondary" role="alert">
                A simple secondary alert—check it out!
            </div>
            <div class="alert alert-success" role="alert">
                A simple success alert—check it out!
            </div>
            <div class="alert alert-danger" role="alert">
                A simple danger alert—check it out!
            </div>
            <div class="alert alert-warning" role="alert">
                A simple warning alert—check it out!
            </div>
            <div class="alert alert-info" role="alert">
                A simple info alert—check it out!
            </div>
            <div class="alert alert-light" role="alert">
                A simple light alert—check it out!
            </div>
            <div class="alert alert-dark" role="alert">
                A simple dark alert—check it out!
            </div>
            ```
        - Alert dengan Close Button
            ```
            <div class="alert alert-warning alert-dismissible fade show" role="alert">
                <strong>Holy guacamole!</strong> You should check in on some of those fields below.
                <button type="button" class="btn-close" data-bs-dismiss="alert" aria-label="Close"></button>
            </div>
            ```
        #### Badges
        - Contoh
            ```
            <span class="badge bg-primary">Primary</span>
            <span class="badge bg-secondary">Secondary</span>
            <span class="badge bg-success">Success</span>
            <span class="badge bg-danger">Danger</span>
            <span class="badge bg-warning text-dark">Warning</span>
            <span class="badge bg-info text-dark">Info</span>
            <span class="badge bg-light text-dark">Light</span>
            <span class="badge bg-dark">Dark</span>
            ```
        #### Breadcrumps
        - Normal
            ```
            <nav aria-label="breadcrumb">
                <ol class="breadcrumb">
                    <li class="breadcrumb-item"><a href="#">Home</a></li>
                    <li class="breadcrumb-item active" aria-current="page">Library</li>
                </ol>
            </nav>
            ```
        - Dividers
            ```
            <nav style="--bs-breadcrumb-divider: '>';" aria-label="breadcrumb">
                <ol class="breadcrumb">
                    <li class="breadcrumb-item"><a href="#">Home</a></li>
                    <li class="breadcrumb-item active" aria-current="page">Library</li>
                </ol>
            </nav>
            ```
        #### Buttons
        - Normal
            ```
            <button type="button" class="btn btn-primary">Primary</button>
            <button type="button" class="btn btn-secondary">Secondary</button>
            <button type="button" class="btn btn-success">Success</button>
            <button type="button" class="btn btn-danger">Danger</button>
            <button type="button" class="btn btn-warning">Warning</button>
            <button type="button" class="btn btn-info">Info</button>
            <button type="button" class="btn btn-light">Light</button>
            <button type="button" class="btn btn-dark">Dark</button>

            <button type="button" class="btn btn-link">Link</button>
            ```
        - Outline
            ```
            <button type="button" class="btn btn-outline-primary">Primary</button>
            <button type="button" class="btn btn-outline-secondary">Secondary</button>
            <button type="button" class="btn btn-outline-success">Success</button>
            <button type="button" class="btn btn-outline-danger">Danger</button>
            <button type="button" class="btn btn-outline-warning">Warning</button>
            <button type="button" class="btn btn-outline-info">Info</button>
            <button type="button" class="btn btn-outline-light">Light</button>
            <button type="button" class="btn btn-outline-dark">Dark</button>
            ```
        #### Button Groups
        - Normal
            ```
            <div class="btn-group" role="group" aria-label="Basic example">
                <button type="button" class="btn btn-primary">Left</button>
                <button type="button" class="btn btn-primary">Middle</button>
                <button type="button" class="btn btn-primary">Right</button>
            </div>
            ```
        - Mixed
            ```
            <div class="btn-group" role="group" aria-label="Basic mixed styles example">
                <button type="button" class="btn btn-danger">Left</button>
                <button type="button" class="btn btn-warning">Middle</button>
                <button type="button" class="btn btn-success">Right</button>
            </div>
            ```
        - Outline
            ```
            <div class="btn-group" role="group" aria-label="Basic outlined example">
                <button type="button" class="btn btn-outline-primary">Left</button>
                <button type="button" class="btn btn-outline-primary">Middle</button>
                <button type="button" class="btn btn-outline-primary">Right</button>
            </div>
            ```
        - Checkbox
            ```
            <div class="btn-group" role="group" aria-label="Basic checkbox toggle button group">
                <input type="checkbox" class="btn-check" id="btncheck1" autocomplete="off">
                <label class="btn btn-outline-primary" for="btncheck1">Checkbox 1</label>

                <input type="checkbox" class="btn-check" id="btncheck2" autocomplete="off">
                <label class="btn btn-outline-primary" for="btncheck2">Checkbox 2</label>

                <input type="checkbox" class="btn-check" id="btncheck3" autocomplete="off">
                <label class="btn btn-outline-primary" for="btncheck3">Checkbox 3</label>
            </div>
            ```
        - Radio
            ```
            <div class="btn-group" role="group" aria-label="Basic radio toggle button group">
                <input type="radio" class="btn-check" name="btnradio" id="btnradio1" autocomplete="off" checked>
                <label class="btn btn-outline-primary" for="btnradio1">Radio 1</label>

                <input type="radio" class="btn-check" name="btnradio" id="btnradio2" autocomplete="off">
                <label class="btn btn-outline-primary" for="btnradio2">Radio 2</label>

                <input type="radio" class="btn-check" name="btnradio" id="btnradio3" autocomplete="off">
                <label class="btn btn-outline-primary" for="btnradio3">Radio 3</label>
            </div>
            ```
        #### Cards
        - Normal
            ```
            <div class="card" style="width: 18rem;">
                <img src="..." class="card-img-top" alt="...">
                <div class="card-body">
                    <h5 class="card-title">Card title</h5>
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                    <a href="#" class="btn btn-primary">Go somewhere</a>
                </div>
            </div>
            ```
        - Title, Text, dan Links
            ```
            <div class="card" style="width: 18rem;">
                <div class="card-body">
                    <h5 class="card-title">Card title</h5>
                    <h6 class="card-subtitle mb-2 text-muted">Card subtitle</h6>
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                    <a href="#" class="card-link">Card link</a>
                    <a href="#" class="card-link">Another link</a>
                </div>
            </div>
            ```
        - Images
            ```
            <div class="card" style="width: 18rem;">
                <img src="..." class="card-img-top" alt="...">
                <div class="card-body">
                    <p class="card-text">Some quick example text to build on the card title and make up the bulk of the card's content.</p>
                </div>
            </div>
            ```
        #### Navbars
        - Contoh
            ```
            <nav class="navbar navbar-expand-lg navbar-light bg-light">
                <div class="container-fluid">
                    <a class="navbar-brand" href="#">Navbar</a>
                    <button class="navbar-toggler" type="button" data-bs-toggle="collapse" data-bs-target="#navbarSupportedContent" aria-controls="navbarSupportedContent" aria-expanded="false" aria-label="Toggle navigation">
                    <span class="navbar-toggler-icon"></span>
                    </button>
                    <div class="collapse navbar-collapse" id="navbarSupportedContent">
                    <ul class="navbar-nav me-auto mb-2 mb-lg-0">
                        <li class="nav-item">
                        <a class="nav-link active" aria-current="page" href="#">Home</a>
                        </li>
                        <li class="nav-item">
                        <a class="nav-link" href="#">Link</a>
                        </li>
                        <li class="nav-item dropdown">
                        <a class="nav-link dropdown-toggle" href="#" id="navbarDropdown" role="button" data-bs-toggle="dropdown" aria-expanded="false">
                            Dropdown
                        </a>
                        <ul class="dropdown-menu" aria-labelledby="navbarDropdown">
                            <li><a class="dropdown-item" href="#">Action</a></li>
                            <li><a class="dropdown-item" href="#">Another action</a></li>
                            <li><hr class="dropdown-divider"></li>
                            <li><a class="dropdown-item" href="#">Something else here</a></li>
                        </ul>
                        </li>
                        <li class="nav-item">
                        <a class="nav-link disabled" href="#" tabindex="-1" aria-disabled="true">Disabled</a>
                        </li>
                    </ul>
                    <form class="d-flex">
                        <input class="form-control me-2" type="search" placeholder="Search" aria-label="Search">
                        <button class="btn btn-outline-success" type="submit">Search</button>
                    </form>
                    </div>
                </div>
            </nav>
            ```