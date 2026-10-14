# Pengujian API Petstore Menggunakan Katalon Studio

## Deskripsi Proyek

Repository ini berisi proyek **Pengujian Otomatis API (API Testing)** menggunakan Katalon Studio dengan Swagger Petstore sebagai API sampel.

Pengujian berfokus pada validasi fungsi REST API, pemeriksaan kode status HTTP, validasi isi respons, pengujian positif dan negatif, serta pengujian alur menyeluruh (*End-to-End Testing*).

Proyek ini bertujuan untuk memastikan setiap endpoint memberikan respons yang sesuai dengan spesifikasi dan skenario pengujian.

## Tujuan Pengujian

- Memvalidasi fungsi REST API menggunakan Katalon Studio.
- Memeriksa kode status HTTP dan isi respons.
- Melakukan pengujian positif dan negatif.
- Memvalidasi data pada permintaan (*request*) dan respons (*response*).
- Menyusun alur pengujian API secara menyeluruh.
- Menggunakan Global Variables dan data dinamis jika diperlukan.
- Menjalankan pengujian melalui Test Suite dan menghasilkan laporan pengujian.

## Tools dan Teknologi

- **Katalon Studio** — Otomatisasi pengujian API.
- **REST API** — Pengujian komunikasi melalui HTTP.
- **Groovy** — Penulisan skrip dan assertion.
- **Swagger Petstore** — API sampel untuk pengujian.
- **Git dan GitHub** — Pengelolaan versi dan dokumentasi proyek.

## Base URL API

```text
https://petstore.swagger.io/v2
```

## Daftar Endpoint yang Diuji

| Metode HTTP | Endpoint | Fungsi |
|---|---|---|
| POST | `/pet` | Membuat data hewan baru |
| PUT | `/pet` | Memperbarui data hewan |
| GET | `/pet/{petId}` | Mengambil data hewan berdasarkan ID |
| DELETE | `/pet/{petId}` | Menghapus data hewan |

## Skenario Pengujian

### 1. Pengujian Positif

Pengujian dilakukan untuk memastikan endpoint berfungsi sesuai dengan hasil yang diharapkan.

- Memastikan data hewan berhasil dibuat.
- Memastikan data hewan yang tersedia dapat diperbarui.
- Memastikan data hewan dapat diambil menggunakan ID yang valid.
- Memastikan data hewan dapat dihapus.

### 2. Pengujian Negatif

Pengujian dilakukan untuk memeriksa penanganan kesalahan ketika API menerima permintaan atau data yang tidak valid.

- Memvalidasi respons ketika isi permintaan menggunakan format JSON yang tidak valid.
- Menguji respons ketika data penting tidak tersedia.
- Menguji respons ketika ID hewan tidak valid atau tidak ditemukan.
- Memvalidasi penanganan kesalahan terhadap data permintaan yang tidak sesuai.

**Catatan:** Kode status HTTP dan respons yang diharapkan harus disesuaikan dengan spesifikasi endpoint serta hasil pengujian aktual.

## Pengujian End-to-End (E2E)

Pengujian E2E dirancang untuk memvalidasi rangkaian proses pengelolaan data hewan dari awal hingga akhir.

1. **Create Pet** — Membuat data hewan melalui permintaan POST.
2. **Retrieve Pet** — Mengambil data yang telah dibuat melalui permintaan GET.
3. **Update Pet** — Memperbarui informasi hewan melalui permintaan PUT.
4. **Verify Update** — Memastikan perubahan data berhasil melalui permintaan GET.
5. **Delete Pet** — Menghapus data hewan melalui permintaan DELETE.
6. **Verify Deletion** — Memeriksa respons setelah data dihapus.

Alur ini digunakan untuk memastikan setiap operasi API dapat bekerja secara berurutan dalam satu rangkaian pengujian.

## Pendekatan Otomatisasi Pengujian

Proses pengujian menggunakan pendekatan berikut:

- Membuat objek REST Request di Katalon Studio.
- Mengelompokkan test case berdasarkan metode HTTP dan skenario pengujian.
- Menggunakan Global Variables atau data dinamis untuk mengurangi penggunaan data yang ditulis secara tetap (*hardcode*).
- Memvalidasi kode status HTTP dan isi respons menggunakan assertion.
- Menggunakan kembali objek permintaan jika sesuai.
- Menjalankan pengujian melalui Test Suite.
- Menganalisis log dan laporan untuk menemukan kegagalan pengujian.

## Cara Menjalankan Proyek

1. Unduh repository menggunakan perintah berikut:

   ```bash
   git clone https://github.com/4binn/katalon-petstore-api.git
   ```

2. Buka Katalon Studio.
3. Buka file proyek berekstensi `.prj`.
4. Periksa konfigurasi Base URL dan Global Variables.
5. Periksa objek REST Request dan test case yang tersedia.
6. Jalankan test case secara individual atau melalui Test Suite.
7. Periksa log eksekusi dan laporan hasil pengujian.

## Laporan Hasil Pengujian

Laporan pengujian digunakan untuk mengevaluasi:

- Jumlah test case yang berhasil dan gagal.
- Kesesuaian kode status HTTP aktual dengan hasil yang diharapkan.
- Hasil validasi isi respons.
- Kegagalan assertion dan pesan kesalahan.
- Hasil pengujian End-to-End.

## Pengembang

**4binn**

GitHub: https://github.com/4binn

## Lisensi dan Penggunaan

Proyek ini dibuat untuk keperluan pembelajaran dan latihan pengujian API. Swagger Petstore merupakan API sampel sehingga ketersediaan layanan dan hasil respons dapat berubah.

