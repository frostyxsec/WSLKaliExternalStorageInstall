# 💻 Install Kali Linux WSL di External Drive (E:\)

Panduan lengkap untuk menginstal Kali Linux di Windows Subsystem for Linux (WSL) **langsung ke drive eksternal (E:\)**

---

## 📦 Tahap 1: Install Kali Linux via Microsoft Store

1. Buka Microsoft Store
2. Cari **Kali Linux**, lalu install
3. Jalankan Kali dari Start Menu dan selesaikan setup awal

---

## 🧰 Tahap 2: Export Kali Linux ke File `.tar`

```powershell
wsl --export kali-linux E:\WSL\Kali\kali-export.tar
```

> Pastikan folder `E:\WSL\Kali` sudah dibuat sebelumnya

---

## 💾 Tahap 3: Import Kali Linux ke Drive E:\

```powershell
wsl --import KaliE E:\WSL\Kali E:\WSL\Kali\kali-export.tar --version 2
```

- `KaliE` = nama WSL instance baru
- `E:\WSL\Kali` = lokasi file system-nya
- `--version 2` = gunakan WSL 2

---

## 🔐 Jalankan Kali dari Drive E:\ & Pengaturan Hindari Login Sebagai Root Default

```powershell
wsl -d KaliE -u <nama user yang kamu setup>
```
```powershell
nano ~/.bashrc
```
baris paling atas taruh kata "cd"

---

## ✅ Hasil Akhir

- Kali Linux berjalan dari **drive E:\**
- Tidak auto-login sebagai root
- Siap digunakan untuk testing, pentest, atau development

---

## 📌 Catatan

- Jangan lupa untuk menyalakan fitur **WSL** dan **Virtual Machine Platform** dari Windows Feature sebelum memulai.
- Pastikan Windows kamu sudah mendukung **WSL 2** (Windows 10 2004+ / Windows 11)
- Ketika sudah selesai digunakan, jangan lupa eject external storage dan ketik
```powershell
wsl --shutdown
```

---

## 📎 Lisensi

Distribusi Kali Linux mengikuti lisensi [Offensive Security](https://www.kali.org/docs/policy/kali-linux-licensing/)

---
