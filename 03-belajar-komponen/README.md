## Nama: Patria Anggara Susilo Putra
## Kelas: TI 3A
## NIM: 2141720058
---

### 1. Ubah isi kode Home() sehingga dapat tampil seperti berikut dengan memanfaatkan komponen Profile() yang tadi sudah dibuat dari langkah 1 tersebut!

+ Membuat komponen profile
![screenshot_langkah_2](assets-record/praktikum-satu/1.png)

+ Import komponen dan gunakan di page.tsx
![screenshot_langkah_3](assets-record/praktikum-satu/2.png)

+ Menampilkan hasil
![screenshot_hasil](assets-record/praktikum-satu/result.png)

Sempat mengalami error saat menampilkan gambarnya, hal ini disebabkan tidak mengatur domains di file next.config.mjs. 

![screenshot_error](assets-record/praktikum-satu/error.png)

Cara memperbaikinya sangat mudah, cukup buka file next.config.mjs, di dalam nextConfig tambahkan objek images, di dalam images tambahkan properti domains dengan nilai domain dari gambar (sebenarnya menggunakan domains sudah tidak didukung tapi entah kenapa bisa :v).

![screenshot_error](assets-record/praktikum-satu/solve.png)

### 2. Jelaskan apa yang telah Anda pelajari dan bagaimana tampilannya saat ini?

![screenshot_result_1](assets-record/praktikum-dua/result-1.png)

Kode dari tampilan di atas seperti berikut:

![screenshot_praktikum_2](assets-record/praktikum-dua/1.png)

![screenshot_praktikum_2](assets-record/praktikum-dua/2.png)

Dari praktikum kedua, hasilnya menampilkan gambar yang kurang sejajar dengan dua gambar lainnya. Agar gambar sejajar semua, gunakan flex. Berikut perbaikannya:


![screenshot_solve_1](assets-record/praktikum-dua/solve-1.png)

![screenshot_solve_2](assets-record/praktikum-dua/solve-2.png)

Ganti class "columns-3" dengan class "flex justify-center items-center" dan hapus class sebelumnya di tag div pada page.tsx (sisakan class margin-top saja).

Dengan membuat komponen baru (Gallery) untuk menampung 3 gambar profile, saat digunakan pada page.tsx tidak perlu memanggil sebanyak 3x seperti sebelumnya (yang saya komen) karena di dalam komponen Gallery sudah memanggil komponen Profile sebanyak 3x, jadi kode yang ada di dalam page.tsx menjadi lebih bersih dan singkat.

Berikut hasil setelah melakukan perbaikan kode:

![screenshot_result_2](assets-record/praktikum-dua/result-2.png)

### 3. Silakan perbaiki kode JSX berikut ini. Anda boleh menggunakan konverter atau perbaiki secara manual dan elaskan apa yang telah Anda pelajari dan mengapa error itu bisa terjadi?

![screenshot_bonus_stage](assets-record/bonus-stage/not-solved.png)

Ada beberapa kesalahan dari kode di atas:
+ saat mereturn jsx, jumlah tag yang di return harus berjumlah satu, maka dari itu bungkus dengan div atau tag kosong (fragment)
+ properti class pada tag div seharusnya memakai className
+ tag br tidak bisa digunakan di dalam tag p
+ posisi tag penutup dari tag b salah, seharusnya setelah tag penutup dari tag i (tinggal ganti posisi)

Berikut kode yang telash diperbaiki dan hasilnya:

![screenshot_bonus_stage](assets-record/bonus-stage/solved.png)

![screenshot_bonus_stage](assets-record/bonus-stage/result.png)

### 4. Silahkan perbaiki kode yang error

![screenshot_praktikum_3](assets-record/praktikum-tiga/solved.png)

+ panggil properti name di variabel person di dalam tag h1 (belumnya tidak dipanggil)
+ Sebaiknya ganti karakter ' dengan &-apos; (tanpa tanda hubung)
+ tag img saya ganti dengan Image dari next karena muncul warning Using <img> could result in slower LCP and higher bandwidth. Consider using <Image /> from next/image to automatically optimize images. This may incur additional usage or cost from your provider. (sebenarnya nggak error cuma nggak enak dilihat karena muncul warna kuning wkwkwk)
+ jika menggunakan komponen Image dari next, wajib menyertakan properti width dan height, kalau tidak akan muncul error pada web sebagai berikut:

![screenshot_error_1](assets-record/praktikum-tiga/error-1.png)

![screenshot_error_2](assets-record/praktikum-tiga/error-2.png)

Berikut hasilnya:

![screenshot_result](assets-record/praktikum-tiga/result.png)

### 5. Buka file src/components/todolist.tsx lakukan ekstrak URL gambar ke dalam objek person. Apakah ada perbedaan pada tampilan web saat ini?

![screenshot_solved_2](assets-record/praktikum-tiga/solved-2.png)

![screenshot_solved_3](assets-record/praktikum-tiga/solved-3.png)

![screenshot_result_2](assets-record/praktikum-tiga/result-2.png)

Link gambar saya masukkan ke dalam person dengan property bernama profile, dari situ dipanggil di dalam property scr, lalu diimport ke page.tsx, dari hasil di atas, gambar tampil dengan benar, dan karena tag gallery dipanggil muncul judul, garis pemisah dan tiga gambar.

### 6. Perbaiki kode tersebut pada bagian atribut src. Kode lainnya dapat Anda sesuaikan dari jawaban soal sebelumnya. Jelaskan apa yang telah Anda pelajari dan bagaimana tampilannya saat ini?

![screenshot_solved_4](assets-record/praktikum-tiga/solved-4.png)

Menampilkan gambar bisa menggunakan string literal (menggunakan simbol $ yang dibungkus dengan backtick). Setiap pemanggilan atribut objek person, dibungkus menggunakan kurung kurawal. Berikut hasilnya: 

![screenshot_result_3](assets-record/praktikum-tiga/result-3.png)

### 7. Jika kode di atas terdapat error, silakan diperbaiki. Komponen MyGallery ini berisi dua markup yang sama persis. Ekstraklah menjadi komponen MyProfile untuk mengurangi duplikasi. Anda perlu memilih props apa saja yang akan dikirimkan.

![screenshot_solved](assets-record/praktikum-empat/solved-1.png)

Membuat sebuah class interface untuk memuat data mengenai gambar yang ditampilkan, dari sini mengambil data nama, alamat gambar, profesi, penghargaan dan penemuan. Menggunakan destructuring objek.

![screenshot_result](assets-record/praktikum-empat/result.png)

### 8. Jika kode di atas terdapat error, silakan diperbaiki. Ubahlah komponen MyAvatar untuk diolah ukuran gambarnya berdasarkan prop size. Khususnya, jika size kurang dari 90, kirimkan 's' ("small") bukan 'b' ("big") pada fungsi getImageUrl. Pastikan bahwa perubahan yang Anda buat berjalan dengan cara me-render avatars dengan nilai prop size yang berbeda dan buka gambar pada tab baru di browser.

![screenshot_result](assets-record/praktikum-empat/solved-3.png)

![screenshot_result](assets-record/praktikum-empat/solved-4.png)

Menambahkan variabel untuk mengecek apakah size yang dimasukkan itu kurang dari 90 atau tidak. Menggunakan operator ternary dan di dalam fungsi getImageUrlV2(), parameter dikasih tipe data secara eksplisit.

Tampilan gamabr jika ukuran kurang dari 90 (maka nilai menjadi 's')
![screenshot_result](assets-record/praktikum-empat/result-2.png)

Tampilan gamabr jika ukuran lebih dari 90 (maka nilai menjadi 'b')
![screenshot_result](assets-record/praktikum-empat/result-3.png)

### 9. Jika kode di atas terdapat error, silakan diperbaiki. Buatlah komponen Card dari kode di atas, lalu gunakan prop children untuk mengirimkan JSX yang berbeda.

Membuat komponen card dengan menempatkan children di tengah tag div dan memanggil komponen Card di dalam komponen MyProfileV2.

![screenshot_solved_4](assets-record/praktikum-empat/solved-5.png)

![screenshot_result_4](assets-record/praktikum-empat/result-4.png)