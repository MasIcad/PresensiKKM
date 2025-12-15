# alternate-pres-kkmxlvi
# 📷 PANDUAN SISTEM PRESENSI QR - KKM XLVI
**Fakultas Teknik Universitas Brawijaya**

Dokumen ini berisi panduan teknis bagi panitia yang bertugas menjaga pos presensi. Mohon dibaca dengan teliti demi kelancaran arus 2.000+ peserta.

---

## 🔗 Link Penting
Simpan link berikut atau *bookmark* di browser HP/Laptop kalian:

* **Halaman Scan (Utama):** `alternate-pres-kkmxlvi.vercel.app`
* **Halaman Admin (Cek Data):** `alternate-pres-kkmxlvi.vercel.app/admin`

* **Halaman Scan (Cadangan):** `presensi-kkm.vercel.app`
* **Halaman Admin (Cek Data):** `presensi-kkm.vercel.app/admin`

---

## 🛠️ Persiapan Sebelum Jaga (Wajib!)

1.  **Baterai Penuh & Powerbank:**
    Menyalakan kamera browser memakan banyak baterai. Pastikan baterai HP/Laptop 100% sebelum mulai dan **selalu sedia Powerbank** di meja.
2.  **Koneksi Internet Cadangan:**
    Jangan hanya mengandalkan WiFi lokasi. Siapkan minimal satu HP dengan kuota data (Tethering) dari provider yang sinyalnya kuat di lokasi, jaga-jaga jika WiFi *down* karena overload.
3.  **Kecerahan Layar & Pencahayaan:**
    * Pastikan area meja presensi cukup terang (bantu pakai lampu belajar/senter HP jika malam).
    * Minta peserta menaikkan *brightness* HP mereka jika QR code di HP mereka sulit terbaca.

---

## 🚦 SOP Melakukan Scanning (Sangat Penting)

Sistem ini menggunakan *Cloud Queue* agar data tidak tabrakan. Ikuti langkah ini agar tidak macet:

1.  Buka Link Scanner.
2.  Izinkan akses kamera (**Allow**).
3.  Arahkan kamera ke QR Code peserta.
4.  **TUNGGU HINGGA MUNCUL TULISAN HIJAU.**
    > ✅ *"Presensi Berhasil! Terima Kasih [Nama]"*
5.  **JANGAN Scan Orang Berikutnya Sebelum Hijau!**
    * Proses ini butuh waktu 0.5 - 2 detik.
    * Jika kalian scan beruntun secepat kilat (tanpa jeda), sistem akan antre dan berpotensi error/timeout.
    * **Kunci:** *Scan -> Tunggu Hijau -> Next.*

---

## 💻 Akses Halaman Admin

Untuk panitia yang bertugas memantau data masuk atau mengecek peserta yang bermasalah.

* **URL:** `.../admin`
* **ID Panitia:** `kkm2025`
* **Password:** `teknikub2025kkmxlvi`

Halaman admin digunakan untuk memantau traffic dan melakukan rekap presensi panitia KKM. Terdapat beberapa hal yang perlu dipahami oleh Penanggung Jawab Presensi, sebagai berikut:
* **Untuk link utama:**
* Hanya terdapat 1 menu yang digunakan untuk mengakses presensi panitia KKM. Penanggung jawab dapat melakukan rekapitulasi presensi melalui link tersebut dan tidak menyebarluaskan link presesnsi, beserta ID dan Password halaman administrasi.
* Penanggung jawab perlu melakukan rekap pada spreadsheet atau excel yang berbeda untuk setiap harinya, dengan menggunakan CTRL + C dan CTRL + V.
* Setelah data dipindahkan, Penanggung Jawab perlu melakukan reset spreadsheet dengan cara menghapus data yang ada di dalamnya untuk mengurangi kesalahan program dalam membaca dan menulis data.
* **Untuk link alternate:**
* Terdapat 2 menu, yakni: "Buka Data Presensi" dan "Buka Data Rekapitulasi".
* Penanggung jawab wajib melakukan reset atau penghapusan data presensi pada 2 menu terseubt setiap 
*Gunakan halaman ini untuk membuka Google Spreadsheet secara langsung tanpa perlu login Gmail.*

---

## ⚠️ Logika Waktu (Sesi)

Sistem otomatis menentukan sesi berdasarkan jam scan (WIB):
* **06:00 - 11:59** ➔ Sesi **PAGI**
* **12:00 - 14:59** ➔ Sesi **SIANG**
* **15:00 - 18:00** ➔ Sesi **SORE**
* **00:00 - 05:59** ➔ Status **TERLAMBAT**

*(Peserta tidak bisa absen 2x di sesi yang sama. Jika mencoba, akan muncul pesan Error Merah).*

---

## ❓ Troubleshooting (Kendala & Solusi)

| Masalah | Solusi Cepat |
| :--- | :--- |
| **Layar Kamera Blank/Hitam** | Refresh halaman browser. Pastikan izin kamera di-set ke "Allow". Cek apakah browser memblokir kamera. |
| **Muncul Pesan Error Merah** | Cek internet kalian. Jika internet aman tapi masih error, minta peserta tunjukkan QR lagi (mungkin QR rusak/terpotong). |
| **Internet Lemot/RTO** | Segera ganti ke Tethering HP panitia. Jangan paksa pakai WiFi jika sudah lemot. |
| **Salah Satu Device Error** | Tenang. Pindah ke meja sebelah. Sistem mendukung *Multiple Device* (banyak HP scan barengan aman). |

---

**Semangat Bertugas Panitia KKM XLVI!**
*#123TEKNIK #KITASATUBRAWIJAYA