# PresensiKKM
# 📱 Sistem Presensi QR Code

Sistem presensi digital menggunakan QR Code, terintegrasi otomatis dengan Google Sheets.

---

## 📢 PANDUAN UNTUK PESERTA (Bisa dicetak & ditempel di meja)

**Cara Melakukan Presensi:**
1.  **Siapkan QR Code** Anda (dari HP atau kartu ID).
2.  **Arahkan QR Code** ke kamera laptop yang tersedia.
3.  Tunggu hingga layar berkedip dan muncul pesan:
    * ✅ **HIJAU:** "Terima Kasih [Nama Anda]" (Berhasil).
    * ❌ **MERAH:** "Maaf, Anda sudah presensi" (Data ganda).
4.  Jika berhasil, silakan mengambil konsumsi.

---

## 👮 PANDUAN UNTUK OPERATOR / PANITIA JAGA

**Persiapan Sebelum Acara:**
1.  **Internet Wajib Stabil:** Pastikan laptop terkoneksi WiFi/Hotspot yang kencang.
2.  **Cek Cahaya:** Jangan biarkan kamera menghadap cahaya silau (backlight). Pastikan wajah/QR peserta terang.
3.  **Aktifkan Sistem:** Hubungi tim IT untuk memastikan Workflow n8n sudah "Active".

**Cara Mengatasi Masalah (Troubleshooting):**
* **Masalah:** Muncul tulisan *"Server Error / Cek Koneksi"* terus-menerus.
    * **Solusi:** Cek internet laptop. Jika internet aman, tekan tombol **F5** (Refresh) pada browser.
* **Masalah:** Kamera tidak mau scan (diam saja).
    * **Solusi:** Refresh halaman (F5). Pastikan tidak ada aplikasi lain (seperti Zoom/Meet) yang menggunakan kamera.
* **Masalah:** Muncul pesan Merah *"Maaf Anda Sudah Presensi"*.
    * **Solusi:** Jelaskan pada peserta bahwa data mereka **sudah masuk** sebelumnya. Tidak perlu scan ulang.

---

## 🛠️ DOKUMENTASI TEKNIS (Untuk Admin/Developer)

Sistem ini menggunakan **n8n** sebagai backend dan **Google Sheets** sebagai database.

### 1. Konfigurasi n8n (Wajib Diperhatikan)
Jika membuat ulang workflow, pastikan settingan ini benar agar tidak Error CORS:

* **Node Webhook (Start):**
    * Method: `POST`
    * Respond: `Using 'Respond to Webhook' Node`
    * Authentication: `None`
* **Node Respond to Webhook (End):**
    * Respond With: `JSON`
    * **Response Code:** KOSONGKAN (Jangan diisi angka).
    * **Response Headers (Penting!):**
        * Name: `Access-Control-Allow-Origin`
        * Value: `*`
    * **Response Body (Format JSON):**
        ```json
        {
           "valid": true,
           "nama": "{{ $json.nama }}",
           "message": "Pesan sukses/gagal di sini"
        }
        ```

### 2. Deployment (Production)
* Pastikan URL di file HTML menggunakan **Production URL** (tanpa akhiran `-test`).
    * Contoh Benar: `.../webhook/presensi-qr`
    * Contoh Salah: `.../webhook-test/presensi-qr`
* **PENTING:** Tombol **"Active"** di pojok kanan atas n8n harus menyala **HIJAU** agar sistem berjalan 24 jam.

---
*Dibuat untuk keperluan Event [Nama Acara Anda]*