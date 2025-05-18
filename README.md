# fix-block-apache2-ubuntu

# 1. Hentikan dan Nonaktifkan Apache
```bash
sudo systemctl stop apache2
sudo systemctl disable apache2
```

# 2. Hapus Apache dan Semua Dependensinya
```bash
sudo apt remove --purge apache2 apache2-utils apache2-bin apache2.2-common -y
sudo apt autoremove -y
```

# 3. Cek dan Hapus Sisa Konfigurasi (Jika Ada)
```bash
sudo rm -rf /etc/apache2
```

# 4. Blokir Apache Agar Tidak Terinstal Lagi Otomatis
```bash
sudo apt-mark hold apache2 apache2-utils apache2-bin
```

# 5. Pastikan Nginx Aktif
```bash
sudo systemctl enable nginx
sudo systemctl start nginx
sudo systemctl status nginx
```
