[PublikasiMedia.drawio](https://drive.google.com/file/d/1FuCPvAq59yFTIZDRcNjETxXQARLbHPCt/view?usp=sharing)
[USHER AND ADMIN NEEDED](https://docs.google.com/document/d/1mVW-fzhiUWES0JfVvZiIaQ_7mZopQqdpa4e9bHVSET0/edit)


---
**Alur User :**
**1.  Login**
**2.  Lihat Tampilan Layanan"**
**3.  Buat campign => isi nama campign**
**4.  redirect ke menu detailing (sesuai layanan yg dipilih no.2)**
**5.  Pilih media (dan lengkapi dokumen)**
**6.  Klik Pesan atau simpan ke draft**
**7.  Masuk ke keranjang lalu bayar**

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
- [ ] Halaman Checkout
- [x] Halaman History
	- [ ] Filter tanggal
	***Status :***
		- validasi konten
		- proses penerbitan
		- terbit

---
#####    Embbed Spreadsheet
-   [x] Tambah DataTable (Search)
***Buat Import Excel/CSV***
-   [x] Media
-   [x] Service
	-  [ ] Attribute
	-  [ ] Variants
-   [ ] Buat Export Cart ⇒ Excel/CSV
---
#####    Campaign/Orders
-   [x] Campign/Order bisa berbeda-beda, login langsung bisa buat camping dinamai.
-   [x] satu keterangan yang sama/detail bisa memiliki banyak media di satu layanan

`semrush brief = campign`

###### **Masalah internal ini seperti :**

1.  kebutuhan laporan orderan
2.  listing harga & detail

Jadi di internal itu ada kerumitan soal laporan pekerjaan, kadang ketumpuk tumpuk di WA. ⇒ **Laporan**
-   [x] **Request Media** : Proses pengajuan media (select search). Jika tidak ada masuk ke waiting list 
-   [ ] Halaman Create Custom Invoice
-   [x] Isi nama Campign

---

-   [x] Pertanyaan Perlu/Tidak Perlu Pembuatan Konten
-   [x] Submit Draft : Tiap Media bisa ditambah draft
-   [x] Order id => keranjang shopping.
-   [x] Buat halaman depan
-   [x] tambah search di list media
-   [ ] Follow up (lewat email oleh admin/operator) jika user buat pesanan
-   [ ] Teknik up selling
-   [x] Bisa pilih media dulu baru pilih kategori
- [ ] media alternatif hanya press-release [Layanan lain sudah pasti terbit]
---
#####    Fitur Afiliasi

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

Pembayaran Manual : Invoice Basah