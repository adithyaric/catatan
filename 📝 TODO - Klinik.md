---

- [x] Stok Obat dan Reagen pada Inventory
- [x] Pengurangan Obat//Reagen saat Membuat tindakan Poli [ada kuantitas obat//reagen]
- [x] Data Perawat adalah Users yang punya level sebagai perawat ~~Email, Password
- [x] Data Tagihan [status = belum_lunas]
- [x] Data Pembayaran [status = lunas]
- [x] Status Kamar kembali available jika sudah di checkout/bayar
- [x] Rawat inap : tindakan poli bisa lebih dari 1 (id_rawat_inap)
- [x] Tindakan Sesuai Dokter
- [x] Detail Rawat Inap
- [x] Previllage User

#### Laporan Excel

- [x] Pemasukan
  - [x] Export : totalObat = harga jual - harga beli
- [x] Pengeluaran [group by category???]
- [ ] Perhitungan Fee dokter dan perawat
- [x] Stok
- [x] History Pasien

---

#revisi 1.0 :

- [x] User dan Perawat di Sendirikan.
  - [x] Pendaftaran
  - [x] Admin
  - [x] Perawat
  - [x] Cashier
  - [x] Laboratorium/Apotek
- [x] Data Perawat Nama & username di jadikan satu
- [x] Tindakan Perawat di data tagihan
- [x] create yg rawat inap belum benar filter tindakan dokter dan perawatnya
- [x] List tindakan poli, group rawat inap
- [x] (sort by newest)
- [x] Penjualan Obat dan Reagen. Penjualan obat udah ada.. Tapi itu baru bisa jual 1 jenis aja Jadi penjualannya itu untuk jual banyak obat Gausah di kategorikan gapapa.. Jadi milih milih aja obatnya sama qty nya berapa.. Nanti diakumulasikan.. Di akhir ada total akhirnya.. Yang harus dibayar oleh pembeli.. Baru di save mas. _Owhh ya paham² berarti dikasih form repeater aja to mas?_ Isinya.. Nama obat, qty, harga nanti di akhir. Ada total Harga otomatis dari data obat.. Di kali qty nya Kalau yang di penjualan.. Harga jual \* qty
- [x] di data pasien : tambah data tindakan
  - [x] Jadi gini Di user pendaftaran kan cuma bisa akses data pasien. Nah di data pasien kemarin kan aku minta ada tombol "Tindakan". Nah ketika tombol itu di klik... Langsung direct ke form yang isinya **cuma inputan'nya biaya pendaftaran** Nahh pas di submit. Otomatis biaya pendaftaran itu nanti yang masuk ke nota. Nah di nota kan ada jam kunjungan. Nah dapetnya dari pas si user pendaftaran nge klik submit biaya pendaftarannya itu mas. Oke ini yang di bagian user pendaftaran.
  ```sql
  Buat TABLE pendaftaran_user
  int id,
  int pasien_id,
  bigInt biaya_pendaftaran,
  timestamp
  ```
  - [x] Nah iki akan berelasi sama user perawat di poli. Di tindakan poli. Kita harus milih pasien yang mau di tindak kan. disini kita filter pasiennya mas. Kan ada banyak pasien tuh, tapi ga semua pasien bisa di tindak.
  - [x] _Mesti pertanyaannya... Gimana nge filternya??_ Pasien yang bisa ditindak itu hanya pasien yang udah melalui alur pendaftaran diatas tadi. _Pertanyaan lagi.. Lha fungsi data pasiennya di master data apa??_ Pasien yang di master data yang belum melewati itu. Berarti dia cuma data pasien biasa aja. Yang ga sedang berobat.
  - [x] _Kapan pasien yang udah melalui alur pendaftaran kembali menjadi pasien biasa lagi.. Atau kehapus dari filter tindakan..??_ Nah pasien itu bakal balik menjadi pasien biasa lagi setelah cashier sudah menganggap lunas tagihannya.
- [x] form input biaya pendaftaran
- [x] hitung umur dibuat otomatis
- [x] di list data pasien : NIK, Nama, Jenis Kelamin, BPJS, Umur, Alamat
- [x] Cetak Nota : Jam Kunjungan diganti bahasa indo
- [x] Kasus di Tindakan Poli
- [x] Search di select"
- [x] Dashboard total pasien rawat inap (status belum lunas + kamar tidak kosong)
- [x] Tindakan dokter & perawat = pendapatan klinik + fee
- [x] Dashboard + total pasien dalam tindakan...

#revisi 1.1
Update pengecekan Aplikasi Klinik :

1. Dashboard

- [x] Nominal total tagihan perlu dicek ulang

2. Data perawat

- [x] [`Isi dan nama tabel belum sesuai`]

3. Data pasien

- [x] Tambah pasien erorr

4. Export
   - [x] Data History Pasien pada kolom umur belum jalan
   - [x] [`Data pendapatan pada baris jumlah belum jalan`]

- [x] Perhitungan total pada nota perlu dicek kembali
  - [x] non Rawat Inap
  - [x] [`Rawat Inap`]
- [x] Hak akses belum dibagi
- [x] Perhitungan kamar belum jalan
- [x] Laporan data obat dipakai format seperti dibawah. total (harga&stok)
  - [x] Stok Keluar

## #revisi 1.2

| Perbaikan Menu |

---

1. Dashboard
   - [x] Total pasien Dalam Tindakan -> Total Tagihan Sudah Dibayar
   - Total Pemasukan ??
   - Total Tagihan ??
   - Total Pasien Rawat Jalan ++
   - Total Pasiem Rujuk ++
2. %%Master Data Perawat (Masukkan Password)%%
3. %%List Pasien dalam tindakan harus hilang setelah lunas (Rawat Inap)%%
4. %%Disable Tindakan setelah lunas%%
5. `Data Request Obat dari poli pada Apotek`
6. Penjualan Obat (Select Obat & Quantity)
7. %%Perhitungan Pada Nota%%
8. Perhitungan Pada Laporan Pemasukan dan Pengeluaran
9. %%Laporan Stock obat dan Reagen%%
10. Laporan History Pasien
    - Untuk rawat Inap Ambil 1
    - Perhitungan Rawat inap, jalan, rujuk
11. %%Remove add button di stock obat dan reagen%%

---

| Perbaikan Menu |

---

Admin

- %%Dashboard (Tetap)%%
- %%Kategori (Tetap)%%
- %%Master Data (Tetap)%%
- [x] Tindakan Poli (Jadikan Menu jangan Submenu)
- [x] Laporan Jadi -> Kasir
- %%Inventory (Tetap)%%
- [x] Export Jadi -> Cetak Laporan
      Pendaftaran
- [x] Dashboard (Total Pasien Rujuk, Rawat Jalan, dan Rawat Inap)
- %%Master Data tetap%%
  Perawat
- [x] Dashboard (Total Pasien Rujuk, Rawat Jalan, dan Rawat Inap)
- %%Master Data (tetap)%%
- [x] Tindakan Poli (Jadikan Menu jangan Submenu)
      Apotek
- [x] Dashboard (Total Pasien Rujuk, Rawat Jalan, dan Rawat Inap)
- [x] Kategori
  - Obat
  - Reagen
- [x] Inventory
  - Stok Obat
  - Stok Reagen
- [x] Penjualan (Merupakan Menu Penjualan Obat -> Di jadikan menu sendiri)
      Cashier
- [x] Dashboard (Total Tagihan dan Total Tagihan Belum Dibayar)
- [x] Kasir (menu yang tadinya bernama Laporan)
      %%Note : Menu Export atau Cetak laporan hanya ada di Admin Saja.%%
