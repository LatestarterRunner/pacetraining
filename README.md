# Aplikasi VDOT untuk Android

Proyek ini membungkus halaman web Aplikasi VDOT (folder `www`) menjadi aplikasi Android memakai Capacitor 8. APK dibangun otomatis oleh GitHub Actions, jadi tidak perlu Android Studio.

## Langkah membuat APK (cukup lewat browser)

1. **Ekstrak** file zip ini di komputer Anda.
2. **Buat repositori baru** di github.com: klik tanda **+** di kanan atas, pilih **New repository**, beri nama `aplikasi-vdot`, boleh pilih **Private**, lalu **Create repository**.
3. **Unggah isi proyek.** Di halaman repositori yang kosong, klik **uploading an existing file**. Seret **isi** folder hasil ekstrak (bukan file zip-nya) ke halaman itu, yaitu: `www`, `icons`, `.github`, `package.json`, `capacitor.config.json`, `.gitignore`, dan `README.md`. Lalu klik **Commit changes**.
   - Folder `.github` bersifat tersembunyi. Di Windows, aktifkan Tampilkan item tersembunyi (View > Show > Hidden items). Di Mac, tekan Cmd+Shift+titik di Finder.
   - Jika `.github` tidak ikut terunggah: klik **Add file > Create new file**, ketik nama `.github/workflows/build-apk.yml` (garis miring otomatis membuat folder), tempel seluruh isi file `build-apk.yml.txt` (hapus baris pertama yang diawali `#`), lalu **Commit changes**.
4. **Jalankan build.** Buka tab **Actions**. Build bernama **Build APK** berjalan otomatis setelah commit. Jika tidak, klik **Build APK** di kiri lalu **Run workflow**. Tunggu sekitar 5-10 menit sampai muncul tanda centang hijau.
5. **Unduh APK.** Klik hasil build yang berhasil, gulir ke bagian **Artifacts**, klik **Aplikasi-VDOT-apk**. File zip akan terunduh; ekstrak untuk mendapatkan `app-debug.apk`.
6. **Pasang di HP.** Kirim `app-debug.apk` ke HP (kabel, Drive, atau WhatsApp ke diri sendiri), buka, dan izinkan "pasang dari sumber tidak dikenal" bila diminta.

## Mengubah aplikasi

Edit `www/index.html` langsung di GitHub (ikon pensil), lalu commit. Build berjalan lagi dan menghasilkan APK baru.

## Catatan penting

- APK ini adalah versi debug untuk dipasang sendiri. Setiap build memakai kunci penandatanganan baru, jadi APK versi baru tidak bisa menimpa versi lama. **Hapus aplikasi lama dulu sebelum memasang yang baru.** Data tersimpan di aplikasi (hasil lari yang diisi) ikut hilang.
- Untuk Google Play Store diperlukan kunci penandatanganan tetap dan format AAB. Itu bisa ditambahkan nanti.
- Aplikasi berjalan tanpa internet. Font Space Grotesk dan Inter dimuat dari Google saat online; bila offline, HP memakai font bawaan dan semua angka tetap sama.
- Jika build gagal (tanda silang merah), buka langkah yang gagal di halaman Actions, salin pesan error-nya, dan kirim ke Claude untuk diperbaiki.
