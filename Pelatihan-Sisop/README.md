# Soal Latihan Sisop Pelatihan Linux

# Soal

  Dhea adalah seorang mahasiswi yang baru belajar dunia programming. Dia sangat ingin belajar lebih mendalam tentang dunia cyber security. Dalam langkah awal karirnya, Dhea diberi tantangan oleh mentornya untuk menganalisis log HTTP. Tantangan ini mengarahkan Dhea pada pencarian string base64 yang merupakan secret flag. Pada tahap pertama, Dhea diminta untuk membuat folder bernama “ilovelinux” pada direktori home user tersebut [1]. Setelah folder selesai dibuat, Dhea berpindah ke dalam folder tersebut dan diminta untuk mendownload sebuah file dari sebuah link berikut: http://10.199.16.188:7331/file.txt dan menyimpan hasilnya kedalam sebuah file bernama file.txt [2]. Dari file tersebut, dia mendownload sebuah file dengan menggabungkan IP Address sebelumnya serta isi dari file.txt [3]. Dari hasil download tersebut, akan didapatkan 1 buah file zip. Dhea kemudian diminta untuk melakukan unzip file tersebut ke dalam folder bernama “latihan” [4]. Karena penasaran, ia berpindah ke dalam folder dan melihat isi dari file unzip tersebut, ternyata didapatkan 2 buah file bernama runme dan .daemon [5]. 
	Untuk menjalankan challenge yang diminta, jalankanlah file runme yang telah didapat dan simpan output yang dikeluarkan ke dalam file bernama runme.log [6]. Dengan menjalankan file runme, Dhea telah mencapai tahap pertama dalam pencarian hidden flag. Karena penasaran, Dhea juga menjalankan file executable .daemon yang didapat dari hasil unzip sebelumnya [7]. Karena kedua program telah dijalankan, cek semua program yang sedang berjalan [8]. Setelah dicek, program .daemon tidak memiliki hal berarti di dalamnya, sehingga Dhea harus mematikan program .daemon yang telah dijalankan sebelumnya serta untuk memastikan jika program .daemon telah mati, Dhea mengecek kembali program yang sedang berjalan [9].
	Dhea kemudian berpindah dari program tadi, dia diminta untuk mengecek semua user yang tersedia pada komputer-nya [10]. Untuk menjalankan tugas-nya, ia diminta untuk membuat user baru bernama jagosisop [11] dan menambahkan user baru tersebut ke dalam sudoers group agar dapat menjadi root [12]. Dhea kemudian mengecek, apakah user “jagosisop” telah masuk sudoers group atau belum, dengan cara menampilkan list user yang termasuk ke dalam sudoers group [13]. Selanjutnya, Dhea berganti menjadi user baru yang telah dia buat (jagosisop) dan membuat folder baru bernama analysis pada home direktori jagosisop [14]. Dhea kemudian berganti kembali ke user awal dan berpindah ke folder yang telah dibuah tadi, yaitu ilovelinux dan masuk ke dalam folder latihan [15]. Dalam folder tersebut, ternyata terdapat sebuah file zip baru serta Dhea kemudian melakukan unzip pada file tersebut [16]. Pada tahap ini, Dhea baru mulai menganalisis HTTP log dan diminta untuk meng-list serta mengurutkan semua file dengan akhiran “.log” dan menemukan kapan log pertama dibuat serta menyimpan hasilnya ke dalam file bernama http.txt [17]. Kemudian diminta untuk meng-copy semua file yang mempunyai kata “2023” dan diakhiri dengan “.log” ke dalam folder “analysis” yang dimiliki oleh user jagosisop [18]. Setelah itu, ia berpindah ke user “jagosisop” serta berpindah ke folder “analysis” [19]. Setelah berpindah ke folder tersebut, ia diminta untuk menghitung berapa banyak 404 [20] dan 200 request serta menyimpan output-nya ke dalam file bernama request.txt [21]. Pada akhir challenge ini, bantu Dhea untuk mencari string base64 yang mengandung secret flag. Dhea akan sangat senang jika berhasil mendapatkan secret flag tersebut dan menyimpannya ke dalam file bernama flag.txt [22].
	Untuk memperdalam ilmu Dhea di dunia programming, Dhea juga berkeinginan untuk belajar mengenai version control system, yaitu git. Dhea kemudian diminta untuk mengupload hasil yang diperoleh ke akun github-nya [23], dengan ketentuan:

Repository public
  Jika memperoleh secret flag, maka hanya upload file bernama flag.txt
  Jika tidak memperoleh secret flag, maka upload file text.txt dan http.txt

Ketentuan Tambahan :
Wajib menggunakan VPN ITS atau terkoneksi dengan wifi ITS dalam proses download file ke ip address 10.199.16.188. Konfigurasi openvpn dapat diakses pada link berikut.
Seluruh soal dikerjakan hanya dengan menggunakan command line/terminal.
Setiap nomor hanya boleh dikerjakan dengan menggunakan 1 line command.
Soal nomor 3 harus dikerjakan menggunakan command substitution. Dilarang menggunakan command berikut :
curl http://10.199.16.188:7331/5bda90afcfd344fa33b8b33580cdbe7b.zip

# Solusi

## 1. Buat directory
```bash
mkdir ilovelinux
```

## 2. Pindah dan Download file.txt
```bash
wget -P /home/ikktaa/ilovelinux http://10.199.16.188:7331/file.txt | cd ilovelinux
```

## 3. Download file baru lagi
```bash
cat file.txt | xargs -I {} wget http://10.199.16.188:7331/{}
```

## 4. Unzip File yang Baru di Download & Mengouput kan ke Folder
```bash
sudo mkdir latihan | pwd {} | sudo unzip 5bda90afcfd344fa33b8b33580cdbe7b.zip -d {}/latihan
```

## 5. Berpindah dan Melihat Isi Folder
```bash
cd latihan ; ls -a
```

## 6. Jalankan runme dan Simpan Dalam runme.log
```bash
sudo sh -c './runme >> runme.log'
```

## 7. Jalankan .daemon
```bash
./.daemon
```

## 8. Cek Semua Program yang Berjalan
```bash
ps aux
```

## 9. Matikan .daemon dan Cek Program yang Berjalan
```bash
kill PID ; ps aux
```

## 10. Cek Semua User
```bash
cut -d ":" -f 1 /etc/passwd
```

## 11. Buat User jagosisop
```bash
sudo adduser jagosisop
```

## 12. Masukkan jagosisop ke sudoers group
```bash
sudo usermod -aG sudo jagosisop
```

## 13. 

## 14. Menjadi User Baru dan Membuat Directory "analysis"
```bash
sudo su - jagosisop -c "mkdir analysis" ; sudo -i -u jagosisop
```

## 15. Ganti User Lama dan Pindah Directory ke Latihan
```bash
exit
```
```bash
cd /ilovelinux/latihan
```

## 16. Unzip S3cr3t_f1L3s.zip
```bash
sudo unzip S3cr3t_f1L3s.zip
```

## 17. Di List Semua File yang Berakhiran .log dan Mengambil log yang Pertama
```bash
cd dump | find -type f  -name "*.log" | rev | cut -d "/" -f 1 | rev | head -n 1
```
