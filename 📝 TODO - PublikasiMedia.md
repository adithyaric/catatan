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
#####    Menu Login
-   [x] Login Menggunakan Jetstream
-   [x] Register dan Login Default
-   [x] Role : super admin, admin, operator/support, freelance (marketing)
- [x] Verifikasi Email
- [x] No HP

> Customer -> Personal : order biasa. Supportnya terbatas. Berlanganan : dapet diskon lebih banyak.
---
#####    CRUD By Admin
- [x] Halaman Users
- [x] Halaman Roles
- [x] Halaman Media
- [x] Halaman Kategori Layanan
- [ ] Halaman Layanan Product (Services)
	- [ ] Sistem Bundle/Paket
	- [ ] Edit Detail Product (Services)
- [x] Halaman Attribute Layanan Product
- [x] Halaman Varaint Layanan Product
- [ ] Halaman Dashboard
- [x] Halaman Campaign/Orders
- [x] Halaman History
- [x] saat Link hasil sudah ada :
	- [x] Ada revisi
	- [x] isi keterangan revisi
---
#####    Embbed Spreadsheet
-   [x] Tambah DataTable (Search)
###### Buat Import Excel/CSV
-   [x] Media
-   [x] Service
-   [ ] Buat Export Cart ⇒ Excel/CSV
---
#####    Campaign/Orders
-  [x] Campign/Order bisa berbeda-beda, login langsung bisa buat camping dinamai.
-  [x] satu keterangan yang sama/detail bisa memiliki banyak media di satu layanan
-  [ ] pilihan 200k (press) atau 500k (adv), free (back) ==fixed?==
-  [x] **Request Media** : Pencarian Tidak ditemukan => request!
-  [ ] Halaman Admin : Create Custom Invoice
-  [x] isi centang dengan Syarat dan ketentuan/chat CS untuk tanya
-  [x] Isi nama Campign
-  [ ] Laporan Orderan
-  [x] 1. Checklist Membutuhkan Penambahan PPH (Pajak)
-  [x] 2. Checklist Minta tanda tangan Basah di materai 10k

---

-   [x] Pertanyaan Perlu/Tidak Perlu Pembuatan Konten
-   [x] Submit Draft : Tiap Media bisa ditambah draft
-   [x] Order id => keranjang shopping.
-   [x] Buat halaman depan
-   [x] tambah search di list media
-   [ ] Teknik up selling ???
-   [x] Bisa pilih media dulu baru pilih kategori
- [ ] media alternatif hanya press-release [`Layanan lain sudah pasti terbit`]

- [x] Pembayaran Payment Gateway : Invoice Paper ID.
- [x] Pembayaran Manual : Invoice Basah.

---
Notifikasi Email dan Wa 
- [x] Verifikasi email
- [ ] Orderan/Invoice yang sudah dibuat
- [ ] Orderan yang masih di keranjang belum dibayar lebih dari 3 hari
- [ ] Notifikasi Link Hasil manual oleh admin [`admin buat tombol buat notif ke user`]
- [ ] Notifikasi Orderan Selesai Terimakasih (template) berisi pesan dan feedback 

#####    Fitur Afiliasi
Komisi didapat dari :
- [x] Mengajak orang
- [x] Banyak transaksi
- [x] Perhitungan Bonus

> example:
> ![[Pasted image 20221114212122.png]]


---

```json
  [
  "status_code" => 201
	  "data" => array:5 [
	    "id" => "547074048"
	    "number" => "num17"
	    "payper_url" => "get.sandbox.paper.id/Bdx8K2F"
	    "pdf_url" => "get.sandbox.paper.id/mkF8hHV"
	    "status_send" => []
	  ]
  ]
```

```json
[
  "id" => "547074048"
  "number" => "num17"
  "payper_url" => "get.sandbox.paper.id/Bdx8K2F"
  "pdf_url" => "get.sandbox.paper.id/mkF8hHV"
  "status_send" => []
]
```

```json
{
  "status_code": 201
  "message": "Request Success"
  "data": {
    "payper_url": "get.sandbox.paper.id/gmdH6Tz"
    "ref_id": "00000001"
    "transaction_id": "48413bfd-273c-4171-935b-1becbd6d084b"
    "transaction_status": "PENDING"
  }
}
```
