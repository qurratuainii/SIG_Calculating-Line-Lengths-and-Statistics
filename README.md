# SIG_Calculating-Line-Lengths-and-Statistics

*Tutorial Calculating Line Lengths and Statistics

1. Download terlebih dahulu file ne_10m_railroads_north_america.zip

2. Cari file ne_10m_railroads_north_america.zip yang telah di download. Lalu seret file ne_10m_railroads_north_america.shp ke kanvas atau double click (*Gambar 1*)

3. Akan tampil layer baru di panel Layers. Kita akan melihat layer tersebut memiliki garis yang mewakili jalur kereta api untuk seluruh Amerika Utara. Selanjutnya kita akan hitung panjang setiap fitur garis. Buka Processing lalu klik Toolbox (*Gambar 2*)

4. Cari dan temukan Vector geometry lalu Add geometry attributes. Lalu klik dua kali untuk meluncurkannya (*Gambar 3*)

5. Pada Add Geomrtry Attributes dialog, pilih ne_10m_railroads_north_america sebagai lapisan input. Sistem Referensi KOordinat lapisan input adalah EPSG:4326 WGS84. Ini adalah CRS Geografis dengan Latitude dan Longitude sebagai koordinat, WGS84 sebagai ellipsoid dan derajat sebagai unit. Karena lintang dan bujur tidak memiliki panjang standar, kita tidak dapat mengukur jarak atau area secara akurat menggunakan fungsi geometri planar. Kali ini cara menghitung jarak menggunakan geometri ellipsoidal merupakan metode paling akurat untuk lapisan yang mencakup area yang luas. Pilih Ellipsoidal lalu klik Run. Setelah selesai silahkan ditutup (*Gambar 4*)

6. Akan muncul layer baru Added geom info loaded di panel layers. Ini merupakan salinan dari lapisan input dengan kolom baru yang ditambahkan untuk jarak. Klik kanan pada Added geom info dan pilih Open Attribute Table (*Gambar 5*)

7. Pada tabel atribut kita melihat kolom baru yang disebut jarak. Ini berisi panjang setiap fitur garis dalam meter. Perhatikan juga atribut sov_a3 berisi kode negara untuk setiap fitur. Tutup Attribute rable window (*Gambar 6*)

8. Sekarang kita memiliki panjang masing-masing segmen jalur kereta api, kita juga bisa menjumlahkan untuk menemukan panjang total jalur kereta api. Kita harus menggunakan hanya segmen yang ada di Amerika Serikat. Kita dapat menggunakan nilai kode negara sov_a3 untuk memfilter layer. Klik kanan Added geom info dan klik filter (*Gambar 7*)

9. Dalam Query Builder dialog, masukkan ekspresi "sov_a3" = 'USA' lalu klik OK (*Gambar 8*)

10. Kita akan melihat ikon Filter muncul disebelah layer Added geom info yang ditambhakan di layers panel yang menunjukkan bahwa filter diterapkan ke layer. Kita juga bisa mengonfirmasi secara visul bahwa lapisan sekarang berisi segmen garis hanya untuk Amerika Serikat. Kita akan menghitung jumlahnya klik Show statictical di bilah Attributes Toolbar (*Gambar 9*)

11. Panel Statistik baru akan terbuka. Pilih Lapisan info geom yang ditambahkan dan kolom panjang (*Gambar 10*)

12. Satuan statistik sama dengan aturan panjang kolom - meter. Kita ubah perhitungan untuk mengunakan kilometer sebagai gantinya. Klik ikon Expression di sebeleh menu drop-down di panel statistik (*Gambar 11*)

13. Masukkan ekspresi berikut dalam Expression Dialog yang mengubah panjang menjadi kilometer length / 1000 (*Gambar 12*)

14. Nilai SUM yang ditampilkan merupakan total panjang rel di Amerika Serikat (*Gambar 13*)
