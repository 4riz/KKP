# Dari Data Menuju Informasi Strategis

**Tata Kelola Data untuk Mendukung Pengambilan Keputusan di Sektor Kelautan dan Perikanan**

> Pelatihan Pengembangan Kompetensi 20 JP – Sesi 6 · Jumat, 16 Oktober 2026  
> Narasumber: **Akbar Rizki, S.Stat., M.Si.** — Program Studi Statistika dan Sains Data, IPB University  
> Penyelenggara: **Pusat Data dan Informasi, Kementerian Kelautan dan Perikanan Republik Indonesia**

![Poster Pelatihan KKP](poster.jpg)

## Materi dan hasil analisis

**[Buka materi HTML (kode, tabel, grafik, dan hasil analisis)](KKP.html)** · **[Lihat kode R Markdown](KKP.Rmd)**

Repository ini menyajikan materi pelatihan beserta hasil analisis yang sudah dihitung, antara lain:

- **Entry, eksplorasi, dan coding data:** perapian nama variabel, pemeriksaan struktur data, pengkodean jenis usaha.
- **Filter dan agregasi:** pemfilteran berdasarkan wilayah/komoditas dan rekapitulasi produksi menurut provinsi.
- **Penggabungan data:** penambahan baris, penggabungan variabel, dan *master table lookup*.
- **Anomali database:** ilustrasi anomali penyisipan, peremajaan, dan penghapusan.
- **Dashboard informasi strategis:** grafik sebar volume–nilai produksi, *lollipop*, *heatmap*, *100% stacked bar*, dan Pareto.

Tabel, grafik, angka ringkasan, dan interpretasi **tetap dapat dibaca langsung pada `KKP.html`**, termasuk sebagian cuplikan baris data dan hasil rekap interaktif. **File dataset mentah lengkap tidak dibagikan lewat repository ini.**

## Akses dataset melalui portal resmi

**Peserta diminta mengunduh data sendiri dari sumber resmi**, bukan dari GitHub:

1. Kunjungi **[Portal Satu Data KKP](https://portaldata.kkp.go.id/)**.
2. Buka menu statistik produksi perikanan, atau mulai dari **[Tabel Dinamis Produksi Perikanan](https://portaldata.kkp.go.id/portals/data-statistik/prod-ikan/tbl-dinamis?filter_utama=1&tahun=2024)**.
3. Pilih kategori/jenis perikanan, tahun, wilayah, dan atribut yang dibutuhkan; gunakan fasilitas unduh di portal bila tersedia.
4. Periksa apakah hasil unduhan memiliki kolom dan satuan yang sesuai dengan contoh, lalu sesuaikan kode import bila diperlukan.

**Catatan kesesuaian:** Dataset yang digunakan untuk menghasilkan HTML asli memiliki kolom seperti `tahun`, `provinsi`, `kab_kota`, `kelompok_ikan`, `jenis_ikan`, `jenis_usaha`, `volume_ton`, dan `nilai_rp_juta`. Hasil unduhan di halaman portal dapat memiliki nama kolom, kelengkapan atribut, satuan, dan periode yang berbeda. **Tautan tabel dinamis adalah pintu masuk resmi, bukan jaminan unduhan tersebut identik dengan dataset pada paparan.**

## Menjalankan kode R secara lokal

1. Install R, RStudio, dan paket yang disebutkan di dalam `KKP.Rmd` (`tidyverse`, `janitor`, `knitr`, `scales`, `DT`, `skimr`, `ggrepel`, dan `rmdformats`).
2. Unduh data dari portal resmi KKP ke komputer Anda.
3. Sesuaikan kode berikut dalam `KKP.Rmd` dengan lokasi/nama file lokal:

   ```r
   file_path <- "Produksi Perikanan Tangkap.csv"
   data_raw <- readr::read_csv(file_path, skip = 1)
   ```

4. Periksa format CSV (termasuk baris header dan pemisah angka). Sesuaikan `skip`, jenis kolom, satuan, dan nama peubah; jalankan blok kode berurutan.
5. *Knit* `KKP.Rmd` jika data yang diperlukan dan paket R sudah tersedia.


**Sumber data:** Kementerian Kelautan dan Perikanan RI — [Portal Satu Data KKP](https://portaldata.kkp.go.id/).  
**Pemateri:** Akbar Rizki, S.Stat., M.Si. — IPB University.
