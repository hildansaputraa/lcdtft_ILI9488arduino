<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tutorial TFT LCD Touchscreen Display 3.5 Inch (ILI9488) dengan ESP32</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            line-height: 1.6;
            margin: 20px;
            background-color: #f9f9f9;
            color: #333;
        }
        h1, h2, h3 {
            color: #0056b3;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin: 20px 0;
        }
        table, th, td {
            border: 1px solid #ccc;
        }
        th, td {
            padding: 10px;
            text-align: left;
        }
        th {
            background-color: #f2f2f2;
        }
        a {
            color: #007bff;
            text-decoration: none;
        }
        a:hover {
            text-decoration: underline;
        }
    </style>
</head>
<body>
    <h1>Tutorial Mengakses TFT LCD Touchscreen Display 3.5 Inch (ILI9488) dengan ESP32</h1>
    <p>Tutorial ini menjelaskan langkah-langkah untuk mengakses TFT LCD Touchscreen ILI9488 menggunakan ESP32 Development Board. Layar touchscreen 3.5 inch ini cocok digunakan untuk membuat <i>Graphical User Interface</i> (GUI) pada berbagai proyek.</p>

    <h2>📦 Komponen yang Diperlukan</h2>
    <ul>
        <li><strong>TFT LCD Touchscreen 3.5 Inch (ILI9488)</strong>: Layar ini mendukung mode paralel 8-bit untuk komunikasi data yang cepat.</li>
        <li><strong>ESP32 Development Board</strong>: Microcontroller dengan berbagai fitur dan protokol komunikasi.</li>
    </ul>

    <h2>🔗 Protokol Komunikasi: Mode Paralel 8-Bit</h2>
    <p>Komunikasi antara ESP32 dan layar ILI9488 menggunakan mode paralel 8-bit, yang memungkinkan pengiriman data secara cepat melalui 8 pin data sekaligus. Berikut adalah pin utama yang digunakan:</p>
    <ul>
        <li><strong>TFT_D0 - TFT_D7</strong>: Pin data untuk mengirim byte data secara paralel.</li>
        <li><strong>TFT_CS</strong>: Chip Select, mengaktifkan layar.</li>
        <li><strong>TFT_DC (Data Command)</strong>: Menentukan apakah data yang dikirim adalah perintah atau data grafis.</li>
        <li><strong>TFT_WR (Write Strobe)</strong>: Sinyal untuk menulis data ke layar.</li>
        <li><strong>TFT_RD (Read Strobe)</strong>: Digunakan jika pembacaan data diperlukan.</li>
        <li><strong>TFT_RST</strong>: Reset layar untuk menginisialisasi ulang.</li>
    </ul>

    <h2>🛠️ Konfigurasi Koneksi</h2>
    <p>Sambungkan TFT LCD Touchscreen ILI9488 dengan ESP32 sesuai dengan tabel berikut:</p>
    <table>
        <thead>
            <tr>
                <th>Nama Pin TFT</th>
                <th>Pin ESP32</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>TFT_CS</td>
                <td>GPIO 33</td>
            </tr>
            <tr>
                <td>TFT_DC/RS</td>
                <td>GPIO 15</td>
            </tr>
            <tr>
                <td>TFT_RST</td>
                <td>GPIO 32</td>
            </tr>
            <tr>
                <td>TFT_WR</td>
                <td>GPIO 4</td>
            </tr>
            <tr>
                <td>TFT_RD</td>
                <td>GPIO 2</td>
            </tr>
            <tr>
                <td>TFT_D0</td>
                <td>GPIO 12</td>
            </tr>
            <tr>
                <td>TFT_D1</td>
                <td>GPIO 13</td>
            </tr>
            <tr>
                <td>TFT_D2</td>
                <td>GPIO 26</td>
            </tr>
            <tr>
                <td>TFT_D3</td>
                <td>GPIO 25</td>
            </tr>
            <tr>
                <td>TFT_D4</td>
                <td>GPIO 17</td>
            </tr>
            <tr>
                <td>TFT_D5</td>
                <td>GPIO 16</td>
            </tr>
            <tr>
                <td>TFT_D6</td>
                <td>GPIO 27</td>
            </tr>
            <tr>
                <td>TFT_D7</td>
                <td>GPIO 14</td>
            </tr>
            <tr>
                <td>5V</td>
                <td>5V</td>
            </tr>
            <tr>
                <td>3.3V</td>
                <td>3.3V</td>
            </tr>
            <tr>
                <td>GND</td>
                <td>GND</td>
            </tr>
        </tbody>
    </table>

    <h2>🔧 Menginstal dan Memodifikasi Library</h2>
    <ol>
        <li>
            <strong>Instal Library</strong>:
            <ul>
                <li>Buka Arduino IDE.</li>
                <li>Pilih <strong>Library Manager</strong>.</li>
                <li>Cari dan instal <strong>TFT_eSPI by Bodmer</strong>.</li>
            </ul>
        </li>
        <li>
            <strong>Modifikasi File <code>User_Setup.h</code></strong>:
            <ul>
                <li>Buka Arduino IDE dan pilih <strong>File > Preferences</strong>.</li>
                <li>Salin lokasi <strong>Sketchbook</strong> dari <strong>Preferences</strong>.</li>
                <li>Buka lokasi tersebut di file explorer.</li>
                <li>Unduh file <a href="https://github.com/hildansaputraa/lcdtft_ILI9488/blob/main/lib/TFT_eSPI/User_Setup.h">User_Setup.h</a> dan ganti file <code>User_Setup.h</code> di folder library <strong>TFT_eSPI</strong>.</li>
            </ul>
        </li>
    </ol>

    <h2>📋 Contoh Penggunaan</h2>
    <p>Kami telah menyediakan contoh kode yang dapat langsung digunakan: <a href="https://github.com/hildansaputraa/lcdtft_ILI9488">Contoh Kode LCD TFT ILI9488</a>.</p>
    <h3>Cara Upload Kode</h3>
    <ol>
        <li>Buka file kode pada Arduino IDE.</li>
        <li>Klik tombol <strong>Upload</strong> (ikon panah).</li>
    </ol>

    <h3>Dokumentasi Tambahan</h3>
    <p>Untuk informasi lebih lanjut dan modifikasi sesuai kebutuhan proyek Anda, silakan kunjungi: <a href="https://doc-tft-espi.readthedocs.io/tft_espi/">Dokumentasi TFT_eSPI</a>.</p>

    <h2>🎉 Terima Kasih!</h2>
    <p>Selamat mencoba! Jika ada pertanyaan atau saran, jangan ragu untuk menghubungi kami melalui repository ini.</p>
</body>
</html>
