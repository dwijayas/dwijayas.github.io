---
layout: post
category : tutorial
tagline: 
tags : [pengantar, pemula, jekyll]
---
{% include JB/setup %}

Pengenalan Jekyll ini akan menguraikan secara spesifik apa itu Jekyll dan mengapa Anda ingin menggunakannya.
Langsung mengikuti intro kita akan belajar persis _bagaimana_ Jekyll melakukan apa yang dilakukannya.

## Ringkasan

### Apa itu Jekyll?

Jekyll adalah mesin pengurai yang dibundel sebagai permata ruby ​​yang digunakan untuk membangun situs web statis dari
komponen dinamis seperti template, parsial, kode cair, penurunan harga, dll. Jekyll dikenal sebagai "generator situs statis yang sederhana, sadar blog".

### Contoh

Website ini dibuat dengan Jekyll. [Situs Jekyll lainnya](https://github.com/mojombo/jekyll/wiki/Sites).

### Apa yang Jekyll Lakukan?

Jekyll adalah permata ruby yang Anda instal di sistem lokal Anda.
Sesampai di sana Anda dapat menelepon `jekyll --server` pada direktori dan menyediakan direktori itu
diatur dengan cara yang diharapkan jekyll, itu akan melakukan hal-hal ajaib seperti mengurai file penurunan harga/tekstil,
menghitung kategori, tag, permalink, dan membuat halaman Anda dari template tata letak dan sebagian.

Setelah diurai, Jekyll menyimpan hasilnya dalam folder `_site` statis mandiri.
Tujuannya di sini adalah Anda dapat menyajikan semua konten dalam folder ini secara statis dari server web statis biasa.

Anda dapat menganggap Jekyll sebagai blog dinamis normal, tetapi tidak menguraikan konten, template, dan tag
pada setiap permintaan, Jekyll melakukan ini sekali _beforehand_ dan menyimpan _seluruh situs web_ di dalam folder untuk disajikan secara statis.

### Jekyll Bukan Software Blogging

**Jekyll adalah mesin pengurai.**

Jekyll tidak datang dengan konten apapun juga tidak memiliki template atau elemen desain.
Ini adalah sumber kebingungan yang umum saat memulai.
Jekyll tidak datang dengan apa pun yang benar-benar Anda gunakan atau lihat di situs web Anda - Anda harus membuatnya.

### Mengapa Saya Harus Peduli?

Jekyll sangat minimalis dan sangat efisien.
Hal yang paling penting untuk disadari tentang Jekyll adalah bahwa Jekyll menciptakan representasi statis dari situs web Anda yang hanya membutuhkan server web statis.
Blog dinamis tradisional seperti Wordpress memerlukan database dan kode sisi server.
Blog dinamis yang banyak diperdagangkan harus menggunakan lapisan caching yang pada akhirnya melakukan pekerjaan yang sama seperti yang ditetapkan Jekyll; menyajikan konten statis.

Oleh karena itu jika Anda ingin menjaga hal-hal sederhana dan Anda lebih suka baris perintah daripada UI panel admin, cobalah Jekyll.

**Pengembang menyukai Jekyll karena kami dapat menulis konten seperti kami menulis kode:**

- Kemampuan untuk menulis konten dalam penurunan harga atau tekstil di editor teks favorit Anda.
- Kemampuan untuk menulis dan melihat pratinjau konten Anda melalui localhost.
- Tidak diperlukan koneksi internet.
- Kemampuan untuk mempublikasikan melalui git.
- Kemampuan untuk meng-host blog Anda di server web statis.
- Kemampuan untuk menghosting secara bebas di Halaman GitHub.
- Tidak diperlukan basis data.

# Bagaimana Jekyll Bekerja

Berikut ini adalah garis besar lengkap namun ringkas tentang cara kerja Jekyll.

Sadarilah bahwa konsep inti diperkenalkan secara berurutan tanpa contoh kode.
Informasi ini tidak dimaksudkan untuk secara khusus mengajarkan Anda bagaimana melakukan sesuatu, melainkan
dimaksudkan untuk memberi Anda _gambaran lengkap_ relatif terhadap apa yang terjadi di dunia Jekyll.

Mempelajari konsep-konsep inti ini akan membantu Anda menghindari frustrasi umum dan pada akhirnya
membantu Anda lebih memahami contoh kode yang terdapat di seluruh Jekyll-Bootstrap.

## Pengaturan awal

Setelah [menginstal jekyll](/index.html#start-now) Anda harus memformat direktori situs web Anda dengan cara yang diharapkan jekyll.
Jekyll-bootstrap dengan mudah menyediakan format direktori dasar.

### Format Basis Aplikasi Jekyll

Jekyll mengharapkan direktori situs web Anda ditata seperti ini:
    .
    |-- _config.yml
    |-- _includes
    |-- _layouts
    |   |-- default.html
    |   |-- post.html
    |-- _posts
    |   |-- 2011-10-25-open-source-is-good.markdown
    |   |-- 2011-04-26-hello-world.markdown
    |-- _site
    |-- index.html
    |-- assets
        |-- css
            |-- style.css
        |-- javascripts


- **\_config.yml**
	Menyimpan data konfigurasi.

- **\_includes**
	Folder ini untuk tampilan sebagian.

- **\_layouts**
	Folder ini untuk template utama yang akan dimasukkan konten Anda.
	Anda dapat memiliki tata letak yang berbeda untuk halaman atau bagian halaman yang berbeda.

- **\_posts**
	Folder ini berisi konten/posting dinamis Anda.
	Format penamaan harus`@YEAR-MONTH-DATE-title.MARKUP@`.

- **\_site**
	Di sinilah situs yang dihasilkan akan ditempatkan setelah Jekyll selesai mengubahnya.

- **assets**
	Folder ini bukan bagian dari struktur jekyll standar.
	Folder aset mewakili folder _semua generik_ yang kebetulan Anda buat di direktori root Anda.
	Direktori dan file yang tidak diformat dengan benar untuk jekyll tidak akan tersentuh untuk Anda layani secara normal.

(Baca selengkapnya:<https://github.com/mojombo/jekyll/wiki/Usage>)


### Konfigurasi Jekyll

Jekyll mendukung berbagai opsi konfigurasi yang dijelaskan sepenuhnya di sini:
(<https://github.com/mojombo/jekyll/wiki/Configuration>)

## Konten di Jekyll

Konten di Jekyll adalah postingan atau halaman.
"Objek" konten ini dimasukkan ke dalam satu atau lebih templat untuk membuat hasil akhir untuk halaman statis masing-masing.

### Postingan dan Halaman

Posting dan halaman harus ditulis dalam penurunan harga, tekstil, atau HTML dan mungkin juga mengandung sintaks template Liquid.
Posting dan halaman dapat memiliki meta-data yang ditetapkan pada basis per halaman seperti judul, jalur url, serta meta-data kustom arbitrer.

### Bekerja Dengan Posting

**Membuat Postingan**
Postingan dibuat dengan memformat file dengan benar dan menempatkannya di folder `_posts`.

**Memformat**
Sebuah posting harus memiliki nama file yang valid dalam formulir `YEAR-MONTH-DATE-title.MARKUP` dan ditempatkan di direktori `_posts`.
Jika format data tidak valid, Jekyll tidak akan mengenali file tersebut sebagai kiriman. Tanggal dan judul secara otomatis diurai dari nama file dari file posting.
Selain itu, setiap file harus memiliki [YAML Front-Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter) ditambahkan ke isinya.
YAML Front-Matter adalah sintaks YAML yang valid yang menentukan meta-data untuk file yang diberikan.

**Memesan**
Pemesanan adalah bagian penting dari Jekyll tetapi sulit untuk menentukan strategi pemesanan khusus.
Hanya urutan kronologis dan kronologis terbalik yang didukung di Jekyll.

Karena tanggal dikodekan ke dalam format nama file, untuk mengubah urutannya, Anda harus mengubah tanggal dalam nama file.

**Tag**
Postingan dapat memiliki tag yang terkait dengannya sebagai bagian dari meta-datanya.
Tag dapat ditempatkan pada postingan dengan menyediakannya di bagian depan YAML postingan.
Anda memiliki akses ke tag khusus posting di template. Tag ini juga ditambahkan ke koleksi seluruh situs.

**Kategori**
Postingan dapat dikategorikan dengan menyediakan satu atau lebih kategori di bagian depan YAML.
Kategori menawarkan lebih banyak signifikansi daripada tag karena dapat dicerminkan di jalur URL ke pos yang diberikan.
Catat kategori di Jekyll bekerja dengan cara tertentu.
Jika Anda mendefinisikan lebih dari satu kategori, Anda mendefinisikan "set" hierarki kategori.
Contoh:

    ---
    title :  Hello World
    categories : [lessons, beginner]
    ---

Ini mendefinisikan hierarki kategori "lessons/beginner". Perhatikan ini adalah _one category_ node di Jekyll.
Anda tidak akan menemukan "pelajaran" dan "pemula" sebagai dua kategori terpisah kecuali jika Anda mendefinisikannya di tempat lain sebagai kategori tunggal.

### Bekerja Dengan Halaman

**Membuat Halaman**
Halaman dibuat dengan memformat file dengan benar dan menempatkannya di mana saja di direktori root atau subdirektori yang _tidak_ dimulai dengan garis bawah.

**Memformat**
Untuk mendaftar sebagai halaman Jekyll, file harus berisi: [YAML Front-Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter).
Mendaftarkan sebuah halaman berarti 1) bahwa Jekyll akan memproses halaman tersebut dan 2) bahwa objek halaman akan tersedia di `site.pages` array untuk dimasukkan ke dalam template Anda.

**Kategori dan Tag**
Halaman tidak menghitung kategori atau tag sehingga mendefinisikannya tidak akan berpengaruh.

**Sub-Direktori**
Jika halaman ditentukan dalam sub-direktori, jalur ke halaman tersebut akan tercermin dalam url.
Contoh:

    .
    |-- people
        |-- bob
            |-- essay.html

Halaman ini akan tersedia di `http://yourdomain.com/people/bob/essay.html`


**Halaman yang direkomendasikan**

- **index.html**
  Anda akan selalu ingin menentukan halaman root index.html karena ini akan ditampilkan pada URL root Anda.
- **404.html**
  Buat halaman root 404.html dan GitHub Pages akan menyajikannya sebagai respons 404 Anda.
- **sitemap.html**
  Membuat peta situs adalah praktik yang baik untuk SEO.
- **about.html**
  Halaman yang bagus tentang mudah dilakukan dan memberikan perspektif manusia ke situs web Anda.


## Template di Jekyll

Template digunakan untuk memuat konten halaman atau postingan.
Semua template memiliki akses ke variabel objek situs global: `site` serta variabel objek halaman: `halaman`.
Variabel situs menampung semua konten dan metadata yang dapat diakses relatif terhadap situs.
Variabel halaman menyimpan data yang dapat diakses untuk halaman atau postingan yang diberikan pada saat itu.

**Buat Template**
Template dibuat dengan memformat file dengan benar dan menempatkannya di direktori `_layouts`.

**Memformat**
Template harus dikodekan dalam HTML dan berisi YAML Front Matter.
Semua template dapat berisi kode Liquid untuk bekerja dengan data situs Anda.

**Rending Halaman/Konten Postingan dalam Template**
Ada variabel khusus di semua template bernama : `content`.
Variabel `konten` menampung konten halaman/posting termasuk konten sub-templat yang telah ditentukan sebelumnya.
Render variabel konten di mana pun Anda ingin konten utama Anda disuntikkan ke dalam template Anda:

{% capture text %}...
<body>
  <div id="sidebar"> ... </div>
  <div id="main">
    |.{content}.|
  </div>
</body>
...{% endcapture %}
{% include JB/liquid_raw %}

### Sub-Templat

Sub-templat persis templat dengan satu-satunya perbedaan adalah mereka
tentukan tata letak/templat "root" lain di dalam YAML Front Matter mereka.
Ini pada dasarnya berarti sebuah template akan dirender di dalam template lain.

### Termasuk
Di Jekyll Anda dapat menentukan file include dengan menempatkannya di folder `_includes`.
Termasuk BUKAN template, melainkan hanya cuplikan kode yang disertakan ke dalam template.
Dengan cara ini, Anda dapat memperlakukan kode di dalamnya termasuk seolah-olah itu asli dari templat induk.

Setiap kode template yang valid dapat digunakan dalam include.


## Menggunakan Cairan untuk Templat

Templating mungkin adalah bagian Jekyll yang paling membingungkan dan membuat frustrasi.
Hal ini terutama disebabkan oleh fakta bahwa templat Jekyll harus menggunakan Liquid Templating Language.

### Apa Itu Liquid?

[Liquid](https://github.com/Shopify/liquid) adalah bahasa templating aman yang dikembangkan oleh [Shopify](http://shopify.com).
Liquid dirancang untuk pengguna akhir untuk dapat mengeksekusi logika dalam file template tanpa memaksakan risiko keamanan apa pun pada server hosting.

Jekyll menggunakan Liquid untuk menghasilkan konten posting dalam struktur tata letak halaman akhir dan sebagai antarmuka utama untuk bekerja dengan
data situs dan posting/halaman Anda.

### Mengapa Kita Harus Menggunakan Cairan?

GitHub menggunakan Jekyll untuk memberi daya [GitHub Pages](http://pages.github.com/).
GitHub tidak mampu menjalankan kode arbitrer di server mereka sehingga mereka mengunci pengembang melalui Liquid.

### Liquid Tidak Ramah Programmer.

Cerpen Liquid bukan kode nyata dan tidak dimaksudkan untuk mengeksekusi kode nyata.
Intinya adalah Anda tidak dapat melakukan omong kosong dalam Liquid yang belum diizinkan secara eksplisit oleh implementasi.
Terlebih lagi Anda hanya dapat mengakses struktur data yang telah secara eksplisit diteruskan ke template.

Dalam kasus Jekyll, tidak mungkin mengubah apa yang diteruskan ke Liquid tanpa meretas permata atau menjalankan plugin khusus.
Keduanya tidak dapat didukung oleh GitHub Pages.

Sebagai seorang programmer - ini sangat membuat frustrasi.

Tapi daripada melihat kuda hadiah di mulut kita akan
menyedotnya dan melihatnya sebagai peluang untuk mengatasi keterbatasan dan mengadopsi solusi sisi klien jika memungkinkan.

**Ke samping**
Sikap pribadi saya adalah untuk tidak menginvestasikan waktu mencoba meretas cairan. Ini benar-benar tidak perlu
_dari sudut pandang pemrogram_. Artinya jika Anda memiliki kemampuan untuk menjalankan plugin khusus (yaitu menjalankan kode Ruby arbitrer)
Anda lebih baik bertahan dengan ruby. Untuk tujuan itu saya telah membangun [Mustache-with-Jekyll](http://github.com/plusjade/mustache-with-jekyll)

## Aset Statis

Aset statis adalah file apa pun di root atau subfolder yang tidak digarisbawahi yang bukan halaman.
Artinya, mereka tidak memiliki YAML Front Matter yang valid dan karenanya tidak diperlakukan sebagai Halaman Jekyll.

Aset statis harus digunakan untuk file gambar, css, dan javascript.

## Bagaimana Jekyll Mem-parsing File

Ingat Jekyll adalah mesin pengolah. Ada dua jenis utama parsing di Jekyll.

- **Penguraian konten.**
Ini dilakukan dengan tekstil atau penurunan harga.
- **Penguraian template.**
  Ini dilakukan dengan bahasa templating cair.

Dan dengan demikian ada dua jenis format file utama yang diperlukan untuk penguraian ini.

- **File Postingan dan Halaman.**
  Semua konten di Jekyll adalah posting atau halaman sehingga posting dan halaman yang valid diuraikan dengan penurunan harga atau tekstil.
- **File template.**
File-file ini masuk ke folder `_layouts` dan berisi **template** blog Anda. Mereka harus dibuat dalam HTML dengan bantuan sintaks Liquid.
Karena file include hanya disuntikkan ke dalam template, mereka pada dasarnya diurai seolah-olah itu asli dari template.

**File dan folder arbitrer.**
File yang _bukan_ halaman yang valid diperlakukan sebagai konten statis dan melewati
Jekyll tidak tersentuh dan berada di blog Anda dalam struktur dan format yang sama seperti aslinya.

### Memformat File untuk Parsing.

Kami telah menguraikan perlunya pemformatan yang valid menggunakan **YAML Front Matter**.
Template, posting, dan halaman semua harus menyediakan YAML Front Matter yang valid meskipun Matter kosong.
Ini adalah satu-satunya cara Jekyll tahu Anda ingin file diproses.

YAML Front Matter harus didahului dengan bagian atas template/post/page files:

    ---
    layout: post
    category : pages
    tags : [how-to, jekyll]
    ---

    ... contents ...

Tiga tanda hubung pada baris baru memulai blok Front-Matter dan tiga tanda hubung pada baris baru mengakhiri blok.
Data di dalam blok harus YAML yang valid.

Parameter konfigurasi untuk YAML Front-Matter diuraikan di sini:
[A comprehensive explanation of YAML Front Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter)

#### Mendefinisikan Tata Letak untuk Postingan dan Parsing Template.

Parameter `layout` di YAML Front Matter mendefinisikan file template yang harus diinjeksi dengan postingan atau template tertentu.
Jika file template menentukan tata letaknya sendiri, file tersebut secara efektif digunakan sebagai `sub-templat.`
Artinya memuat file posting ke dalam file templat yang merujuk ke file templat lain dengan pekerjaan seperti yang Anda harapkan; sebagai sub-templat bersarang.

## Bagaimana Jekyll Menghasilkan File Statis Terakhir.

Pada akhirnya, tugas Jekyll adalah menghasilkan representasi statis dari situs web Anda.
Berikut ini adalah garis besar cara melakukannya:

1. **Jekyll mengumpulkan data.**
  Jekyll memindai direktori posting dan mengumpulkan semua file posting sebagai objek posting. Kemudian memindai aset tata letak dan mengumpulkannya dan akhirnya memindai direktori lain untuk mencari halaman.

2. **Jekyll menghitung data.**
  Jekyll mengambil objek-objek ini, menghitung metadata (permalinks, tag, kategori, judul, tanggal) dari mereka dan membangun satu
  objek `situs` besar yang menampung semua posting, halaman, tata letak, dan metadata masing-masing.
  Pada tahap ini situs Anda adalah satu objek ruby ​​besar yang dihitung.

3. **Jekyll mencairkan postingan dan template.**
  Selanjutnya jekyll mengulang setiap file posting dan mengonversi (melalui penurunan harga atau tekstil) dan **mencairkan** posting di dalam tata letak masing-masing.
  Setelah posting diuraikan dan dicairkan di dalam struktur tata letak yang tepat, tata letak itu sendiri "dicairkan".
**Liquification** didefinisikan sebagai berikut: Jekyll memulai template Liquid, dan meneruskan representasi hash yang lebih sederhana dari objek situs ruby ​​serta yang lebih sederhana
  representasi hash dari objek posting Ruby. Struktur data yang disederhanakan inilah yang dapat Anda akses dalam template.

3. **Jekyll menghasilkan keluaran.**
Akhirnya templat cair "dirender", sehingga memproses sintaksis cair apa pun yang disediakan di templat
dan menyimpan representasi statis terakhir dari file.

**Catatan.**
Karena Jekyll menghitung seluruh situs dalam satu gerakan, setiap template diberikan akses ke
hash `situs` global yang berisi data berguna. Data inilah yang akan Anda ulangi dan format
menggunakan tag dan filter Liquid untuk merendernya ke halaman tertentu.

Ingat, di Jekyll Anda adalah pengguna akhir. API Anda hanya memiliki dua komponen:

1. Cara Anda mengatur direktori Anda.
2. Sintaks dan variabel cair diteruskan ke templat cair.

Semua objek data yang tersedia untuk Anda dalam template melalui Liquid diuraikan di **Bagian API** Jekyll-Bootstrap.
Anda juga dapat membaca dokumentasi aslinya di sini: <https://github.com/mojombo/jekyll/wiki/Template-Data>

## Kesimpulan

Saya harap ini memberikan gambaran yang lebih jelas tentang apa yang dilakukan Jekyll dan mengapa ia bekerja seperti itu.
Seperti disebutkan, kendala pemrograman utama kami adalah kenyataan bahwa API kami terbatas pada apa yang dapat diakses melalui Liquid dan Liquid saja.

Jekyll-bootstrap dimaksudkan untuk menyediakan metode dan strategi pembantu yang bertujuan untuk membuatnya lebih intuitif dan lebih mudah untuk bekerja dengan Jekyll =)

**Terima kasih** telah membaca sejauh ini.

## Langkah selanjutnya

Silakan lihat [{{ site.categories.api.first.title }}]({{ BASE_PATH }}{{ site.categories.api.first.url }})
atau lompat langsung ke [Usage]({{ BASE_PATH }}{{ site.categories.usage.first.url }}) jika kamu mau.