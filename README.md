# NusantaraVoice AI - Android APK Project

Panduan Membangun File APK Android menggunakan Capacitor & Android Studio:

## Struktur Folder
```
nusantara-voice-ai/
├── package.json            # Konfigurasi dependensi Node.js & Capacitor
├── capacitor.config.json   # Konfigurasi ID aplikasi & folder webDir ("www")
├── README.md               # Panduan build APK
└── www/                    # Direktori aset web utama
    ├── index.html          # Kode aplikasi utama HTML/JS
    ├── manifest.json       # Konfigurasi PWA & ikon aplikasi
    └── css/
        └── style.css       # Styling tambahan
```

## Langkah-langkah Build APK:

1. **Install Node.js** (versi 18 atau lebih baru) dan **Android Studio** di komputer Anda.
2. **Ekstrak** file ZIP ini ke dalam sebuah folder.
3. Buka Terminal / Command Prompt di dalam folder proyek tersebut, lalu jalankan perintah:
   ```bash
   npm install
   npx cap add android
   npx cap sync android
   ```
4. **Penting (API Key Gemini):**
   Buka file `www/index.html`, cari bagian `const apiKey = "";`, dan masukkan Gemini API Key Anda agar fitur TTS berjalan di aplikasi Android standalone.
5. **Izin Penyimpanan Android (AndroidManifest.xml):**
   Buka proyek di Android Studio dengan perintah:
   ```bash
   npx cap open android
   ```
   Pastikan pada file `android/app/src/main/AndroidManifest.xml` terdapat izin internet:
   ```xml
   <uses-permission android:name="android.permission.INTERNET" />
   ```
6. **Build APK:**
   Di dalam Android Studio, pilih menu **Build > Build Bundle(s) / APK(s) > Build APK(s)**. File `.apk` siap diinstal di perangkat Android Anda!
