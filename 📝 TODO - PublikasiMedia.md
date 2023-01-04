[PublikasiMedia.drawio](https://drive.google.com/file/d/1FuCPvAq59yFTIZDRcNjETxXQARLbHPCt/view?usp=sharing)

[USHER AND ADMIN NEEDED](https://docs.google.com/document/d/1mVW-fzhiUWES0JfVvZiIaQ_7mZopQqdpa4e9bHVSET0/edit)

---

**Alur User :**

1.  Login
2.  Lihat Tampilan Layanan"
3.  Buat campign => isi nama campign
4.  redirect ke menu detailing (sesuai layanan yg dipilih no.2)
5.  Pilih media (dan lengkapi dokumen)
6.  Klik Pesan atau simpan ke draft
7.  Masuk ke keranjang lalu bayar

---

#####  Menu Login

- %%[x] Login Menggunakan Jetstream%%
- %%[x] Register dan Login Default%%
- %%[x] Role : super admin, admin, operator/support, freelance (marketing)%%
- %%[x] Verifikasi Email%%
- %%[x] No HP%%
  > Customer
  > - Personal : order biasa. Supportnya terbatas.
  > - Berlanganan : dapet diskon lebih banyak.
- User memasukkan tanggal lahir, (notifikasi ultah)

---

#####  CRUD By Admin

- %%[x] Halaman Users%%
- %%[x] Halaman Roles%%
- %%[x] Halaman Media%%
- %%[x] Halaman Kategori Layanan%%
- %%[x] Halaman Layanan Product (Services)%%
  - %%[x] Sistem Bundle/Paket%%
  - %%[x] Edit Detail Product (Services)%%
- %%[x] Halaman Attribute Layanan Product%%
- %%[x] Halaman Varaint Layanan Product%%
- %%Halaman Dashboard%%
  - %%[x] 1. Pesanan yang sedang diproses%%
  - %%[x] 2. Total belanja%%
  - %%[x] 3. Komisi Affiliasi%%
  - %%[x] 4. Pesanan yang dibatalkan%%
- %%[x] Halaman Campaign/Orders%%
- %%[x] Halaman History%%
- %%[x] saat Link hasil sudah ada :%%
  - %%[x] Ada revisi%%
  - %%[x] isi keterangan revisi%%

---

#####  Embbed Spreadsheet

- %%[x] Tambah DataTable (Search)%%
- %%[x] Buat Import Excel/CSV%%
- %%[x] Media%%
- %%[x] Service%%
- %%[x] Buat Export Cart ⇒ Excel/CSV ==sudah ada di paper id==%%

---

#####  Campaign/Orders

- %%[x] Campign/Order bisa berbeda-beda, login langsung bisa buat camping dinamai.%%
- %%[x] satu keterangan yang sama/detail bisa memiliki banyak media di satu layanan%%
- %%[x] pilihan 200k (press) atau 500k (adv), free (back)%%
- %%[x] **Request Media** : Pencarian Tidak ditemukan => request!%%
- [ ] Halaman Admin : Create Custom Invoice
- %%[x] isi centang dengan Syarat dan ketentuan/chat CS untuk tanya%%
- %%[x] Isi nama Campign%%
- ==Laporan Orderan==
- %%[x] 1. Checklist Membutuhkan Penambahan PPH (Pajak)%%
- %%[x] 2. Checklist Minta tanda tangan Basah di materai 10k%%
- %%_Paket Bundle press release disamakan seperti_ :%%
  %%![[Pasted image 20221125090933.png]]%%

---

<!-- - [x] Pertanyaan Perlu/Tidak Perlu Pembuatan Konten -->
<!-- - [x] Submit Draft : Tiap Media bisa ditambah draft -->
<!-- - [x] Order id => keranjang shopping. -->
<!-- - [x] Buat halaman depan -->
<!-- - [x] tambah search di list media -->
- [x] Teknik up selling
<!-- - [x] Bisa pilih media dulu baru pilih kategori -->
<!-- - [x] media alternatif hanya press-release -->
<!-- - [x] Pembayaran Payment Gateway : Invoice Paper ID. -->
<!-- - [x] Pembayaran Manual : Invoice Basah. -->

---

#####  Notifikasi Email dan Wa

- [x] Verifikasi email
- [ ] Orderan/Invoice yang sudah dibuat
- [ ] Orderan yang masih di keranjang belum dibayar lebih dari 3 hari
- [ ] Notifikasi Link Hasil manual oleh admin
- [ ] Notifikasi Orderan Selesai Terimakasih (template) berisi pesan dan feedback

- [`admin buat tombol buat notif ke user`]
- [ ] Ada tombol untuk mengirim pesan notifikasi ke user.
- [ ] Aksi untuk kirim email revisi, misal revisi dari user ditolak admin
- [ ] Fitur chat langsung

---

#####  Fitur Afiliasi

Komisi didapat dari :

<!-- - [x] Mengajak orang -->
<!-- - [x] Banyak transaksi -->
<!-- - [x] Perhitungan Bonus -->
<!-- - [x] Notification Banyak Cart -->
<!-- - [x] Halaman List Media di hidden dulu -->

==refferal==
- [ ] cookies 14 hari
- [ ] link affiliasi saat user lain klik dihitung cookies selama 14 hari
- [ ] setiap orang yg order lewat link afiliasi dapat diskon total 50.000/media.

---

##### Sistem Refund

- [ ] refund status = ditolak sama media, aka kolom pesan.
- [ ] no rekening
- [ ] nominal refund
- [ ] tujuan kemana
- [ ] tanggal refund
- [ ] rek bank

---

#### Revision v.1

<!-- Perubahan nama menu -->

<!-- - [x] Category = layanan -->
  <!-- - [x] kategori layanan -->
  <!-- - [x] Attribut = detail layanan -->
<!-- - [x] Media = domain -->
<!-- - [x] Refferal = affiliate -->
  <!-- - [x] user affiliator (paling banyak komisi'nya) -->
  <!-- - [x] list withdraw -->
<!-- - [x] (admin) list orders = pesanan dibawah dashboard -->
<!-- - [x] Perlu konten itu di halaman cart saja -->
- [ ] Perbaikan Rumus ===buatkan konten== (harga x jml konten) + total pesanan.
<!-- - [x] di detail History user ada aksi terima. -->
<!-- - [x] aksi menambah id media untuk tim-nya mba nida -->
      ![[Pasted image 20221229131014.png]]
<!-- - [x] tanggal pembuatan invoice -->
<!-- - [x] user bisa download invoice excel `status harus selesai semua` -->
<!-- - [x] di edit admin status approve media & approbe editor jadi satu. -->
<!-- - [x] ada pop up untuk menampilkan bukti transfer (pembayaran manual) -->
<!-- - [x] keterangan hyperlink pada cart bisa di edit -->

![[Pasted image 20221229131053.png]]
