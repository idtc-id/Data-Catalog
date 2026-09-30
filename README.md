# Katalog Data Sensing DT

**Pokja 2 — Data, Teknologi, Implementasi**

Katalog metadata sumber data (sensor/IoT, geospasial, BIM, ERP, cuaca, dsb.) yang tersedia atau
relevan untuk pilot project Digital Twin IDTC. Repo ini menyimpan **metadata sumber data**
(nama, pemilik, cara akses, klasifikasi sensitivitas), **bukan data mentahnya** — lihat
[kebijakan data](https://github.com/idtc-id/pokja2-handbook/blob/main/docs/04-kebijakan-data.md)
untuk aturan penyimpanan data mentah.

## Cara menambah entri baru

**Tidak perlu tahu Git atau menulis JSON.** Isi formulir:

1. Buka tab **Issues** → **New issue** → pilih **📡 Tambah entri Katalog Data Sensing**.
2. Isi formulirnya, lalu **Create**.
3. Sistem otomatis membuatkan Pull Request berisi entri Anda dalam beberapa detik.
4. Pengurus Pokja 2 menelaah dan menggabungkannya — entri Anda resmi masuk katalog begitu
   Pull Request itu digabungkan.

## Cara memperbarui atau menghapus entri

Setiap entri adalah satu berkas `data/DS-XXXX.json`. Perbarui lewat cara yang sama seperti
mengubah dokumen di repo IDTC lain (lihat modul
[M6 di `panduan-github`](https://github.com/idtc-id/panduan-github/blob/main/modul/M6-mengubah-dokumen-lewat-browser.md)):
buka berkasnya → ikon pensil ✏️ → ubah → **Commit changes...** → **Propose changes** →
**Create pull request**.

> Catatan: tabel di bawah dan `data/index.json` dibangun ulang otomatis setiap ada entri **baru**
> lewat formulir. Mengedit berkas entri yang sudah ada secara langsung tidak memicu pembaruan
> tabel ini — perbarui juga baris yang relevan di tabel bila field yang ditampilkan (Nama Data,
> Kategori, Klasifikasi) ikut berubah.

## Skema data

Lihat [`docs/skema.md`](docs/skema.md) untuk penjelasan lengkap setiap kolom.

## Daftar entri

<!-- KATALOG:START -->
| ID | Nama Data | Kategori | Klasifikasi | Kontributor |
|---|---|---|---|---|
| DS-0005 | [Inspeksi Menara ATC Bandara Buchanan Field (Concord) — sampel Esri](data/DS-0005.json) | Data Model Visual & Geospasial | Publik | @geoholix |
| DS-0004 | [Survei Termal Pabrik Aspal Heidelberg Materials (Berkeley) — sampel Esri](data/DS-0004.json) | Data Model Visual & Geospasial | Publik | @geoholix |
<!-- KATALOG:END -->

*(Tabel ini kosong sampai entri pertama diajukan lewat formulir.)*

## Lisensi

Metadata dalam katalog ini dilisensikan di bawah **Creative Commons Attribution 4.0
International (CC BY 4.0)** — atribusi kepada *Indonesia Digital Twin Community (IDTC) —
Pokja 2*. Data yang dirujuk oleh entri katalog mengikuti lisensi/izin pemiliknya masing-masing,
bukan lisensi ini.
