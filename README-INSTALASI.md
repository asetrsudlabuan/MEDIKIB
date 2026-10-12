# MEDIKIB PWA

PWA ini langsung membuka halaman login MEDIKIB setelah animasi loading layar penuh. Tombol **Pasang MEDIKIB** berada di pojok kanan atas halaman aplikasi. Data dan proses aplikasi tetap berada di Web App MEDIKIB.

## Aktifkan tampilan di dalam PWA

1. Sebelum deploy PWA, ganti isi `Code.gs` dan `Index.html` pada proyek Apps Script dengan `AppsScript/Code.gs` dan `AppsScript/Index.html` dari paket MEDIKIB terbaru.
2. Simpan lalu pilih **Deploy → Manage deployments → Edit → New version → Deploy**.
3. PWA memanggil Web App dengan parameter `embed=pwa`; setelah kode backend dan halaman terbaru aktif, aplikasi akan tampil di dalam PWA.
4. Pada pemasangan pertama, masuk kembali ke MEDIKIB jika diminta. Sesi yang sebelumnya tersimpan pada alamat Apps Script mungkin tidak terbawa ke penyimpanan PWA.

Mode embed memakai `XFrameOptionsMode.ALLOWALL` hanya saat parameter `embed=pwa` digunakan. Ini membuat halaman dapat dimuat dalam iframe dari situs lain juga; jangan bagikan URL embed kepada pihak yang tidak dipercaya.

## Jika PWA gagal membuka login MEDIKIB

1. Di proyek Apps Script, salin `AppsScript/Code.gs` dan `AppsScript/Index.html` dari paket MEDIKIB terbaru, lalu simpan.
2. Pilih **Deploy → Manage deployments → Edit → New version → Deploy**. Menyimpan kode saja tidak memperbarui deployment `/exec`.
3. Pastikan pengaturan **Who has access** memang mengizinkan pengguna yang membuka PWA. Jangan ubah ke akses publik tanpa menilai keamanan fungsi backend dan kebijakan institusi.
4. Setelah deployment aktif, tekan **Coba lagi**. Jika Google meminta login akun di dalam PWA, gunakan **Buka login di browser**; halaman login Google tidak dapat dilewati oleh PWA.
5. Setelah memperbarui GitHub Pages, tutup dan buka ulang PWA. Jika tampilan lama tetap tersimpan, muat ulang situs GitHub Pages di browser.
## Deploy ke GitHub Pages

1. Unggah semua isi folder ini ke repositori GitHub.
2. Buka **Settings → Pages** pada repositori.
3. Pada **Build and deployment**, pilih **Deploy from a branch**, branch `main`, folder `/ (root)`, lalu simpan.
4. Buka alamat HTTPS GitHub Pages yang diberikan. PWA tidak dapat dipasang jika dibuka sebagai file lokal `file://`.

## Memasang di perangkat

- **Android / Chrome:** buka alamat GitHub Pages. Saat halaman login termuat, ketuk **Pasang MEDIKIB**, lalu konfirmasi.
- **iPhone / iPad:** buka alamat tersebut di Safari, ketuk **Bagikan → Tambah ke Layar Utama → Tambah**.
- **Komputer:** gunakan prompt instal Chrome/Edge, atau menu browser **Instal aplikasi**.

Setelah browser mendeteksi aplikasi terpasang, tombol instal disembunyikan. Service worker menyimpan halaman loading dan ikon agar PWA dapat dibuka kembali. Membuka data MEDIKIB tetap memerlukan internet dan akses Google Apps Script.
