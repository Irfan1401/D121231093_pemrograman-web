ini adalah website prtovolio dan cv pribadi saya untuk menampilkan keahlian, proyek dan latar belakang profesional. website ini di bangun dengan menggunakan HTML, CSS dan JavaScript.

berikut penjelasannya:

A. index.html:

File index.html menyediakan kerangka dan konten dari website. Strukturnya dibuat secara semantik untuk memastikan kejelasan, aksesibilitas, dan optimisasi mesin pencari (SEO) yang baik.

Fitur Utama & Alasan Penggunaannya
HTML5 Semantik: 

1. Saya menggunakan tag seperti <header>, <nav>, <section>, dan <footer>. 
    Alasan: Hal ini membuat kode lebih mudah dibaca dan lebih bermakna. Ini juga membantu mesin pencari dan screen reader (pembaca layar) untuk memahami tata letak dan hierarki konten di halaman.

2. Pembagian Section yang Logis: Halaman dibagi menjadi beberapa bagian yang jelas: Hero, About, Skills, Portfolio, dan Contact. Setiap bagian memiliki ID yang unik (contoh: #about).

    Alasan: Ini mengorganisir konten secara logis. ID tersebut berfungsi sebagai penanda (anchor), memungkinkan tautan di navbar (<a href="#about">) untuk mengarahkan pengguna ke bagian yang sesuai dengan mulus.

3.  Class fade-in: Anda akan melihat bahwa elemen <section> utama memiliki kelas bernama fade-in.

    Alasan: Kelas ini berfungsi sebagai "pengait" (hook) untuk JavaScript agar dapat memicu animasi berbasis scroll, membuat situs terasa lebih dinamis saat dijelajahi.

3. Penempatan Script: Tag <script src="script.js"></script> ditempatkan tepat sebelum tag penutup </body>.

    Alasan: Ini adalah praktik terbaik untuk performa web. Hal ini memungkinkan browser untuk mem-parsing dan me-render semua konten HTML terlebih dahulu, sehingga pengguna dapat melihat halaman dengan cepat. Elemen JavaScript yang interaktif dimuat setelahnya untuk mencegah penundaan render.

B. style.css

File ini mengontrol seluruh presentasi visual website, mulai dari tata letak, warna, hingga animasi dan desain responsif.

Fitur Utama & Alasan Penggunaannya
Teknik Tata Letak Modern: 

1. Tata letak situs ini terutama menggunakan Flexbox (untuk navbar) dan CSS Grid (untuk bagian portofolio).

    Alasan: Ini adalah alat CSS modern yang mempermudah pembuatan tata letak yang kompleks, fleksibel, dan responsif. Flexbox sangat cocok untuk menyelaraskan item dalam satu dimensi (seperti navbar), sementara Grid sangat baik untuk tata letak dua dimensi (seperti kartu portofolio).

2. Desain Responsif: Media query @media (max-width: 768px) digunakan untuk menerapkan gaya yang berbeda pada perangkat seluler.

    Alasan: Ini memastikan website terlihat bagus dan berfungsi penuh di berbagai ukuran layar. Pada layar yang lebih kecil, navbar tradisional diciutkan menjadi menu "hamburger" untuk menghemat ruang dan meningkatkan kegunaan.

3. UI Interaktif & Animasi:

a. Efek Hover: Kartu-kartu portofolio memiliki efek hover yang sedikit mengangkat kartu (transform: translateY) dan memperbesar gambar (transform: scale).

    Alasan: Interaksi kecil ini memberikan umpan balik visual kepada pengguna, membuat situs terasa lebih responsif dan menarik.

b. Animasi Fade-In: Kelas .fade-in dan .fade-in.show mendefinisikan animasi yang mengubah opasitas dan posisi elemen.

    Alasan: Ini menciptakan efek halus dan profesional di mana konten muncul saat pengguna melakukan scroll. Gayanya disimpan di CSS untuk memisahkannya dari logika JavaScript yang memicunya.

C. script.js

File JavaScript menghidupkan website yang statis dengan menambahkan fitur interaktif dan dinamis. Kode ini ditulis secara modern dan berfokus pada performa.

1. Toggle Navbar Seluler
Cara Kerja: Kode ini mendengarkan event klik pada ikon menu hamburger. Saat diklik, kode ini akan menambah atau menghapus kelas .show dari daftar link navigasi <ul>.

    Alasan: Ini adalah cara yang efisien untuk menampilkan dan menyembunyikan menu seluler. Dengan hanya mengubah kelas, kita membiarkan CSS menangani semua perubahan gaya (dari display: none menjadi display: flex). Pemisahan tugas (separation of concerns) ini membuat kode lebih mudah dipelihara.

2. Efek Fade-in saat Scroll
Cara Kerja: Fitur ini membuat setiap section muncul secara perlahan (fade-in) saat pengguna menggulir halaman ke bawah.

    Alasan: Untuk mencapai ini, saya menggunakan IntersectionObserver API. Ini adalah fitur browser modern yang sangat berkinerja tinggi dan dirancang khusus untuk tujuan ini.

    Performa: Tidak seperti metode tradisional yang memantau setiap event scroll (yang dapat memperlambat situs), IntersectionObserver hanya menjalankan kode ketika sebuah elemen benar-benar masuk atau keluar dari layar.

    Efisiensi: Setelah sebuah elemen selesai muncul, skrip akan memanggil observer.unobserve(entry.target). Ini memberitahu browser untuk berhenti mengamati elemen tersebut, sehingga menghemat sumber daya sistem.