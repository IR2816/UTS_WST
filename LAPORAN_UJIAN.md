# Laporan UTS Web Software Tools

**Nama:*Irfan Muhamad Ilham*
**Nomor Induk Mahasiswa:*12523018*
**Kelas:*A*
**Tanggal:*Rabu, 11-11-2026*

## A. Bukti pemeriksaan masalah
| Masalah | Alat yang digunakan | Bukti pemeriksaan | Perkiraan penyebab | Perbaikan | Hasil setelah perbaikan |
|---|---|---|---|---|---|
| Produk | Console  | terdapat error 404 di console | endpoint di app.js berbeda dengan yang di server.mjs | ganti endpoint dari api/barang ke api/products | product list muncul |
| Tombol keranjang | Sources | tombol tidak terbaca dan saat di breakpoint error | class tidak sama untuk tombol | ubah .add-to-cart menjadi .add-button | product dapat dimasukan ke keranjang |
| Total belanja | Test runner dan browser F12 | Setelah produk yang sama ditambahkan dua kali, jumlah barang bertambah tetapi total tidak ikut bertambah dengan benar | Fungsi calculateTotal hanya menghitung item.price dan belum mengalikan item.quantity | Mengubah perhitungan menjadi harga dikali jumlah barang | Total berubah sesuai jumlah produk dan test berhasil |

## B. Hasil pengujian
- Jumlah pengujian sebelum perbaikan: Tidak dicatat sebelum perbaikan dilakukan.
- Jumlah pengujian berhasil setelah seluruh perbaikan: 7 dari 7 pengujian berhasil.
- Catatan perubahan pada fungsi yang diperiksa: Perbaikan keseluruhan mencakup endpoint product list, event tombol Add to Cart, fungsi `addProduct`, dan fungsi `calculateTotal`. Fungsi `calculateTotal` sekarang menghitung harga berdasarkan `item.price * item.quantity`.

## C. Kualitas kode
- Temuan sebelum perbaikan: Secara keseluruhan terdapat endpoint product list yang tidak sesuai, selector tombol keranjang yang berbeda, total yang belum memperhitungkan quantity, dan variabel `discount` yang tidak digunakan.
- Perbaikan yang dilakukan: Endpoint disamakan dengan server, selector tombol disamakan menjadi `.add-button`, dan rumus total diperbaiki agar mengalikan harga dengan quantity.
- Hasil pemeriksaan ulang secara keseluruhan: Test berhasil 7 dari 7. Lint masih memberikan 1 warning karena variabel `discount` belum digunakan. Format check dan quality check masih perlu dirapikan karena formatter Biome menemukan perbedaan format pada `public/app.js` dan `src/cart.js`.

## D. Git
- Branch (jika membuat): `feat-produck_list`, `fix-add-to-cart`, dan `fix-cart-total`; seluruh perbaikan kemudian digabungkan ke `main`.
- Ringkasan commit: `Fix add to cart button`, `Fix total cart calculation`, serta merge pull request untuk setiap perbaikan.
- Hasil pemeriksaan `git status`: Working tree bersih saat pemeriksaan sebelum perubahan laporan ini. Setelah laporan diisi, file `LAPORAN_UJIAN.md` perlu di-commit.

## E. Pemakaian kecerdasan buatan (jika digunakan)
- Nama alat: GitHub Copilot.
- Pertanyaan/instruksi yang diberikan: Meminta bantuan menemukan penyebab product list tidak tampil, tombol Add to Cart tidak merespons, dan total belanja produk yang sama tidak berubah.
- Bagian jawaban yang diterapkan: Memeriksa kecocokan endpoint API, mencocokkan class tombol dengan selector event listener, dan menghitung total menggunakan harga dikalikan quantity.
- Cara memeriksa apakah saran tersebut benar: Membandingkan kode frontend dengan endpoint server, menggunakan Console dan Sources pada browser, menjalankan test otomatis, serta menguji penambahan produk yang sama secara manual.

## F. Refleksi singkat
- Satu pelajaran paling penting dari ujian ini: Debugging perlu dilakukan dari gejala ke sumber masalah dengan memeriksa Console, kode yang menjalankan event, dan hasil test. Perubahan kecil seperti perbedaan nama class atau perhitungan quantity dapat membuat fitur terlihat tidak berfungsi.
