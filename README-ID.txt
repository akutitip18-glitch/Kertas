KERTAS KERJA PEJABAT PENGADAAN V7 — PWA DAN LOW-FI

ISI PAKET
- index.html: aplikasi V7 (SLA, template DOCX, Low-Fi, filter paket, ekspor JSON untuk ekstensi)
- manifest.webmanifest: metadata pemasangan PWA
- sw.js: cache shell dan fallback offline
- icons/: ikon pemasangan 192x192 dan 512x512

CARA MEMASANG (Cloudflare Pages / GitHub Pages / hosting HTTPS)
1. Ekstrak ZIP. Jangan mengubah nama/lokasi berkas index.html, manifest.webmanifest, sw.js, dan folder icons.
2. Unggah seluruh isi folder (bukan folder pembungkusnya) ke hosting statis HTTPS.
3. Buka URL HTTPS saat online sekali dan tunggu status PWA menunjukkan siap.
4. iPhone/iPad: buka URL di Safari → Bagikan → Tambahkan ke Layar Utama.
5. Android/desktop: gunakan menu Install app/Pasang aplikasi pada browser.
6. Setelah shell disimpan, halaman inti dapat dibuka offline. Tautan JDIH dan situs resmi tetap memerlukan internet.

FITUR V7
- SLA end-to-end dari tanggal dokumen diterima PPK sampai BA Reviu dan timeline target/selesai untuk setiap tahap. Target diisi sesuai SOP internal; aplikasi tidak menganggap angka target sebagai batas hukum.
- Template DOCX kustom dengan tag seperti {nama_paket}, {nilai_hps}, {tahun_anggaran}, dan tag paket lain. Proses berlangsung lokal; pada browser modern yang mendukung DecompressionStream deflate-raw.
- Toggle Mode Kinerja: Standar / Low-Fi. Low-Fi mematikan animasi, transform, filter/blur, gradien dekoratif, dan bayangan.
- Filter daftar paket menurut tahun anggaran dan status verifikasi, serta filter tabel verifikasi hukum per paket.
- Ekspor data paket minimal sebagai JSON untuk ekstensi pendamping pengisian SPSE.
- Fitur V6 tetap tersedia: verifikasi hukum, audit hash berantai, ID RUP/SPSE, rekap multi-tahun, dan pertukaran paket terenkripsi.

EKSTENSI PENDAMPING SPSE
Ekstensi browser tersedia sebagai ZIP terpisah bernama KKPP-V7-SPSE-Extension-Chrome-Edge-Firefox.zip. Instal folder chrome-edge untuk Chrome/Edge atau folder firefox untuk Firefox. Ekstensi hanya mengisi bidang yang cocok ketika diminta pengguna, tidak mengirim formulir, dan bukan integrasi/API resmi LKPP. Ikuti README dalam ZIP ekstensi.

CATATAN SLA DAN KEAMANAN
- SLA awalnya kosong dan harus diisi berdasarkan SOP/penugasan instansi. Pengingat hari kalender bukan tenggat hukum nasional.
- Timeline SLA disimpan bersama data paket dan ikut dalam backup/transfer aplikasi.
- Template DOCX disimpan di IndexedDB lokal browser. Jika origin file:// tidak mendukung IndexedDB, template hanya tersedia selama sesi saat ini; gunakan HTTPS untuk penyimpanan antar-sesi.
- Ekstensi memerlukan tindakan klik pengguna pada tab aktif dan tidak mempunyai izin permanen akses semua situs. Periksa semua nilai yang diisi sebelum melanjutkan pada laman resmi.
- Data tetap lokal. Buat cadangan berkala; jangan menganggap rantai hash lokal sebagai audit log immutable atau tanda tangan digital tersertifikasi.
