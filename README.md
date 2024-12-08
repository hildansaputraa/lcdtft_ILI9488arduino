# Tutorial Mengakses TFT LCD Touchscreen Display 3.5 Inch (ILI9488) dengan ESP32

Tutorial ini menjelaskan langkah-langkah untuk mengakses TFT LCD Touchscreen ILI9488 menggunakan ESP32 Development Board. Layar touchscreen 3.5 inch ini cocok digunakan untuk membuat **Graphical User Interface (GUI)** pada berbagai proyek.

---

## 📦 Komponen yang Diperlukan
- **TFT LCD Touchscreen 3.5 Inch (ILI9488)**: Layar ini mendukung mode paralel 8-bit untuk komunikasi data yang cepat.
- **ESP32 Development Board**: Microcontroller dengan berbagai fitur dan protokol komunikasi.

---

## 🔗 Protokol Komunikasi: Mode Paralel 8-Bit
Komunikasi antara ESP32 dan layar ILI9488 menggunakan mode paralel 8-bit, yang memungkinkan pengiriman data secara cepat melalui 8 pin data sekaligus. Berikut adalah pin utama yang digunakan:

- **TFT_D0 - TFT_D7**: Pin data untuk mengirim byte data secara paralel.
- **TFT_CS**: Chip Select, mengaktifkan layar.
- **TFT_DC (Data Command)**: Menentukan apakah data yang dikirim adalah perintah atau data grafis.
- **TFT_WR (Write Strobe)**: Sinyal untuk menulis data ke layar.
- **TFT_RD (Read Strobe)**: Digunakan jika pembacaan data diperlukan.
- **TFT_RST**: Reset layar untuk menginisialisasi ulang.

---

## 🛠️ Konfigurasi Koneksi
Sambungkan TFT LCD Touchscreen ILI9488 dengan ESP32 sesuai dengan tabel berikut:

| Nama Pin TFT | Pin ESP32  |
|--------------|------------|
| **TFT_CS**   | GPIO 33    |
| **TFT_DC/RS**| GPIO 15    |
| **TFT_RST**  | GPIO 32    |
| **TFT_WR**   | GPIO 4     |
| **TFT_RD**   | GPIO 2     |
| **TFT_D0**   | GPIO 12    |
| **TFT_D1**   | GPIO 13    |
| **TFT_D2**   | GPIO 26    |
| **TFT_D3**   | GPIO 25    |
| **TFT_D4**   | GPIO 17    |
| **TFT_D5**   | GPIO 16    |
| **TFT_D6**   | GPIO 27    |
| **TFT_D7**   | GPIO 14    |
| **5V**       | 5V         |
| **3.3V**     | 3.3V       |
| **GND**      | GND        |

---

## 🔧 Menginstal dan Memodifikasi Library
1. **Instal Library**:
   - Buka Arduino IDE.
   - Pilih **Library Manager**.
   - Cari dan instal **TFT_eSPI by Bodmer**.

2. **Modifikasi File `User_Setup.h`**:
   - Buka Arduino IDE dan pilih **File > Preferences**.
   - Salin lokasi **Sketchbook** dari **Preferences**.
   - Buka lokasi tersebut di file explorer.
   - Unduh file [User_Setup.h](https://github.com/hildansaputraa/lcdtft_ILI9488/blob/main/lib/TFT_eSPI/User_Setup.h) dan ganti file `User_Setup.h` di folder library **TFT_eSPI**.

---

## 📋 Contoh Penggunaan
Kami telah menyediakan contoh kode yang dapat langsung digunakan: [Contoh Kode LCD TFT ILI9488](https://github.com/hildansaputraa/lcdtft_ILI9488).

### Cara Upload Kode
1. Buka file kode pada Arduino IDE.
2. Klik tombol **Upload** (ikon panah).

---

## 📝 Dokumentasi Tambahan
Untuk informasi lebih lanjut dan modifikasi sesuai kebutuhan proyek Anda, silakan kunjungi: [Dokumentasi TFT_eSPI](https://doc-tft-espi.readthedocs.io/tft_espi/).

---

## 🎉 Terima Kasih!
Selamat mencoba! Jika ada pertanyaan atau saran, jangan ragu untuk menghubungi kami melalui repository ini.
