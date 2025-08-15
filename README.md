# pembelajaran1

# Flutter Splash Screen dengan Animated Splash Screen & Lottie

Project ini adalah contoh pembuatan **Splash Screen animasi** di Flutter menggunakan package:

- [`animated_splash_screen`](https://pub.dev/packages/animated_splash_screen)
- [`lottie`](https://pub.dev/packages/lottie)

Animasi menggunakan file `.json` yang diunduh dari **[LottieFiles](https://lottiefiles.com/)**.

---

## 📌 Fitur
- Splash screen animasi menggunakan **Lottie JSON**.
- Navigasi otomatis ke halaman utama setelah splash screen selesai.
- Pengaturan durasi splash screen yang fleksibel.

---

## 📂 Struktur Folder Penting
assets/
└── splash.json # File animasi Lottie
lib/
├── main.dart # File utama Flutter
└── home_page.dart # Halaman tujuan setelah splash
pubspec.yaml # File konfigurasi Flutter

yaml
Copy
Edit

---

## 📥 Instalasi & Menjalankan Project
1. **Clone atau download project**
   ```bash
   git clone https://github.com/username/flutter_splash_lottie.git
Masuk ke folder project

bash
Copy
Edit
cd flutter_splash_lottie
Install dependencies

bash
Copy
Edit
flutter pub get
Jalankan project

bash
Copy
Edit
flutter run
📜 Konfigurasi pubspec.yaml
yaml
Copy
Edit
dependencies:
  flutter:
    sdk: flutter
  animated_splash_screen: ^1.3.0
  lottie: ^2.6.0

flutter:
  assets:
    - assets/splash.json
📝 Kode Lengkap main.dart
dart
Copy
Edit
import 'package:flutter/material.dart';
import 'package:animated_splash_screen/animated_splash_screen.dart';
import 'package:lottie/lottie.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      debugShowCheckedModeBanner: false,
      home: AnimatedSplashScreen(
        splash: Lottie.asset('assets/splash.json'),
        nextScreen: const HomePage(),
        splashIconSize: 250,
        duration: 3000,
        backgroundColor: Colors.white,
      ),
    );
  }
}

class HomePage extends StatelessWidget {
  const HomePage({super.key});

  @override
  Widget build(BuildContext context) {
    return const Scaffold(
      body: Center(
        child: Text(
          'Halaman Utama',
          style: TextStyle(fontSize: 24),
        ),
      ),
    );
  }
}
🌐 Sumber & Referensi
LottieFiles: https://lottiefiles.com/

Package Animated Splash Screen: https://pub.dev/packages/animated_splash_screen

Package Lottie: https://pub.dev/packages/lottie

📄 Lisensi
Project ini dibuat untuk tujuan pembelajaran. Animasi Lottie yang digunakan mengikuti lisensi masing-masing dari LottieFiles.
