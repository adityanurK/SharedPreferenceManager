# 📱 User Preference Manager (Android - Kotlin)

Sebuah aplikasi Android sederhana untuk mengelola preferensi pengguna seperti login, pengaturan tema (gelap/terang), dan notifikasi menggunakan `SharedPreferences`.

---

## 🚀 Fitur Aplikasi

- 🔐 Login sederhana dengan kredensial tetap (`aditya` / `aditya123`)
- 🌗 Dukungan mode tema gelap dan terang
- 🔔 Kontrol pengaturan notifikasi pengguna
- 💾 Penyimpanan data lokal dengan `SharedPreferences`
- 🔁 Navigasi otomatis antar activity berdasarkan status login

---

## 🧱 Struktur Proyek

```
app/
├── manifests/
│   └── AndroidManifest.xml
│
├── java/com.example.userpreferencemanager/
│   ├── LoginActivity.kt
│   ├── MainActivity.kt
│   ├── PrefsHelper.kt
│   ├── SettingsActivity.kt
│   └── SplashActivity.kt
│
├── res/
      │
      ├── layout/
      │   ├── activity_login.xml
      │   ├── activity_main.xml
      │   ├── activity_settings.xml
      │   └── activity_splash.xml
      │
      └── values/
         ├── colors.xml
         ├── colors.xml (night)
         ├── strings.xml
         └── styles.xml
```

---

## 🧭 Alur Navigasi Aplikasi

1. **SplashActivity**

   - Menampilkan splash screen selama 2 detik.
   - Mengecek status login (`isLoggedIn`).
   - Jika sudah login → langsung ke `MainActivity`.
   - Jika belum → diarahkan ke `LoginActivity`.

2. **LoginActivity**

   - Form login untuk username dan password.
   - Jika sesuai (`aditya` dan `aditya123`), simpan status login dan username, lalu pindah ke `MainActivity`.

3. **MainActivity**

   - Menampilkan:
     - Teks sambutan `Welcome, <username>`
     - Status notifikasi (On/Off)
     - Tombol ke halaman Settings dan Logout
   - Tema gelap/terang diterapkan sesuai preferensi pengguna.

4. **SettingsActivity**
   - Terdapat dua `Switch`:
     - Untuk mengaktifkan/menonaktifkan tema gelap
     - Untuk mengatur status notifikasi
   - Saat menyimpan, perubahan disimpan ke `SharedPreferences` dan `MainActivity` direfresh jika tema berubah.

---

## ⚙️ Cara Setup & Menjalankan

### Prasyarat:

- Android Studio
- Emulator Android / perangkat fisik

---

## ✅ Pengujian Fungsional

| Langkah                       | Hasil yang Diharapkan                                      |
| ----------------------------- | ---------------------------------------------------------- |
| Aplikasi dijalankan           | Splash screen tampil selama 2 detik                        |
| Belum login                   | Muncul halaman login                                       |
| Login: `aditya` / `aditya123` | Langsung masuk ke halaman utama                            |
| Masuk ke Settings             | Switch tema dan notifikasi tersedia                        |
| Klik Save & Back              | Preferensi disimpan, kembali ke MainActivity dengan update |
| Klik Logout                   | Kembali ke halaman login dan data login terhapus           |
| Buka ulang aplikasi           | Jika login tersimpan, langsung masuk ke halaman utama      |

---

## 🗃️ SharedPreferences (PrefsHelper)

| Key                      | Tipe    | Deskripsi                         |
| ------------------------ | ------- | --------------------------------- |
| `isLoggedIn`             | Boolean | Status login pengguna             |
| `username`               | String  | Username yang tersimpan           |
| `isDarkMode`             | Boolean | Status tema gelap/terang          |
| `isNotificationsEnabled` | Boolean | Status notifikasi aktif/nonaktif  |
| `isThemeChanged`         | Boolean | Menandai apakah tema telah diubah |

---

## 🔧 Teknologi yang Digunakan

- Kotlin
- Android SDK
- SharedPreferences
- Material Design Components
- XML Layout

---

## 📸 Screenshot

Screenshoot lengkap dapat dilihat pada file berikut:

📄 [Screenshoot.docx](./Screenshoot.docx)
