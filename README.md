# Geosiana QGIS Pack V2

Folder ini adalah output tunggal dan paket siap-upload. Semua aset penting dikumpulkan di satu tempat agar tidak tercecer.

## Cara Mendapatkan Paket

Pengguna repo publik nanti bisa memilih salah satu cara ini:

### 1. Clone dengan Git

```bash
git clone git@github.com:dhanyyudi/geosiana-qgis-symbol-pack.git
cd geosiana-qgis-symbol-pack
```

### 2. Download ZIP dari GitHub

1. Buka halaman repo GitHub.
2. Klik `Code`.
3. Pilih `Download ZIP`.
4. Extract ZIP, lalu buka folder hasil extract.

## Entry Point Yang Perlu Dibuka Pengguna

- `README.md`
  Panduan utama paket.
- `style-packs/geosiana-curated-v2-embedded.xml`
  Pack awal yang paling aman untuk import ke `Style Manager`.
- `style-packs/geosiana-full-embedded.xml`
  Pack lengkap semua marker SVG.
- `style-packs/geosiana-line-fill-starter.xml`
  Pack starter untuk symbol `line` dan `polygon`.
- `previews/`
  Preview kontak simbol per font.
- `test-cases/test-cases.html`
  Preview lokal untuk cek point, line, dan polygon sebelum dipakai di QGIS.
- `catalogs/geosiana-curated-v2.csv`
  Daftar simbol kurasi dan tag.
- `catalogs/geosiana-semantic-map.csv`
  Kamus nama semantik simbol.
- `catalogs/geosiana-style-recipes.csv`
  Recipe sumber line/fill yang dipakai untuk starter pack.

## Akses Cepat Setelah Download

Kalau pengguna baru pertama kali membuka repo ini, urutan yang paling aman:

1. Baca `README.md`.
2. Buka folder `previews/` untuk melihat simbol yang tersedia.
3. Import `style-packs/geosiana-curated-v2-embedded.xml` ke `Style Manager` QGIS.
4. Jika butuh symbol garis dan area, import juga `style-packs/geosiana-line-fill-starter.xml`.
5. Jika ingin mengecek hasil cepat di luar QGIS, buka `test-cases/test-cases.html` di browser.

## Struktur Folder

- `svg/`: seluruh marker SVG hasil konversi dari font Geosiana.
- `style-packs/`: file `.xml` untuk import langsung ke `Style Manager` QGIS.
- `catalogs/manifests/`: daftar lengkap mapping glyph ke file SVG.
- `catalogs/geosiana-curated-v2.csv`: daftar simbol terkurasi v2 beserta kategori dan tag.
- `catalogs/geosiana-semantic-map.csv`: kamus penamaan semantik yang dipakai untuk memperbaiki nama simbol di pack XML.
- `catalogs/geosiana-style-recipes.csv`: resep sumber line/fill yang dipakai untuk starter pack non-marker.
- `previews/`: contact sheet untuk browsing simbol per font.
- `test-cases/`: preview tiga skenario uji point, line, polygon.

## Isi Pack

- Total SVG: `592`
- Full import pack: `style-packs/geosiana-full-embedded.xml`
- Curated import pack v2: `style-packs/geosiana-curated-v2-embedded.xml`
- Starter line/fill pack: `style-packs/geosiana-line-fill-starter.xml`
- Full pack memakai nama semantik untuk glyph yang sudah dikenali, dan fallback netral untuk glyph yang belum dipetakan.
- Starter line/fill pack dibangun dari recipe legenda LapakGIS dengan pendekatan `Simple line`, `Marker line`, `Simple fill`, dan `Point pattern fill` yang konservatif.

## Cara Import ke QGIS

1. Buka `Settings > Style Manager`.
2. Klik `Import/Export > Import Item(s)`.
3. Pilih `style-packs/geosiana-curated-v2-embedded.xml` jika ingin mulai dari subset yang sudah dikategorikan.
4. Pilih `style-packs/geosiana-line-fill-starter.xml` jika Anda ingin langsung mencoba starter symbol line dan polygon.
5. Jangan centang `Do not import embedded tags` jika ingin tag seperti `batas-administrasi`, `jalan`, `hidrologi`, atau `untuk-line` ikut masuk.
6. Setelah import, buka panel `Tags` untuk memfilter simbol.

## Paket Ini Berisi Apa

- Aset simbol sudah langsung tersedia di repo ini.
- Pengguna tidak perlu menginstall font TTF asli untuk memakai pack XML yang sudah embedded.
- Untuk pemakaian normal, cukup download repo ini lalu import file XML dari folder `style-packs/`.

## Style Manager Walkthrough

Gunakan urutan ini saat membuka pack di QGIS:

```text
Settings
  -> Style Manager
    -> Import/Export
      -> Import Item(s)
        -> pilih file XML
        -> pastikan tag ikut diimpor
        -> import
```

### Opsi Pack

- `style-packs/geosiana-curated-v2-embedded.xml`
  Pilihan awal yang paling aman. Simbol sudah diberi nama yang lebih jelas dan dibagi ke kategori seperti `batas-administrasi`, `jalan`, `hidrologi`, `vegetasi`, dan `transportasi`.
- `style-packs/geosiana-full-embedded.xml`
  Dipakai kalau Anda ingin seluruh simbol hasil ekspor masuk semua ke `Style Manager`.
- `style-packs/geosiana-line-fill-starter.xml`
  Dipakai untuk mencoba symbol `line` dan `polygon` yang sudah jadi, tanpa harus merakit semuanya manual dari marker pack.

### Langkah Detail

1. Buka `Settings > Style Manager`.
2. Pada panel atas, pastikan Anda sedang melihat tab `Symbols`.
3. Klik `Import/Export` di kiri bawah.
4. Pilih `Import Item(s)`.
5. Pada dialog import:
   - pilih sumber file XML dari folder `style-packs/`
   - mulai dari `geosiana-curated-v2-embedded.xml` jika ingin yang lebih rapi
6. Periksa opsi import:
   - biarkan item diimpor sebagai symbol
   - jangan centang `Do not import embedded tags`
7. Jalankan import.
8. Setelah selesai, lihat panel `Tags` di sisi kiri `Style Manager`.
9. Klik tag seperti:
   - `batas-administrasi`
   - `jalan`
   - `hidrologi`
   - `permukiman`
   - `fasilitas-umum`
   - `vegetasi`
   - `transportasi`
   - `utilitas`
   - `fauna`
10. Untuk filter berbasis cara pakai, gunakan tag:
   - `untuk-point`
   - `untuk-line`
   - `untuk-polygon`
11. Jika mengimpor `geosiana-line-fill-starter.xml`, cari nama seperti `Batas Negara`, `Jalan`, `Sungai`, `LT Permukiman`, atau `LTT Sawah`.

### Hasil Yang Harus Terlihat

Kalau import berhasil, biasanya Anda akan melihat:

- nama simbol yang lebih manusiawi seperti `Jalan - Chevron Tipis` atau `Vegetasi - Konifer`
- tag muncul di panel kiri `Style Manager`
- simbol bisa dipreview tanpa perlu install font TTF asli

### Contoh Cara Pakai Setelah Import

#### 1. Point

1. Buka `Layer Properties > Symbology`.
2. Untuk layer titik, pilih simbol dari library hasil import.
3. Cari tag `untuk-point` atau kategori seperti `fasilitas-umum`, `permukiman`, atau `transportasi`.

#### 2. Line

1. Untuk layer garis, tambahkan symbol layer `Marker line`.
2. Pada sub-symbol marker, pilih simbol dari hasil import.
3. Cari tag `untuk-line`, `jalan`, `batas-administrasi`, atau `utilitas`.
4. Aktifkan `Rotate marker to follow line direction` bila perlu.

#### 3. Polygon

1. Untuk layer polygon, gunakan pendekatan:
   - `SVG fill`, atau
   - `Point pattern fill`
2. Pilih simbol dengan tag `untuk-polygon` atau kategori `vegetasi` / `hidrologi`.

### Troubleshooting Cepat

- Simbol tidak muncul setelah import:
  cek apakah Anda benar-benar mengimpor file `.xml`, bukan folder `svg/`.
- Tag tidak muncul:
  ulangi import dan pastikan `Do not import embedded tags` tidak dicentang.
- Simbol line terasa kurang pas:
  starter pack ini memang konservatif; pakai sebagai baseline lalu fine-tune width, interval, atau warna di QGIS.
- Hasil web berbeda saat `qgis2web`:
  uji dulu dengan sample di folder `test-cases/`, lalu sederhanakan line/polygon symbol bila perlu.

## Catatan

- Kategori `batas-administrasi` dan `jalan` di curated pack v2 difokuskan pada simbol yang paling masuk akal sebagai dekorator line symbol.
- Untuk style garis final, tetap kombinasikan marker ini dengan line style native QGIS seperti `Simple line`, `Marker line`, atau `Hashed line`.
- Karena pack XML memakai SVG embedded base64, file ini tidak bergantung pada font asli saat diimpor ke QGIS.

## Attribution

- File TTF sumber pada folder `Marker_v1.0/` diolah dari referensi publik Lapak GIS:
  [Style Simbol Peta Praktis sesuai Teknis Penyajian Peta](https://www.lapakgis.com/2020/04/style-simbol-peta-praktis-sesuai-teknis.html)
- Pada artikel tersebut disebutkan bahwa template style dibuat oleh tim Geosiana dan dibagikan melalui tulisan Lapak GIS tertanggal 19 April 2020.
- Paket ini tidak mengubah provenance sumber; folder ini hanya mengemas ulang aset TTF menjadi SVG dan pack import QGIS yang lebih mudah dipakai untuk workflow QGIS dan qgis2web.
