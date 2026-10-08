# Be My Local Friend in Jabodetabek (IMFOO OFFICIAL)

Website statis. Tidak perlu build atau server. Isi folder:

- `index.html`  : seluruh halaman
- `img/`        : foto-foto situs
- `data/state.json` : foto galeri dan tanggal penuh (diubah lewat panel Admin)
- `.nojekyll`   : supaya GitHub Pages menampilkan semua file apa adanya

## 1. Taruh di GitHub

1. Buka github.com, buat repository baru, misalnya `imfoo-website`. Pilih **Public**.
2. Klik **Add file → Upload files**, lalu seret SEMUA isi folder ini (termasuk folder `img` dan `data`). Klik **Commit changes**.
3. (Kalau mau memakai GitHub Pages) Buka **Settings → Pages**, di "Branch" pilih `main` dan folder `/ (root)`, lalu **Save**. Setelah sekitar 1 menit, alamat situsnya muncul di halaman itu.

## 2. Taruh di Vercel

1. Buka vercel.com dan login dengan akun GitHub.
2. Klik **Add New → Project**, pilih repository `imfoo-website`, lalu **Import**.
3. Biarkan semua pengaturan apa adanya (Framework: Other, tanpa build command), lalu **Deploy**.
4. Setiap kali ada perubahan di GitHub, Vercel memperbarui situs otomatis dalam sekitar 30 detik.

## 3. Aktifkan Admin (hanya kamu yang bisa ubah)

Admin dipakai untuk **menandai tanggal penuh** dan **menambah/menghapus foto galeri**.
Yang bisa mengubah hanya orang yang memegang token GitHub-mu.

Buat token:
1. GitHub → foto profil → **Settings → Developer settings → Personal access tokens → Fine-grained tokens → Generate new token**.
2. Isi nama, misalnya `imfoo-admin`. Atur masa berlaku (maksimal 1 tahun).
3. **Repository access**: pilih **Only select repositories**, lalu pilih `imfoo-website` saja.
4. **Permissions → Repository permissions → Contents → Read and write**.
5. Klik **Generate token**, lalu salin tokennya (hanya tampil sekali).

Masuk sebagai admin:
1. Buka situsmu, gulir ke bawah, klik tulisan kecil **Admin** di footer.
2. Isi **Repository** (contoh: `usernamekamu/imfoo-website`), **Branch** (`main`), dan tempel **token**. Klik **Masuk**.
3. Di bagian "My Galeri" muncul tombol **+ Tambah foto galeri**, dan di atas kalender muncul **Atur tanggal penuh**.
4. Setiap kali kamu tekan Simpan, perubahan dikirim ke GitHub. Situs publik ikut berubah dalam sekitar 1 menit (Vercel sekitar 30 detik).

Catatan keamanan:
- Token disimpan hanya di browser yang kamu pakai untuk masuk. Pakai perangkatmu sendiri. Klik **Keluar** di panel Admin setelah selesai kalau memakai perangkat lain.
- Jangan membagikan token ke siapa pun. Kalau token bocor atau hilang, hapus di GitHub (Settings → Developer settings → token tersebut → Delete) dan buat yang baru.
- Tamu yang membuka tulisan Admin hanya melihat form login. Tanpa token yang benar mereka tidak bisa mengubah apa pun.
- Repository bersifat publik, jadi foto galeri dan tanggal penuh memang terbaca publik (itu memang tujuannya).

## Mengubah isi lain

Teks, harga, menu makanan, dan tempat wisata ada di dalam `index.html`.
Minta Claude memperbaruinya, lalu unggah `index.html` baru ke repository (Add file → Upload files, timpa file lama).
Jangan menimpa folder `data`, supaya foto galeri dan tanggal penuhmu tidak hilang.
