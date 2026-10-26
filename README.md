# TKA English — Ruang Latihan

Website HTML, CSS, dan Vanilla JavaScript tanpa backend, akun, CDN, atau dependency produksi. Semua soal adalah latihan mandiri, bukan soal resmi TKA.

## Menjalankan

Dari folder ini, jalankan `python -m http.server 8000`, lalu buka `http://localhost:8000`. Gunakan server HTTP; membuka `index.html` melalui `file://` tidak mendukung pemuatan JSON pada sebagian browser.

## Fitur

- Wajib 28 soal, Pilihan 28 soal: dua latihan untuk masing-masing 14 topik.
- Mixed Practice berisi seluruh 66 soal, termasuk 10 soal berbasis dua bacaan panjang.
- PG, multi-select, kategori, tabel, 28 strategi topik, level kesulitan.
- Navigasi nomor soal, sebelumnya/berikutnya, penandaan, perubahan/pengosongan jawaban.
- Timer opsional 90 detik per soal. Batas waktu tetap berjalan saat tab ditutup atau berada di latar belakang.
- Shuffle memakai ID pilihan stabil. Baris kategori mempertahankan urutan asli.
- Pembahasan dan bukti hanya ditampilkan setelah submit, beserta rincian per topik.
- Sesi, skor terakhir, dan tema disimpan di LocalStorage. Jika penyimpanan diblokir, kuis tetap berjalan dalam memori dan menampilkan pemberitahuan.
- Tema terang/gelap, layout satu kolom di layar kecil, label input, focus ring, skip link.
- Reset progres meminta konfirmasi. Beranda menyimpan sesi aktif untuk dilanjutkan.

## Penskoran

Satu soal bernilai satu poin bila semua pilihannya tepat. Tidak ada kredit parsial. Kategori yang belum lengkap dihitung sebagai belum lengkap. Persentase dibulatkan dari benar / jumlah soal × 100. Ini aturan latihan pribadi, bukan klaim metode penskoran resmi TKA.

## Struktur

- `index.html`: semantic shell dan aksesibilitas dasar.
- `css/style.css`: responsive layout dan tema.
- `js/app.js`: tampilan, interaksi, timer, penyimpanan sesi.
- `js/quiz.js`: scoring, shuffle, dan validasi sesi murni.
- `js/data.js`: pemuatan dan pemeriksaan bank soal, wrapper penyimpanan.
- `data/wajib.json`, `pilihan.json`, `mixed.json`: soal dengan ID stabil, options, key, alasan dan bukti.
- `data/strategies.json`: ringkasan dan strategi 28 topik.
- `assets/favicon.svg`: ikon native tanpa gambar eksternal.
- `tests/quiz.test.js`: tes logika dan integritas konten.
- `.github/workflows/pages.yml`: tes dan deployment Pages.
- `scripts/publish.sh`: publikasi melalui GitHub CLI, tanpa menimpa repo yang ada.

## Pengujian

Jalankan `npm test` atau `node --test tests/*.test.js` dengan Node 18+. Enam tes menguji cakupan, kunci, scoring, kategori, 100 pengacakan sesi, serta round-trip dan penolakan state rusak. UI browser diuji untuk pilih jawaban, penandaan, navigasi, pemulihan setelah reload, kategori, multi-select, dan submit parsial. Hasil uji contoh: 3 benar, 0 salah, 25 belum lengkap pada Wajib, sesuai tiga soal yang dijawab.

Layout mobile disiapkan lewat breakpoint 760px. Pengujian perangkat fisik, semua pembaca layar, dan seluruh browser belum dilakukan. LocalStorage tidak menyinkronkan data antarperangkat. Karena aplikasi statis, kunci dalam JSON bisa dibaca melalui developer tools; aplikasi ini ditujukan untuk latihan, bukan ujian aman.

## Publikasi GitHub

Repository/Pages belum dibuat oleh sesi pembuatan karena konektor GitHub tidak menyediakan create-repository/Pages dan browser GitHub meminta sign-in.

Pilihan otomatis dari komputer sendiri: install GitHub CLI resmi, login dengan `gh auth login`, ekstrak ke folder bersih di luar repo lain, lalu jalankan `bash scripts/publish.sh`. Skrip membuat repo publik baru `tka-english-quiz` atau nama bertimestamp bila ditemukan nama yang sudah ada, menguji source, commit, push, lalu mencoba mengaktifkan Pages. Bila aktivasi tidak diizinkan oleh akun, buka Settings > Pages > Source > GitHub Actions, lalu jalankan workflow dari tab Actions. Tidak ada token yang disimpan di proyek.

Pilihan manual: buat repository publik baru, upload isi folder ini (termasuk `.github/workflows/pages.yml`), gunakan branch `main`, lalu pilih GitHub Actions sebagai source Pages. URL final hanya diketahui setelah deployment sukses.

## Materi dan referensi

Materi mengadaptasi panduan latihan TKA English yang disusun sebelumnya dari PDF unggahan 2025: Wajib 17 halaman dan Pilihan 41 halaman. Soal baru tidak diklaim sebagai soal resmi. Bacaan mikro membantu fokus pada satu keterampilan dan tidak selalu mencerminkan panjang/kompleksitas penuh ujian. Kasus mixed adalah kasus fiktif untuk latihan.

Kerangka resmi yang diverifikasi pada 26 Oktober 2026 mencakup pemahaman tekstual, inferensial, serta evaluasi dan apresiasi. Pengelompokan 28 topik merupakan rancangan belajar. Tidak ada kebijakan baru khusus 2026 yang diasumsikan.

- [Pusmendik Bahasa Inggris Wajib](https://pusmendik.kemendikdasmen.go.id/tka/tka/view/mata-pelajaran-wajib/sma/bahasa-inggris)
- [Pusmendik Bahasa Inggris Tingkat Lanjut](https://pusmendik.kemendikdasmen.go.id/tka/tka/view/mata-pelajaran-pilihan/sma/bahasa-inggris-tingkat-lanjut)

Tidak ada PDF sumber yang disertakan dalam repository publik. Semua konten ditampilkan melalui `textContent` atau DOM API, tanpa injeksi HTML dari bank soal. Google Drive dan Canva tidak diperlukan untuk aset utama karena seluruh tampilan memakai CSS dan SVG sederhana yang dapat diedit.
