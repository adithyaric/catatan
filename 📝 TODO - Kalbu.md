 
[Checklist Aplikasi Kalbu Smart - Google Sheets](https://docs.google.com/spreadsheets/d/1iDLDcCh_ACMd5bZNHbeZLFzQHrJuixafE8y9SRMbtuQ/edit#gid=0)

---
- [x] Laporan -> laporan pembayaran, Jenis Layanan didapat dari = ks.Layanan Pada Laporan Pembayaran Ditambah Jenis Pencarian Agar Lebih Spesifik (Jenis Layanan, data jenis barangnya banyak jadi pokoknya yang disitu ada ditampilkan) Agar Mudah Dalam Perekapan
	- [x] WO Kapal
	- [x] WO non-Kapal
- [x] Pelayanan -> WO kapal -> Kolom Pengguna Jasa. Pengguna Jasa Pada Page Wo Kapal ditambah dua inputan [`Pemilik`, `Pengurus kapal = Nahkoda`] ks.kapal. 
	- %%Ditambah 2 Kolom Yang Berisi Pemilik Dan Pengurus Kapal%%
	- %%Ditambah di Laporan -> Laporan Pembayaran -> report/cetak-wo-kapal/wo-kapal%%
- [x] Laporan Bisa Di Excel Kan Sehingga Bisa Dengan Mudah Direkap Khususnya Pada Laporan Pembayaran, Seperti Di Laporan Kapal (Ada Fitur Cetak)
- [x] Pada Menu Laporan Rekap Stblk Datang Dan Berangkat Harus Sesuai Dengan Tanggal Dan Jumlah Yang Diinginkan.

- [x] Pelayanan -> Pengembalian barang, Filter Berdasarkan jenis layanan

---

- [x] Wo Non Kapal Dan Wo Kapal Diberikan Paperless Pada Setiap Jenis Layanan Seperti Di Pemakaian Air, Berlaku Untuk Smua Barang Yang Tersedia Di Jenis Layanan. (Khusus Wo Non Kapal Box Diberi Tanggal Pengembalian, Sisa Box, Nomor Box`

%%Paperless :%%
%%modal air kecuali galon & buang air%%
%%galon pakai yg mineral%%
%%pas masuk es tidak usah.%%

%%form lahan = form bangunan%%
%%form pas masuk = form air%%

---

%%Stblk Keberangkatan = Data Perbekalan
Pilih kapal stbl kedatangan sudah otomatis kalo udah kepilih tidak ditampilkan lagi (dalam status apapun),
1 stbl kedatangan buat 1 kapal dan 1 transaksi.%%

- [x] Kapal Yang Sudah Berangkat, Secara Otomatis Nomor Stbl Keberangkatan Hilang Jika Dibatalkan
- [x] Nomor Stbl Keberangkatan Tidak Akan Ditampilkan Di Kolom Nomor Stbl Keberangkatan

---

Pelayanan => wo non-kapal
- [x] Diberikan Akses Membatalkan wo non Kapal Yang Terjadi Kesalahan Input (Dibatalkan, icon sampah)  
- %%Dan Di Dashboard Harus Hilang (grand total yg dibatalkan tidak dihitung)%%
- [x] di dashboard hitung yg statusnya tervalidasi dan selesai
- [x] di dashboard make master => 
	- [x] jenis layanan di paginate.
---
- [x] Data Syahbandar -> Halaman Kesyahbandaran
	* [x] Buat Halaman Baru
	* [x] Untuk Kedatangan Diganti Syahbandar Dan 2 Petugas Syahbandar (Nama Dan Nip). dari Tabel karyawan
	* [x] Untuk Ijin Perbekalan Bebas Bisa Ptt (Ditambahkan Nip). [`Dari data karyawan`]
	* [x] Diberikan Opsi Nama-nama Pegawai Pelabuhan, Dimasukan Dalam List Perbekalan
	* [KALBU SMART | LOGIN](http://localhost/kalbu_smart/misc)
---

- [x] Ditambahkan Sertifikat Awak Kapal Perikanan
	- %%Master -> Kapal%%
	- %%Buat inputan text labelnya "Sertifikat Awak Kapal Perikanan"%%
	- %%Buat inputan file labelnya "Sertifikat Awak Kapal Perikanan"%%
- [x] Dpi Diperinci
- [x] Data Kelengkapan Kapal Dijadikan Satu Draft (di Zip) Dan Diberikan Fitur Download. Fitur Download Dokumen Per Kapal Diletakkan Di Laporan Kapal. Ditambah checkbox buat download file" tiap tiap kapal, perkapal ada 8 file.
---
- [x] Pada Stblk Keberangkatan, Nama Lastlog Tidak Disamakan Dengan Wo. Tetapi Disesuaikan Dengan Nama Karyawan Yang Memberangkatkan.
	- %%Nama Last Log dari Halaman STBL Kedatangan -> Add()%%
	- %%Ditambah select pengguna jasa (karyawan yg memberangkatkan)%%
---

- [x] Pelayanan -> wo & wo-non Kapal, edit hari yang tervalidasi tidak usah otomatis

**Penggantian Template Frontend**
- [x] Halaman Login, [Login Desa Panempan - Siteman (opendesa.id)](https://demosid.opendesa.id/siteman)
- Pengguna Jasa bisa Login, memakai nik & pin
- Tampilan ada dua. 
- [x] login untuk karyawan/admin, 
- [x] satunya buat pengguna jasa.
- Halaman Dashboard.
- [x] warna card dibedakan (gradient/mencolok).
- [x] dibuat agak rounded. 
- [x] Tombol" dibuat kayak opensid, kecil btn-xs ada iconnya.
- [x] Datatable jangan yg secondary, dibuat yg info
- [x] ~~Kiri atas di sebelah tulisan nama user~~ & ==logo==.
- [x] ~~Kanan atas diganti nama user~~ & ==logo==.
- [x] ganti warna primary (biru) dan pallet" warna lain (gradient)
- [x] Navbar dibuat gradient

Tambah chart di :
- [x] dibawahnya datatable pendapatan Dashboard. isinya chart bar, x = nama". y = nominal".

Di Halaman Statistik pakai Chart Pie.
==isinya belum ada.==

Data transaksi = 
```php
$tagihan = $this->ks_tagihan->select_tagihan($sortby, $sorttype, $searchby, $term, $limit, $offset);
where ks_tagihan_status = 1
```

%%1. ~~Home~~
2. ~~Data Tagihan~~
3. ~~Data Transaksi~~
4. Order Transaksi%
1. ~~Top Up~~
	1. Tunai
	2. BRIVA
	3. OVO
	4. BNI VA
2. ~~Pembayaran Lain ( Coming  Soon)~~ 
3. ~~Koperasi Kalbu (Coming Soon)~~%%

> Halaman Responsive, dibagian pencarian" masih berantakan. 
  dibuat kayak https://demosid.opendesa.id/penduduk :
  1. %%Master -> semua%%
  2. %%Kesyahbandaran -> stbl & data perbekalan%%
  %%Kalbu Smart -> tidak perlu%%
  3. %%Pelayanan -> semua%%
  4. %%Laporan -> semua%%
  %%Pengaturan -> tidak perlu%%

==checklist no.18==

%%[KALBU SMART | STBL KEDATANGAN](http://localhost/kalbu_smart/stbl-kedatangan/detail/1920)

ditambah 2 inputan petugas syahbandar, tabel karyawan.
nama inputan petugas syahbandar 1 & petugas syahbandar 2.
[Cetak STBL Kedatangan](http://localhost/kalbu_smart/stbl-kedatangan/prints/1919)
![[Pasted image 20221209151639.png]]
bagian kanan di taruh bawahnya supriadi.
petugas 1 & 2 ditambahkan di kolom kanan.%%

%%[KALBU SMART | STBL KEBERANGKATAN](http://localhost/kalbu_smart/stbl-keberangkatan/detail/1598)
ada opsi data penandatangan. 
mau pake syahbandar (tetap).
kalo radio button'nya petugas lain, baru milih karyawan.
si otik (syahbandar) diganti karyawan%%

Tamabahan File dan folder.. 
1. %%assets_halaman_pengguna/come (folder)%%
2. %%views/halaman_pengguna/coming.php%%

Update File
1. %%Controllers/halaman_pengguna/Dashboard.php%%
2. %%Views/halaman_pengguna/index.php%%
3. %%Views/halaman_pengguna/core/footer.php%%
4. %%Views/halaman_pengguna/topup_detail.php%%

6. %%Controllers/Report.php%%
7. %%Models/Ks_stbl_keberangkatan.php%%
8. %%Models/Ks_stbl_kedatangan.php%%
9. %%Views/report/_printform.php%%
10. %%Views/core/footer.php%%