#  Assignment: Vue.js – Simple To-Do List

## 👤 Identitas
- **Nama** : BAIQ ALFIA ZAHIRA
- **NIM** : F1D02310042

---

## 📝 Deskripsi Tugas
Pada tugas ini, saya membangun aplikasi **To-Do List** sederhana menggunakan framework **Vue.js **. 

Pengguna dapat mengelola aktivitas harian mereka dengan fitur-fitur berikut:

1.  **Menambah Tugas (Create):** Input teks untuk menambahkan item baru ke dalam daftar.
2.  **Menghapus Tugas (Delete):** Tombol hapus pada setiap item untuk menghilangkan tugas yang sudah selesai.
3.  **Kondisi Daftar Kosong:** Menampilkan pesan ramah *"Belum ada tugas hari ini cantik "* menggunakan `v-if` ketika daftar kosong.
4.  **Reaktivitas (Reactivity):** Menggunakan `ref()` dari Vue untuk memastikan tampilan selalu *up-to-date* saat data berubah.
5.  **Validasi Input:** Mencegah pengguna memasukkan tugas kosong (blank text) agar data tetap valid.

---

## 🖼️ Hasil Implementasi

Berikut adalah dokumentasi tampilan antarmuka aplikasi dalam berbagai kondisi:

| Tampilan Program | Keterangan |
| :--- | :--- |
| <img src="https://github.com/user-attachments/assets/e853fd33-51c3-4cd7-a76a-c2582f88829c" width="100%"> | **1. Tampilan Awal (Kondisi Kosong)**<br><br>Saat aplikasi pertama kali dibuka, daftar tugas masih kosong. Sistem menggunakan `v-if` untuk mendeteksi kondisi ini dan menampilkan pesan *placeholder* "Belum ada tugas..." agar antarmuka tidak terlihat kaku. |
| <img src="https://github.com/user-attachments/assets/b9c1dc2e-881c-48f4-b918-e80426b28ce8" width="100%"> | **2. Menambah Data**<br><br>Pengguna dapat mengetik tugas di kolom input dan menekan tombol "Tambah". Data baru akan masuk ke dalam array dan dirender secara otomatis menggunakan `v-for`. Di sini terlihat 3 tugas telah berhasil ditambahkan dan disusun rapi ke bawah. |
| <img src="https://github.com/user-attachments/assets/31ddf8a4-5310-4e10-8144-b478e22c3988" width="100%"> | **3. Menghapus Data**<br><br>Setiap item memiliki tombol "Hapus" berwarna merah. Ketika diklik, fungsi `deleteTask` akan berjalan menghapus item tersebut dari memori. Tampilan daftar akan langsung menyesuaikan (berkurang) tanpa perlu me-refresh halaman browser. |

---

## 🧩 Penjelasan Singkat Kode

Berikut adalah penjelasan logika utama program:

#### a. State Management (`ref`)
Saya menggunakan **ref** sebagai wadah penyimpanan data yang "pintar". Berbeda dengan variabel biasa, jika data di dalam **ref** berubah, maka tampilan website akan otomatis diperbarui seketika tanpa perlu kita refresh halaman. Saya menggunakannya untuk menyimpan daftar tugas dan teks input.

#### b. Menambahkan Tugas (`addTask`)
Fungsi **addTask** bertugas untuk memproses data saat tombol "Tambah" ditekan. Cara kerjanya sederhana yaitu pertama, ia akan mengecek apakah kolom input sudah terisi (tidak kosong). Jika ada isinya, teks tersebut akan dimasukkan ke dalam daftar tugas, lalu kolom input akan dibersihkan kembali agar siap dipakai lagi.

#### c. Menampilkan Data (`v-for`)
Untuk menampilkan daftar tugas yang banyak, saya menggunakan konsep perulangan **v-for**. Fitur ini menyuruh Vue untuk mengambil data dari daftar tugas dan menampilkannya satu per satu ke layar secara otomatis sesuai jumlah tugas yang ada.

#### d. Binding Dua Arah (`v-model`)
**v-model** berfungsi sebagai jembatan penghubung antara kolom input (kotak ketik) dengan data di program. Apa yang kita ketik di layar akan langsung tersimpan di memori program. Sebaliknya, jika program menghapus data, tulisan di layar juga ikut hilang.

#### e. Menghapus Tugas (`deleteTask`)
Setiap tugas memiliki tombol hapus yang terhubung dengan fungsi **deleteTask**. Fungsi ini bekerja dengan cara mengambil nomor urut (index) dari tugas yang diklik, lalu membuang item tersebut dari daftar tugas utama.

---

