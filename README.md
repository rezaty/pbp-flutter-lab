# Tugas 7: Elemen Dasar Flutter

Nama            : Reza Taufiq Yahya

Kelas           : PBP C

NPM             : 2106654183

### 1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget dan jelaskan perbedaan dari keduanya.
- Secara sederhana Stateless Widget dapat diartikan sebagai Widget yang tidak dapat dirubah atau tidak akan pernah berubah.
- Stateful Widget merupakan widget yang dinamis atau dapat berubah. Berbanding terbalik dengan stateless, stateful widget dapat mengupdate tampilan, merubah warna, menambah jumlah baris dll. Jadi dapat disimpulkan bahwa apapun widget yang dapat berubah maka itulah stateful widget.
Jika kita ingin membuat komponen sederhana dan bersifat statis maka Stateless Widget adalah pilihan yang tepat. Tetapi apabila membutuhkan komponen yang dinamis maka gunakan stateful widget.

### 2. Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.
- MaterialApp : Widget yang membungkus sejumlah widget yang biasanya diperlukan untuk aplikasi Desain Material
- AppBar : AppBar biasanya menampilkan satu atau beberapa tindakan umum dengan IconButton s yang secara opsional diikuti oleh PopupMenuButton
- Scaffold : Menerapkan struktur tata letak visual Desain Material dasar. Kelas ini menyediakan API untuk showing drawers and bottom sheets.
- FloatingActionButton : Tombol ikon melingkar yang mengarahkan kursor ke konten untuk mempromosikan tindakan utama dalam aplikasi
- Padding : Padding adalah jarak kotak dengan elemen yang ada di dalam kotak
- Theme : Menggambarkan warna dan pilihan tipografi aplikasi
- Text : untuk menampilkan String teks dengan satu style
- DefaultTextStyle : Style teks yang diberikan ketika tidak memiliki eksplisit style teks
- Align : widget yang akan mereturn dirinya sendiri dan opsional mengukur dirinya sendiri berdasarkan ukuran childnya
- Center : Widget yang menengahkan childnya di dalam dirinya sendiri
- Row : Widget yang menampilkan childnya dalam bentuk horizontal
- Column : Widget yang menampilkan childnya dalam bentuk vertikal
- Visibility : Widget untuk menyembunyikan child atau subtree.

### 3. Apa fungsi dari `setState()?` Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.
Fungsi dari `setState()` adalah untuk memanipulasi dan mengubah data-data yang berada dalam stateful widget yang disimpan pada object state. Variabel-variabel yang terdampak dengan fungsi tersebut adalah _counter dan category dimana _counter dimanipulasi increment dan decrement nya sedangkan category digunakan untuk mengkategorikan _counter apakah ganjil ataupun genap. 

### 4. Jelaskan perbedaan antara `const` dengan `final`.
Seperti pada bahasa pemrograman umumnya dart juga mendukung variabel yang bersifat immutable atau nilainya tidak bisa dirubah, pada bahasa dart sendiri terdapat 2 kata kunci berbeda yang dapat digunakan untuk membuat variabel immutable yaitu final dan const.
-Final dapat digunakan untuk deklarasi variabel immutable yang nilainya sudah ataupun belum diketahui pada saat waktu kompilasi berjalan.
-Const dapat digunakan untuk deklarasi variabel immutable yang nilainya bersifat konstan dan harus sudah diketahui pada saat waktu kompilasi berjalan, artinya adalah nilai dari variabel tersebut harus sudah di berikan secara langsung.

### 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas.
- Pertama bikin app counter_7 lewat cmd dengan perintah `flutter create counter_7`
- Membuat fungsi _decrementCounter yang akan mengurangi variabel _counter 
- Mengatur warna dari text sesuai ketentuan, jika Genap maka berwarna merah dan Ganjil maka berwarna biru
- Menambahkan button + dan - yang akan memanggil fungsi _incrementCounter() dan _decrementCounter serta mengatur visibility pada button - supaya hilang ketika _counter bernilai 0 (BONUS).