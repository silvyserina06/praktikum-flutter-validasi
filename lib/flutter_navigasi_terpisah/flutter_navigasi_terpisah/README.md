# Navigasi Flutter - Versi File Terpisah

Versi ini memecah `main_navigasi.dart` (1 file, 13 project) menjadi **1 file per project**.
Isi kode setiap project sama dengan versi satu file; yang berubah hanya letak file dan
adanya `main()` di tiap file agar project bisa dijalankan sendiri.

## Struktur Folder

```
lib/
  main.dart                      <- menu gabungan (membuka ke-13 project)
  common/
    app_common.dart              <- tema, Halaman (kerangka AppBar), rupiah(), PintuProject
  projects/
    p01_navigator_dasar.dart     <- Bab 1
    p02_kirim_data.dart          <- Bab 2
    p03_terima_hasil.dart        <- Bab 2
    p04_named_routes.dart        <- Bab 3
    p05_arguments.dart           <- Bab 3
    p06_login_home.dart          <- Bab 4
    p07_tumpukan_halaman.dart    <- Bab 4
    p08_bottom_nav.dart          <- Bab 5
    p09_tabbar.dart              <- Bab 5
    p10_drawer.dart              <- Bab 5
    p11_hero.dart                <- Bab 6
    p12_transisi_custom.dart     <- Bab 6
    p13_mini_toko.dart           <- Bab 7
```

## Cara Memakai

1. Buat proyek Flutter: `flutter create belajar_navigasi`
2. Hapus isi folder `lib/` bawaan, lalu salin folder `lib/` dari paket ini ke dalam proyek.
3. Jalankan:

```bash
# Menu gabungan (memilih project dari daftar)
flutter run

# Satu project saja (tanpa menu)
flutter run -t lib/projects/p01_navigator_dasar.dart
flutter run -t lib/projects/p13_mini_toko.dart
```

## Catatan Penting

- **Hot Restart (R)** diperlukan setelah mengubah alur navigasi, `routes`, atau nilai awal state.
- **Project 04 dan 05** memakai named routes. Daftar route-nya (`p4Routes`, `p5Routes`) ada di
  file masing-masing, lalu digabung di `main.dart` dengan operator spread (`...`).
- **Project 07 dan 13** bergantung pada `route.isFirst`. Saat dijalankan sendiri, keduanya dibuka
  dari `PintuProject` (halaman dasar mini di `app_common.dart`) agar perilaku tumpukan halaman
  sama persis dengan saat dibuka dari menu gabungan.
- **Skenario praktik pengubahan** (lembar kerja PDF) ditulis untuk versi satu file. Untuk versi
  ini, padanan lokasinya: ubah `home` pada `main()` di file project yang bersangkutan
  (misalnya S1.3), atau ubah `MyApp` di `main.dart` untuk perubahan yang menyangkut menu.
  Nama class dan isi kode tidak berubah.
- Untuk melatih skenario tanpa merusak file asli, salin file project ke nama lain
  (misalnya `p01_latihan.dart`) dan jalankan dengan `-t`.
