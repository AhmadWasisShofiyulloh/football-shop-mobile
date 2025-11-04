<details>
<summary>Tugas Individu 7</summary>

Widget tree adalah struktur hierarki dari seluruh widget dalam aplikasi Flutter, di mana setiap elemen UI tersusun dalam hubungan induk–anak (parent–child). Widget induk bertanggung jawab mengatur tata letak dan perilaku widget anak, sehingga setiap tampilan terbentuk dari kombinasi widget yang saling bersarang membentuk sebuah pohon.

Widget yang Digunakan dan Fungsinya:
1. MyApp: Root widget.
2. MaterialApp: Fondasi.
3. ThemeData: Mengatur skema warna.
4. MyHomePage: Membangun tampilan beranda.
5. Scaffold: Menyediakan kerangka.
6. AppBar: Menampilkan judul aplikasi.
7. Column: Menampung header dan body utama.
8. Row: Digunakan di dalam Column untuk menyusun data diri secara horizontal.
10. GridView: Layout utama untuk menu.
11. ItemCard: Widget terkecil, di mana Material dan InkWell adalah komponen kuncinya.
12. ScaffoldMessenger: Digunakan untuk menampilkan pesan pop-up singkat (SnackBar) saat sebuah menu diklik.
13. Padding: Menyisipkan ruang kosong di sekitar satu child widget. 
14. Material: Widget yang mendefinisikan properti visual.
15. InkWell: Membuat area widget menjadi interaktif dengan menambahkan efek visual saat ditekan.
16. Container: Menampung, menata, dan memberikan gaya pada child widget.
17. Center: Menempatkan child widget tepat di tengah dari widget induknya.
18. Text: Menampilkan teks dengan gaya tertentu.
19. TextStyle: Objek yang digunakan untuk mendefinisikan gaya dan format dari Text.
20. Icon: Menampilkan ikon Material Design.
21. SizedBox: Membuat kotak dengan ukuran tetap.

MaterialApp berfungsi sebagai widget utama yang membungkus seluruh aplikasi dengan gaya dan struktur Material Design. Widget ini menyediakan pengaturan tema, navigasi, dan konfigurasi global lainnya, sehingga sering digunakan sebagai root widget karena menjadi fondasi utama bagi tampilan dan perilaku aplikasi Flutter.

StatelessWidget digunakan untuk tampilan statis yang tidak berubah, sedangkan StatefulWidget digunakan ketika tampilan perlu berubah berdasarkan interaksi atau data baru. Saya memilih StatelessWidget untuk elemen yang tetap, seperti label atau ikon, dan StatefulWidget untuk bagian yang dinamis seperti tombol interaktif atau daftar produk yang dapat diperbarui.

BuildContext adalah objek yang merepresentasikan posisi widget dalam widget tree dan digunakan untuk mengakses informasi lingkungan seperti tema, ukuran layar, atau navigasi. Dalam metode build, context penting karena memungkinkan widget berinteraksi dengan widget lain dan mengambil data dari hierarki aplikasi.

“Hot reload” memungkinkan pengembang melihat perubahan kode secara langsung tanpa kehilangan state aplikasi, sedangkan “hot restart” memuat ulang seluruh aplikasi dari awal dan menghapus state yang ada. Hot reload ideal untuk mempercepat pengembangan tampilan, sementara hot restart digunakan jika ada perubahan besar pada struktur aplikasi.
</details>