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

"Hot reload" memungkinkan pengembang melihat perubahan kode secara langsung tanpa kehilangan state aplikasi, sedangkan "hot restart" memuat ulang seluruh aplikasi dari awal dan menghapus state yang ada. Hot reload ideal untuk mempercepat pengembangan tampilan, sementara hot restart digunakan jika ada perubahan besar pada struktur aplikasi.
</details>

<details>
<summary>Tugas Individu 8</summary>

Navigator.push() digunakan untuk menambahkan halaman baru di atas halaman saat ini, sehingga pengguna masih bisa kembali ke halaman sebelumnya dengan tombol back. Sedangkan Navigator.pushReplacement() menggantikan halaman yang sedang aktif dengan halaman baru, sehingga pengguna tidak bisa kembali ke halaman sebelumnya. Dalam aplikasi Football Shop, Navigator.push() digunakan untuk berpindah dari halaman utama ke form tambah produk agar pengguna bisa kembali ke menu utama setelah selesai. Sementara itu, Navigator.pushReplacement() digunakan pada navigasi dari Left Drawer untuk berpindah ke halaman utama tanpa menumpuk halaman sebelumnya, sehingga alur navigasi menjadi lebih efisien.

Scaffold berfungsi sebagai kerangka utama setiap halaman untuk menampung elemen-elemen seperti konten utama, tombol, dan drawer. AppBar menampilkan judul halaman seperti "Football Shop" agar pengguna selalu tahu konteks halaman yang sedang dibuka. Drawer digunakan sebagai navigasi samping yang berisi tombol menuju halaman utama dan form tambah produk, sehingga memudahkan pengguna berpindah antarhalaman tanpa kehilangan konsistensi tampilan.

Layout widget seperti Padding, SingleChildScrollView, dan ListView membantu menjaga tampilan elemen form agar tetap rapi, responsif, dan nyaman digunakan di berbagai ukuran layar. Padding digunakan untuk memberi jarak antar elemen agar tampilan form tidak terlalu rapat, SingleChildScrollView memastikan seluruh isi form tetap bisa digulir ketika kontennya panjang atau keyboard muncul, sedangkan ListView mempermudah penyusunan banyak elemen form secara vertikal tanpa overflow. Dalam aplikasi Football Shop, kombinasi Padding dan SingleChildScrollView digunakan di productlist_form.dart, serta ListView digunakan di left_drawer.dart untuk menampilkan input form produk dengan tata letak yang bersih dan mudah diakses.

Aplikasi Football Shop memiliki identitas visual yang konsisten dengan menggunakan ThemeData di MaterialApp, di mana ColorScheme diatur menggunakan primarySwatch: Colors.green dan secondary: Colors.greenAccent[400]. Penggunaan Theme.of(context).colorScheme.primary memastikan bahwa elemen seperti latar belakang, tombol, dan teks utama mengikuti palet warna yang sama, sehingga tampilan aplikasi terlihat seragam di seluruh halaman.
</details>

<details>
<summary>Tugas Individu 9</summary>

Model Dart diperlukan agar data JSON yang diterima atau dikirim memiliki struktur yang jelas, terdefinisi, dan aman dari kesalahan tipe. Jika kita langsung memakai Map<String, dynamic> tanpa model, maka kita kehilangan validasi tipe, rawan null-safety error, dan kode menjadi sulit dirawat karena kita harus menebak key JSON dan melakukan cast manual berulang kali. Dengan model, kita mendapatkan kode yang lebih aman, mudah dikelola, terprediksi, dan mudah diperbarui ketika struktur JSON berubah, sehingga aplikasi lebih maintainable dalam jangka panjang.

Package http digunakan untuk melakukan request HTTP sederhana seperti GET atau POST tanpa penyimpanan sesi, cocok untuk komunikasi stateless. Sedangkan CookieRequest (dari pbp_django_auth) memiliki kemampuan tambahan untuk menyimpan dan mengelola cookie session Django, sehingga dapat mempertahankan status login pengguna.

Karena CookieRequest menyimpan session cookie yang dipakai Django untuk mengenali pengguna, instance ini harus tetap satu dan konsisten di seluruh aplikasi. Jika setiap halaman membuat instance CookieRequest baru, maka session login akan hilang sehingga Django akan menganggap pengguna belum login. Dengan membagikan instance melalui Provider, semua halaman berbagi sesi yang sama sehingga status autentikasi tetap terjaga dan interaksi dengan backend tetap konsisten.

Flutter yang berjalan di Android emulator menggunakan alamat 10.0.2.2 untuk mengakses localhost di komputer host, sehingga alamat ini harus ditambahkan ke ALLOWED_HOSTS Django agar request tidak ditolak. CORS perlu diaktifkan agar Django mengizinkan permintaan dari domain berbeda (yaitu aplikasi Flutter). Pengaturan cookie seperti SameSite=None dan Secure diperlukan agar session cookie dapat dikirim dari Flutter ke Django. Selain itu, Flutter perlu diberi izin akses internet di AndroidManifest. Jika konfigurasi ini tidak dilakukan, permintaan jaringan akan gagal, cookie login tidak tersimpan, dan aplikasi tidak dapat berkomunikasi dengan backend sama sekali.

Proses dimulai ketika pengguna mengisi form pada Flutter. Data tersebut dikumpulkan dari TextEditingController atau widget form lainnya, kemudian diubah menjadi JSON dan dikirim ke endpoint Django melalui CookieRequest atau http. Django menerima request, memprosesnya (misalnya menyimpan data ke database), dan mengembalikan response berupa JSON. Flutter menerima JSON tersebut, mem-parsing-nya ke model Dart, lalu menampilkannya kembali dalam UI seperti daftar produk atau halaman detail.

Pada proses login atau register, Flutter mengirim data akun (username, password, dan lainnya) melalui CookieRequest. Django kemudian memvalidasi data tersebut menggunakan sistem autentikasinya; jika valid, Django mengembalikan session cookie ke Flutter yang kemudian disimpan oleh CookieRequest. Selama cookie ini aktif, Flutter dapat mengakses endpoint yang membutuhkan autentikasi. Saat logout, Flutter mengirim request ke endpoint logout Django, dan Django menghapus session di server. Flutter lalu menghapus session lokal, dan aplikasi kembali ke menu awal atau halaman login.

Langkah-langkah yang saya lakukan untuk mengimplementasikan checklist di atas adalah:
1. Mendownload library yang diperlukan, django-cors-headers di django, provider, pbp_django_auth, dan http di flutter.
2. Membuat app baru di projek Django bernama authentication
3. Mengatur settings.py untuk mengakomodasi flutter.
4. Membuat fungsi login, register, dan logout di django.
5. Membuat fungsi proxy image, create product, dan get my product di django.
6. Membuat file dart untuk login dan register.
7. Membuat halaman baru untuk menampilkan daftar produk.
8. Membuat halaman baru untuk menampilkan detail produk.
8. Mengubah model agar memiliki variabel boolean untuk keperluan filter.
</details>