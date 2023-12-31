## Instalasi & Penggunaan OpenVPN (ft. OpenVPN ITS) 😊

OpenVPN adalah sebuah perangkat lunak open-source yang digunakan untuk membuat jaringan pribadi virtual (VPN) yang aman. Dengan menggunakan OpenVPN, Anda dapat mengamankan koneksi internet Anda dan mengakses sumber daya jaringan yang terbatas secara geografis. Panduan ini akan membantu Anda menginstal dan menggunakan OpenVPN, khususnya dengan layanan OpenVPN ITS.

### Langkah 1: Instalasi OpenVPN 🛠️

Langkah pertama adalah menginstal perangkat lunak OpenVPN di sistem Anda. Anda dapat melakukan ini dengan perintah berikut di terminal:

```bash
sudo apt install openvpn
```

### Langkah 2: Konfigurasi Server OpenVPN ⚙️

1. Pertama-tama, buka terminal dan navigasi ke direktori konfigurasi OpenVPN dengan perintah:

```bash
cd /etc/openvpn
```

2. Selanjutnya, unduh file konfigurasi server OpenVPN dari layanan ITS. Anda dapat mengganti `{link-download}` dengan tautan yang sesuai:

```bash
wget {link-download}
```

3. Setelah unduhan selesai, ekstrak file arsip yang telah Anda unduh:

```bash
unzip {nama-file}
```

Gantilah `{nama-file}` dengan nama file yang sudah Anda unduh.

4. Masuk ke dalam folder hasil ekstraksi:

```bash
cd NAMA-FOLDER
```

### Langkah 3: Koneksi ke Server OpenVPN 🌐

Sekarang, Anda siap untuk terhubung ke server OpenVPN ITS. Misalnya, untuk terhubung ke "Server 1" dari OpenVPN ITS, jalankan perintah berikut:

```bash
sudo openvpn its-onefile-1.ovpn
```

Setelah menjalankan perintah ini, Anda akan terhubung ke jaringan VPN.

Selamat! Anda telah berhasil terhubung ke server OpenVPN ITS. 🎉

_**Catatan:** Pastikan Anda mengganti placeholder seperti `{link-download}`, `{nama-file}`, dan `NAMA-FOLDER` dengan nilai yang sesuai sesuai dengan situasi Anda._

Terima kasih telah menggunakan panduan ini. Semoga berhasil! 🚀
