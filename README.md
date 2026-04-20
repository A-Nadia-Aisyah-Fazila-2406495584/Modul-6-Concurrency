# Tutorial 5 - WebServer

<details>
<summary><b>Milestone 1: Single threaded web server</b></summary>

Method `handle_connection` bertugas untuk menerima dan membaca request yang dikirim oleh browser ke server kita. Ketika browser mengakses `127.0.0.1:7878`, browser sebenarnya mengirimkan text yang berisi informasi request, mulai dari method HTTP yang digunakan, path yang diminta, hingga header-header lainnya. 

Method `handle_connection` ini menggunakan `BufReader` untuk membaca teks tersebut secara efisien dan berhenti membaca ketika menemukan baris kosong, karena baris kosong menandakan bahwa bagian header sudah selesai. Semua baris header yang terkumpul kemudian disimpan dalam sebuah `Vec` dan di print ke terminal.

Saat pertama kali menjalankan server, muncul pesan "Connection established!" beberapa kali, padahal saya hanya membuka satu tab browser. Ternyata, itu terjadi karena browsernya secara otomatis kirim ulang request jika tidak mendapat respons dalam waktu tertentu. 

Selain itu, saya juga memperhatikan banyaknya penggunaan `.unwrap()` di kode ini. Fungsi dari `.unwrap()` adalah untuk mengambil nilai dari tipe `Result`, namun jika terjadi error maka program akan langsung berhenti.

</details>

<details>
<summary><b>Milestone 2: Returning HTML</b></summary>

![Commit 2 screen capture](/assets/images/Milestone2.png)

Saya melakukan modifikasi method `handle_connection` supaya server bisa mengirim balik respons berupa HTML page ke browser. Sebelumnya, servernya hanya bisa menerima request tapi tidak kirim apapun, makanya browser tidak menampilkan apa-apa. Saya melakukan itu dengan membaca file `hello.html` menggunakan `fs::read_to_string`, lalu hasilnya disusun menjadi HTTP response yang valid. Strukturnya urut dari status line `HTTP/1.1 200 OK`, header `Content-Length`, baris kosong, dan isi HTML-nya dikirim. Respons HTTP nya harus disusun secara manual menggunakan `format!`, tidak seperti framework web lain pada umumnya yang bisa menangani ini secara otomatis. 

</details>

<details>
<summary><b>Milestone 3: Validating request and selectively responding</b></summary>
... isi
</details>

<details>
<summary><b>Milestone 4: Simulation slow response</b></summary>
... isi
</details>

<details>
<summary><b>Milestone 5: Multithreaded server</b></summary>
... isi
</details>

<details>
<summary><b>Bonus</b></summary>
... isi
</details>