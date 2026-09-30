# Skema Katalog Data Sensing

Diturunkan dari `pokja2-handbook/docs/Katalog Data Sensing DT.xlsx` (rancangan awal, dengan
catatan telaah yang sudah diselesaikan — lihat bagian "Perubahan dari rancangan awal" di bawah).

| Atribut | Tipe | Pilihan / Format | Wajib diisi? |
|---|---|---|---|
| **ID Data** | Otomatis | `DS-0001`, `DS-0002`, ... — dari nomor issue, bukan diisi manual | — |
| **Nama Data** | Teks | bebas | Ya |
| **Pemilik Data** | Teks | bebas — instansi/organisasi pemilik | Ya |
| **Gambar Pratinjau (Thumbnail)** | Gambar | seret/tempel satu gambar ke kotak formulir — dipakai sebagai thumbnail kartu di halaman katalog | Tidak |
| **Klasifikasi Sensitivitas Data** | Dropdown | Publik, Internal, Confidential, Restricted | Ya |
| **Kategori Data** | Dropdown | Data Sensor & Aktuator (IoT) · Data Model Visual & Geospasial · Data Operasional & Bisnis · Data Kontekstual & Lingkungan · Data Statistik (Kependudukan & Ekososbud) | Ya |
| **Tipe Data** | Dropdown | Time-series/Telemetry, Spatial/GIS, 3D/BIM Model, Operational/ERP, Weather API | Ya |
| **Protokol Komunikasi** | Dropdown | MQTT, Kafka, HTTP REST API, OPC UA, WebSockets, Tidak berlaku | Tidak |
| **Endpoint / Koneksi** | Teks | URL atau detail koneksi (jangan tempel kredensial) | Tidak |
| **Metode Autentikasi / Security** | Dropdown | OAuth2, API Key, X.509 Certificate, None / Open Access (Tidak ada / Publik) | Ya |
| **Karakter Update Data** | Dropdown | Real Time, Per Jam, Per Hari, Per Minggu, Per Bulan, Per Tahun, Statis | Ya |
| **Retensi Data** | Dropdown | Selamanya, 1 Tahun, Lainnya (jelaskan di catatan) | Ya |
| **Format Data** | Teks bebas | mis. JSON, CSV, Shapefile, IFC, Parquet | Ya |
| **Dokumen Terkait** | Teks/tautan | tempel tautan atau seret berkas ke kotak formulir | Tidak |
| **Catatan tambahan** | Teks bebas | keterangan lain yang tidak tertampung kolom di atas | Tidak |
| **Kontributor (username GitHub)** | Otomatis | diambil dari akun yang membuka issue, bukan diisi manual | — |

## Perubahan dari rancangan awal

Rancangan di berkas Excel sempat ditelaah dan meninggalkan empat catatan terbuka. Semuanya
sudah diterapkan pada skema final di atas:

1. **Kategori Data** — opsi lama (`Real Time (IOT & Telemetri)`) tumpang tindih dengan kolom
   Karakter Update Data. Diganti lima kategori yang diusulkan penelaah: Sensor & Aktuator (IoT),
   Model Visual & Geospasial, Operasional & Bisnis, Kontekstual & Lingkungan, Statistik
   (Kependudukan & Ekososbud).
2. **Metode Autentikasi** — ditambahkan opsi *None / Open Access* supaya data publik tanpa
   autentikasi tidak memaksa pengisi memilih opsi yang tidak sesuai.
3. **Format Data** — diubah dari dropdown menjadi teks bebas, karena format data terlalu
   beragam untuk dibatasi daftar tetap.
4. **Kontributor** — diganti dari "Nama Member" menjadi username GitHub, diambil otomatis dari
   akun yang mengirim formulir (bukan diketik manual), supaya selalu akurat dan konsisten
   dengan identitas GitHub yang dipakai di seluruh organisasi `idtc-id`.

Tambahan di luar rancangan awal: **Gambar Pratinjau (Thumbnail)**, memanfaatkan kemampuan
bawaan GitHub Issue Form untuk mengunggah gambar yang diseret/ditempel ke kotak formulir —
tautan gambarnya diambil dari markdown yang disisipkan GitHub sendiri (`![...](url)`), tanpa
perlu server penyimpanan gambar terpisah.

## Format penyimpanan

Setiap entri adalah satu berkas `data/DS-XXXX.json`. Contoh:

```json
{
  "idData": "DS-0001",
  "namaData": "Sensor Curah Hujan DAS Ciliwung",
  "pemilikData": "BMKG",
  "gambarUrl": "",
  "klasifikasiSensitivitas": "Publik",
  "kategoriData": "Data Sensor & Aktuator (IoT)",
  "tipeData": "Time-series/Telemetry",
  "protokolKomunikasi": "HTTP REST API",
  "endpoint": "https://api.contoh.id/curah-hujan",
  "metodeAutentikasi": "API Key",
  "karakterUpdate": "Per Jam",
  "retensiData": "Selamanya",
  "formatData": "JSON",
  "dokumenTerkait": "",
  "catatan": "",
  "kontributorUsernameGithub": "contoh-username",
  "dibuatPada": "2026-09-30T10:00:00Z",
  "issue": "https://github.com/idtc-id/Data-Catalog/issues/1"
}
```

`data/index.json` adalah kumpulan seluruh entri dalam satu berkas — dibangun ulang otomatis
setiap ada entri baru, memudahkan aplikasi lain (situs, dashboard) membaca seluruh katalog
sekali ambil tanpa perlu memanggil API GitHub berkali-kali.
