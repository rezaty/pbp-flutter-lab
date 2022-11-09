# Tugas 7: Elemen Dasar Flutter

Nama            : Reza Taufiq Yahya

Kelas           : PBP C

NPM             : 2106654183

### 1. Jelaskan apa yang dimaksud dengan stateless widget dan stateful widget dan jelaskan perbedaan dari keduanya.
- Secara sederhana Stateless Widget dapat diartikan sebagai Widget yang tidak dapat dirubah atau tidak akan pernah berubah.
- Stateful Widget merupakan widget yang dinamis atau dapat berubah. Berbanding terbalik dengan stateless, stateful widget dapat mengupdate tampilan, merubah warna, menambah jumlah baris dll. Jadi dapat disimpulkan bahwa apapun widget yang dapat berubah maka itulah stateful widget.
Jika kita ingin membuat komponen sederhana dan bersifat statis maka Stateless Widget adalah pilihan yang tepat. Tetapi apabila membutuhkan komponen yang dinamis maka gunakan stateful widget.

### 2. Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.
### 3. Apa fungsi dari `setState()?` Jelaskan variabel apa saja yang dapat terdampak dengan fungsi tersebut.
`setState()` merencanakan suatu pembaruan ke suatu state objek komponen. Ketika state berubah, komponen merespons dengan me-render ulang. 
### 4. Jelaskan perbedaan antara `const` dengan `final`.
Seperti pada bahasa pemrograman umumnya dart juga mendukung variabel yang bersifat immutable atau nilainya tidak bisa dirubah, pada bahasa dart sendiri terdapat 2 kata kunci berbeda yang dapat digunakan untuk membuat variabel immutable yaitu final dan const.
-Final dapat digunakan untuk deklarasi variabel immutable yang nilainya sudah ataupun belum diketahui pada saat waktu kompilasi berjalan.
-Const dapat digunakan untuk deklarasi variabel immutable yang nilainya bersifat konstan dan harus sudah diketahui pada saat waktu kompilasi berjalan, artinya adalah nilai dari variabel tersebut harus sudah di berikan secara langsung.
### 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas.