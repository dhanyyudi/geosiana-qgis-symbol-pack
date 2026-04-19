# Geosiana QGIS Symbol Pack

Paket ini berisi simbol SVG untuk QGIS yang dikonversi dari font marker Geosiana, lalu dikemas ulang agar lebih mudah dipakai di `Style Manager`, lebih mudah dicari lewat nama dan tag, dan lebih aman dipakai ulang pada workflow QGIS modern.

Pengguna tidak perlu menginstal font TTF asli untuk memakai pack XML yang ada di repo ini.

## Unduh Paket

Pilihan paling mudah:

- Buka halaman [Release v1.0.0](https://github.com/dhanyyudi/geosiana-qgis-symbol-pack/releases/tag/v1.0.0)
- Unduh asset `geosiana-qgis-symbol-pack-v1.0.0.zip`
- Jika perlu verifikasi file unduhan, unduh juga `geosiana-qgis-symbol-pack-v1.0.0.sha256`

Halaman semua release:

- [Releases](https://github.com/dhanyyudi/geosiana-qgis-symbol-pack/releases)

Pilihan lain:

- Download ZIP langsung dari halaman repo
- Clone repo ini dengan Git

```bash
git clone git@github.com:dhanyyudi/geosiana-qgis-symbol-pack.git
cd geosiana-qgis-symbol-pack
```

## Mulai Cepat

Kalau baru pertama kali memakai paket ini, urutan paling aman:

1. Buka folder `previews/` untuk melihat simbol yang tersedia.
2. Di QGIS, buka `Settings > Style Manager`.
3. Pilih `Import/Export > Import Item(s)`.
4. Import `style-packs/geosiana-curated-v2-embedded.xml`.
5. Pastikan opsi `Do not import embedded tags` tidak dicentang.
6. Setelah import, cari simbol lewat panel `Tags` atau kolom pencarian.

Jika Anda juga butuh simbol garis dan polygon siap pakai, import tambahan:

- `style-packs/geosiana-line-fill-starter.xml`

## Pilih Pack Yang Mana

### 1. Curated Pack

File:

- `style-packs/geosiana-curated-v2-embedded.xml`

Cocok untuk:

- penggunaan harian
- pencarian simbol yang lebih cepat
- pengguna yang ingin simbol sudah diberi nama dan tag tematik

Isi utama:

- simbol titik terpilih
- dekorator marker untuk line
- nama simbol yang lebih mudah dibaca
- tag seperti `jalan`, `batas-administrasi`, `hidrologi`, `vegetasi`, `fasilitas-umum`

### 2. Full Pack

File:

- `style-packs/geosiana-full-embedded.xml`

Cocok untuk:

- pengguna yang ingin semua hasil ekstraksi SVG
- eksplorasi simbol lengkap
- pencarian glyph yang belum masuk subset kurasi

Isi utama:

- seluruh simbol marker hasil konversi
- nama semantik untuk glyph yang sudah dikenali
- fallback name netral untuk glyph yang belum dipetakan

### 3. Line and Fill Starter Pack

File:

- `style-packs/geosiana-line-fill-starter.xml`

Cocok untuk:

- pengguna yang ingin langsung mencoba symbol garis dan area
- kebutuhan awal untuk `batas administrasi`, `jalan`, `sungai`, `penggunaan lahan`, dan `non-terbangun`

Isi utama:

- symbol `line`
- symbol `fill`
- pendekatan konservatif berbasis `Simple line`, `Marker line`, `Simple fill`, dan `Point pattern fill`

## Cara Import ke QGIS

1. Buka `Settings > Style Manager`.
2. Pastikan Anda berada di tab `Symbols`.
3. Klik `Import/Export`.
4. Pilih `Import Item(s)`.
5. Pilih salah satu file XML dari folder `style-packs/`.
6. Jangan centang `Do not import embedded tags`.
7. Jalankan import.
8. Gunakan kolom pencarian atau panel `Tags` untuk menemukan simbol.

Contoh kata kunci yang bisa dicari:

- `Masjid`
- `Kantor Gubernur`
- `Jalan`
- `Batas Negara`
- `Sungai`
- `LT Permukiman`

## Struktur Folder

- `style-packs/`
  File XML yang bisa langsung diimport ke `Style Manager` QGIS.
- `svg/`
  Seluruh simbol SVG hasil konversi.
- `previews/`
  Contact sheet untuk melihat isi simbol per font.
- `catalogs/`
  Daftar simbol, semantic map, recipe line/fill, dan manifest hasil ekspor.
- `test-cases/`
  Contoh uji point, line, dan polygon.

## Isi Paket

- Total SVG: `592`
- Curated pack: `style-packs/geosiana-curated-v2-embedded.xml`
- Full pack: `style-packs/geosiana-full-embedded.xml`
- Starter line/fill pack: `style-packs/geosiana-line-fill-starter.xml`

## Catatan Pemakaian

- Untuk simbol titik, mulai dari `curated` pack.
- Untuk simbol garis, starter pack ini bisa langsung dipakai, tetapi tetap layak dituning ulang sesuai skala peta.
- Untuk simbol polygon, starter pack memberi baseline yang cukup baik, terutama untuk kategori penggunaan lahan dan non-terbangun.
- Untuk workflow `qgis2web`, tetap uji hasil render akhir di browser karena desktop QGIS dan output web tidak selalu identik.
- File XML pada repo ini memakai SVG embedded base64, jadi tidak bergantung pada font asli saat diimpor ke QGIS.

## File Yang Paling Berguna

- `previews/`
  Untuk melihat isi simbol dengan cepat.
- `style-packs/geosiana-curated-v2-embedded.xml`
  Entry point terbaik bagi sebagian besar pengguna.
- `style-packs/geosiana-line-fill-starter.xml`
  Entry point untuk simbol line dan area.
- `catalogs/geosiana-curated-v2.csv`
  Daftar simbol kurasi dan tag.
- `catalogs/geosiana-semantic-map.csv`
  Kamus nama semantik simbol.
- `catalogs/geosiana-style-recipes.csv`
  Recipe sumber untuk starter line/fill pack.
- `test-cases/test-cases.html`
  Preview lokal untuk memeriksa point, line, dan polygon.

## Attribution

- Referensi sumber TTF:
  [Style Simbol Peta Praktis sesuai Teknis Penyajian Peta - Lapak GIS](https://www.lapakgis.com/2020/04/style-simbol-peta-praktis-sesuai-teknis.html)
- Pada artikel tersebut disebutkan bahwa template style dibuat oleh tim Geosiana.
- Repo ini mengemas ulang aset tersebut menjadi SVG dan pack import QGIS yang lebih mudah dipakai untuk workflow `Style Manager` dan penggunaan ulang di QGIS.
