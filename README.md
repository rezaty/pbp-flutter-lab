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

# Tugas 8: Flutter Form

Nama            : Reza Taufiq Yahya

Kelas           : PBP C

NPM             : 2106654183

### 1. Jelaskan perbedaan Navigator.push dan Navigator.pushReplacement.
`Navigator.push ()`: Metode push digunakan untuk menambahkan rute lain ke atas tumpukan screen (stack) saat ini. Halaman baru ditampilkan di atas halaman sebelumnya.
`Navigator.pushReplacement()` : Berpindah halaman, namun tidak dapat kembali ke halaman sebelumnya.
### 2. Sebutkan widget apa saja yang kamu pakai di proyek kali ini dan jelaskan fungsinya.
- IconButton() : Widget icon yang berfungsi sebagai icon button.
- SizedBox() : Widget yang berfungsi untuk membuat box dengan ukuran spesifik.
- TextFormField() : Widget yang bisa digunakan untuk menginput teks.
- TextButton() : Widget yang berfungsi sebagai tombol.
- InputDatePickerFormField () : Widget TextFormField yang dikonfigurasi untuk menerima dan memvalidasi tanggal yang dimasukkan oleh pengguna.
- MyDrawer() = widget yang digunakan untuk menampilkan drawer.
### 3. Sebutkan jenis-jenis event yang ada pada Flutter (contoh: onPressed).
- onPressed = fungsi yang menjalankan fungsi saat pengguna menekan tombol.
- onChanged = fungsi yang menjalankan fungsi saat pengguna mengubah sesuatu hal.
- onTap = fungsi untuk menjalankan fungsi saat pengguna mengetuk widget.
### 4. Jelaskan bagaimana cara kerja Navigator dalam "mengganti" halaman dari aplikasi Flutter.
Navigator adalah widget yang digunakan untuk mengatur rute yang ada (route management). Navigator bertanggung jawab untuk menavigasi dari satu rute/layar ke rute/layar lainnya. Selain itu, navigator menampilkan layar atau rute sebagai tumpukan, sering disebut sebagai tumpukan navigasi. Untuk menavigasi ke layar baru, kita perlu menggunakan navigator di atas BuildContext rute dan memanggil metode `push()` atau `pop()` .
### 5. Jelaskan bagaimana cara kamu mengimplementasikan checklist di atas.
1. Menambahkan drawer menu pada app dengan membuat widget `MyDrawer()` pada file `drawer.dart`.
``` dart
import 'package:flutter/material.dart';
import 'package:counter_7/DataBudget.dart';
import 'package:counter_7/TambahBudget.dart';
import 'package:counter_7/main.dart';

class MyDrawer extends StatelessWidget {
  const MyDrawer({super.key});

  @override
  Widget build(BuildContext context) {
    return Drawer(
      child: Column(
        children: [
          // Menambahkan clickable menu
          ListTile(
            title: const Text('Counter_7'),
            onTap: () {
              // Route menu ke halaman utama
              Navigator.pushReplacement(
                context,
                MaterialPageRoute(
                    builder: (context) => const MyHomePage(
                          title: 'Program Counter',
                        )),
              );
            },
          ),
          ListTile(
            title: const Text('Tambah Budget'),
            onTap: () {
              // Route menu ke halaman form
              Navigator.pushReplacement(
                context,
                MaterialPageRoute(builder: (context) => const MyFormPage()),
              );
            },
          ),
          ListTile(
            title: const Text('Data Budget'),
            onTap: () {
              // Route menu ke halaman form
              Navigator.pushReplacement(
                context,
                MaterialPageRoute(builder: (context) => const MyDataBudget()),
              );
            },
          ),
        ],
      ),
    );
  }
} 
```
2. Menambahkan tiga tombol navigasi pada drawer. 
Hal ini dilakukan dengan menambahkan child pada widget Drawer seperti di atas. Widget yang ditambahkan berupa Column dengan children berupa ListTile yang mengandung teks untuk masing-masing halaman dan onTap property dengan value berupa fungsi yang digunakan untuk berpindah dari satu halaman ke halaman yang lain.

3. Membuat flle untu form budget yaitu `TambahBudget.dart`.
``` dart
import 'package:counter_7/drawer.dart';
import 'package:counter_7/main.dart';
import 'package:flutter/material.dart';
import 'package:flutter/services.dart';

class MyFormPage extends StatefulWidget {
  const MyFormPage({super.key});

  @override
  State<MyFormPage> createState() => MyFormPageState();
}

class MyFormPageState extends State<MyFormPage> {
  final _formKey = GlobalKey<FormState>();
  String _judul = "";
  int _nominal = 0;
  DateTime _tanggalPembuatan = DateTime.now();

  String? _jenisBudget;
  final List<String> _listJenisBudget = ["Pemasukan", "Pengeluaran"];
  static List<Budget> budgets = [];

  List<Budget> get getBudgets {
    return budgets;
  }

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: const Text('Form Budget'),
      ),
      drawer: const MyDrawer(),
      body: Form(
        key: _formKey,
        child: SingleChildScrollView(
          child: Container(
              padding: const EdgeInsets.all(20.0),
              height: 600,
              child: Column(
                mainAxisAlignment: MainAxisAlignment.spaceAround,
                children: [
                  Column(children: [
                    Padding(
                        // Menggunakan padding sebesar 8 pixels
                        padding: const EdgeInsets.all(8.0),
                        child: TextFormField(
                          decoration: InputDecoration(
                            labelText: "Judul",
                            hintText: "Contoh : Beli Sate Pacil",
                            // Menambahkan circular border agar lebih rapi
                            border: OutlineInputBorder(
                              borderRadius: BorderRadius.circular(5.0),
                            ),
                          ),
                          // Menambahkan behavior saat judul diketik
                          onChanged: (String? value) {
                            setState(() {
                              _judul = value!;
                            });
                          },
                          // Menambahkan behavior saat data disimpan
                          onSaved: (String? value) {
                            setState(() {
                              _judul = value!;
                            });
                          },
                          // Validator sebagai validasi form
                          validator: (String? value) {
                            if (value == null || value.isEmpty) {
                              return 'Judul budget tidak boleh kosong!';
                            }
                            return null;
                          },
                        )),
                    Padding(
                        // Menggunakan padding sebesar 8 pixels
                        padding: const EdgeInsets.all(8.0),
                        child: TextFormField(
                          keyboardType: TextInputType.number,
                          inputFormatters: <TextInputFormatter>[
                            FilteringTextInputFormatter.digitsOnly
                          ],
                          decoration: InputDecoration(
                            hintText: "Masukkan Nominal",
                            labelText: "Nominal",
                            // Menambahkan circular border agar lebih rapi
                            border: OutlineInputBorder(
                              borderRadius: BorderRadius.circular(5.0),
                            ),
                          ),
                          // Menambahkan behavior saat nominal diketik
                          onChanged: (String? value) {
                            setState(() {
                              _nominal =
                                  (value!.isEmpty) ? 0 : int.parse(value);
                            });
                          },
                          // Menambahkan behavior saat data disimpan
                          onSaved: (String? value) {
                            setState(() {
                              _nominal =
                                  (value!.isEmpty) ? 0 : int.parse(value);
                            });
                          },
                          validator: (String? value) {
                            if (value == null || value.isEmpty) {
                              return 'Nominal budget tidak boleh kosong!';
                            }
                            return null;
                          },
                        )),
                    Padding(
                      padding: const EdgeInsets.all(8.0),
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        children: [
                          Expanded(
                            child: InputDatePickerFormField(
                              firstDate: DateTime(2000),
                              initialDate: _tanggalPembuatan,
                              lastDate: DateTime(2099),
                              onDateSubmitted: (value) {
                                setState(() {
                                  _tanggalPembuatan = value;
                                });
                              },
                            ),
                          ),
                          IconButton(
                            icon: const Icon(Icons.date_range),
                            onPressed: () {
                              showDatePicker(
                                context: context,
                                initialDate: DateTime.now(),
                                firstDate: DateTime(2000),
                                lastDate: DateTime(2099),
                              ).then((value) {
                                if (value != null) {
                                  setState(() {
                                    _tanggalPembuatan = value;
                                  });
                                }
                              });
                            },
                          ),
                        ],
                      ),
                    ),
                    Padding(
                      padding: const EdgeInsets.all(8.0),
                      child: Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        children: [
                          Expanded(
                            child: DropdownButtonFormField(
                              hint: const Text("Pilih jenis"),
                              value: _jenisBudget,
                              icon: const Icon(Icons.keyboard_arrow_down),
                              items: _listJenisBudget.map((String items) {
                                return DropdownMenuItem(
                                  value: items,
                                  child: Text(items),
                                );
                              }).toList(),
                              onChanged: (String? newValue) {
                                setState(() {
                                  _jenisBudget = newValue!;
                                });
                              },
                              validator: (String? value) {
                                if (value == null || value.isEmpty) {
                                  return 'Nominal budget tidak boleh kosong!';
                                }
                                return null;
                              },
                            ),
                          ),
                        ],
                      ),
                    ),
                  ]),
                  Padding(
                    padding: const EdgeInsets.only(top: 100),
                    child: Row(
                        mainAxisAlignment: MainAxisAlignment.center,
                        children: [
                          SizedBox(
                            width: 200,
                            height: 40,
                            child: TextButton(
                              style: ButtonStyle(
                                backgroundColor:
                                    MaterialStateProperty.all(Colors.blue),
                              ),
                              onPressed: () {
                                if (_formKey.currentState!.validate()) {
                                  setState(() {
                                    budgets.add(Budget(
                                        jenis: _jenisBudget!,
                                        judul: _judul,
                                        nominal: _nominal,
                                        tanggalPembuatan: _tanggalPembuatan));
                                  });

                                  showDialog(
                                    context: context,
                                    builder: (context) {
                                      return Dialog(
                                        shape: RoundedRectangleBorder(
                                          borderRadius:
                                              BorderRadius.circular(10),
                                        ),
                                        elevation: 15,
                                        child: ListView(
                                          padding: const EdgeInsets.only(
                                              top: 20, bottom: 20),
                                          shrinkWrap: true,
                                          children: <Widget>[
                                            const Center(
                                                child: Text('Informasi Data')),
                                            Padding(
                                                padding:
                                                    const EdgeInsets.all(10),
                                                child: Text(
                                                  "Tanggal Pembuatan: $_tanggalPembuatan \n $_jenisBudget dengan judul $_judul dan harga $_nominal berhasil ditambahkan",
                                                  textAlign: TextAlign.center,
                                                )),
                                            TextButton(
                                              onPressed: () {
                                                Navigator.pop(context);
                                              },
                                              child: const Text('Kembali'),
                                            ),
                                          ],
                                        ),
                                      );
                                    },
                                  );
                                }
                              },
                              child: const Text(
                                "Simpan",
                                style: TextStyle(color: Colors.white),
                              ),
                            ),
                          )
                        ]),
                  ),
                ],
              )),
        ),
      ),
    );
  }
}

class Budget {
  String judul;
  int nominal;
  String jenis;
  DateTime tanggalPembuatan;

  Budget(
      {required this.jenis,
      required this.judul,
      required this.nominal,
      required this.tanggalPembuatan});
}
```
4. Membuat flle untu form budget yaitu `DataBudget.dart`. Untuk menampilkan Budget yang sudah diinput.
``` dart
import 'package:flutter/material.dart';
import 'package:counter_7/TambahBudget.dart';
import 'package:counter_7/drawer.dart';

class MyDataBudget extends StatefulWidget {
  const MyDataBudget({super.key});

  @override
  State<MyDataBudget> createState() => _MyDataBudgetState();
}

class _MyDataBudgetState extends State<MyDataBudget> {
  List<Widget> listDataBudget = [];

  void addDataBudget() {
    setState(() {
      for (var i = 0; i < MyFormPageState.budgets.length; i++) {
        Budget data = MyFormPageState.budgets[i];
        listDataBudget.add(Padding(
            padding: const EdgeInsets.only(top: 5, bottom: 5),
            child: Card(
                child: ListTile(
              title:
                  Text('${data.judul} (${data.tanggalPembuatan.toString()})'),
              subtitle: Text('${data.nominal}'),
              trailing: Text(data.jenis),
            ))));
      }
    });
  }

  @override
  Widget build(BuildContext context) {
    if (listDataBudget.isEmpty) {
      addDataBudget();
    }
    return Scaffold(
        appBar: AppBar(
          title: const Text("Data Budget"),
        ),
        // Menambahkan drawer menu
        drawer: const MyDrawer(),
        body: Container(
          padding: const EdgeInsets.all(20),
          height: 800,
          child: SingleChildScrollView(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.start,
              crossAxisAlignment: CrossAxisAlignment.start,
              children: listDataBudget,
            ),
          ),
        ));
  }
}
```