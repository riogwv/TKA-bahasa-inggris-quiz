<div align="center">

# 📘 TKA English
### Ruang latihan bahasa Inggris SMA / SMK

**Baca dengan tenang. Latih strateginya. Pahami alasannya.**

Latihan interaktif untuk Bahasa Inggris Wajib, Tingkat Lanjut, dan latihan campuran.
Dibuat dengan HTML, CSS, dan JavaScript, tanpa akun atau backend.

`66 soal latihan` · `28 strategi topik` · `Mode terang & gelap`

</div>

---

> **Tentang materi:** Semua soal dalam website ini merupakan soal latihan yang dibuat untuk belajar, bukan soal resmi TKA. Bacaan singkat membantu melatih keterampilan tertentu, tetapi tidak selalu mencerminkan panjang atau tingkat kesulitan ujian yang sesungguhnya.

## 🧭 Pilih jalur belajarmu

| Mode | Isi | Cocok untuk |
| --- | --- | --- |
| **Wajib** | 28 soal dalam 14 topik | Melatih dasar pemahaman bacaan |
| **Tingkat Lanjut** | 28 soal dalam 14 topik | Melatih analisis dan evaluasi teks |
| **Mixed Practice** | 66 soal, termasuk 10 soal dari dua bacaan panjang | Menggabungkan latihan dari kedua kategori |

Setiap topik memiliki panduan strategi singkat. Soal dan bacaan menggunakan bahasa Inggris; pembahasan dan strategi menggunakan bahasa Indonesia.

## ✨ Yang bisa kamu lakukan

- Pilih jawaban tunggal, beberapa jawaban, atau kategorikan pernyataan sesuai jenis soal.
- Berpindah soal, mengubah jawaban, dan menandai soal yang ingin diperiksa kembali.
- Aktifkan timer opsional atau kerjakan dengan santai tanpa timer.
- Lihat skor, jawaban, pembahasan, bukti dari teks, dan hasil per topik setelah selesai.
- Lanjutkan sesi tersimpan, lihat skor sebelumnya, dan pilih tema terang atau gelap.
- Gunakan website di HP maupun komputer.

Jawaban benar ditampilkan setelah kuis dikumpulkan. Setiap soal bernilai satu poin jika seluruh jawabannya tepat; jawaban sebagian tidak mendapat poin. Aturan ini dibuat untuk latihan, bukan klaim sistem penskoran resmi TKA.

## 🎨 Tampilan Blue Hour

Warna biru dipadukan dengan aksen biru kehijauan dan permukaan yang lembut. Pengaturan warna berada di `css/style.css`; mode gelap dapat dipilih dari website.

## 🚀 Menjalankan di komputer

Website ini berjalan tanpa backend dan dependency produksi. Untuk mencoba secara lokal, buka terminal di folder proyek dan jalankan:

```bash
python -m http.server 8000
```

Kemudian buka `http://localhost:8000` di browser. Gunakan server lokal agar browser dapat memuat file JSON dengan baik.

## 🗂️ Struktur proyek

| Lokasi | Isi |
| --- | --- |
| `index.html` | Halaman utama dan struktur website |
| `css/style.css` | Tampilan, warna, dan tata letak responsif |
| `js/` | Tampilan, logika kuis, dan pemuatan data |
| `data/` | Bank soal dan strategi topik |
| `assets/` | Ikon website |
| `tests/` | Pengujian logika dan data soal |
| `.github/workflows/` | Workflow GitHub Pages opsional |
| `scripts/` | Skrip publikasi opsional |

## 🌐 Memasang di GitHub Pages

Unggah isi proyek ke repository, dengan `index.html` di halaman utama repository. Pada **Settings → Pages**, pilih **Deploy from a branch**, lalu pilih branch `main` dan folder `/(root)`. Simpan dan tunggu hingga alamat website muncul. Untuk memperbarui tampilan, unggah `style.css` ke folder `css` dan simpan perubahan.

## 🧪 Pengujian dan batasan

Jalankan `npm test` atau `node --test tests/*.test.js` dengan Node 18+. Tes mencakup kelengkapan soal, validitas kunci, penskoran, pengacakan, dan validasi sesi.

Progres dan pengaturan disimpan di browser perangkat melalui LocalStorage dan tidak otomatis berpindah ke perangkat lain. Kunci jawaban tersedia dalam data aplikasi, sehingga website ditujukan untuk latihan mandiri. Tampilan layar kecil telah disiapkan; pengujian pada semua perangkat dan pembaca layar belum dilakukan.

## 📚 Referensi

Materi latihan disusun dengan merujuk PDF Bahasa Inggris Wajib dan Pilihan yang diberikan serta kerangka kompetensi Pusmendik. Pengelompokan 28 topik adalah rancangan belajar untuk website ini.

- [Pusmendik — Bahasa Inggris Wajib](https://pusmendik.kemendikdasmen.go.id/tka/tka/view/mata-pelajaran-wajib/sma/bahasa-inggris)
- [Pusmendik — Bahasa Inggris Tingkat Lanjut](https://pusmendik.kemendikdasmen.go.id/tka/tka/view/mata-pelajaran-pilihan/sma/bahasa-inggris-tingkat-lanjut)

---

<div align="center">Selamat belajar, satu soal setiap langkah. 💙</div>
