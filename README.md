# 🔐 SecureFile

> Aplikasi enkripsi file dengan **Argon2id + AES-256-GCM** untuk Windows.
> Amankan file pribadi Anda dengan mudah — GUI drag & drop, context menu Explorer, time-lock, dan self-decrypting archive.

[![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)](https://www.python.org/)
[![Platform](https://img.shields.io/badge/Platform-Windows-blue.svg)]()
[![License](https://img.shields.io/badge/License-Free-green.svg)]()
[![Version](https://img.shields.io/badge/Version-2.0-orange.svg)]()

---

## ✨ Fitur

### 🔒 Keamanan
- **Argon2id** — Key Derivation Function dengan parameter RFC 9106
- **AES-256-GCM** — Enkripsi authenticated (AEAD)
- **SHA-256** — Verifikasi integritas file
- **Metadata terenkripsi** — Nama file asli tersembunyi
- **Secure delete** — Hapus file asli dengan overwrite
- **Cegah enkripsi ganda** — File `.psec` tidak bisa dienkripsi lagi
- **Batasan file** — Tolak `.exe`, `.dll`, `.sys`, dll.

### ⏰ Time-Lock (v2.0)
- File hanya bisa dibuka setelah tanggal tertentu
- Cek waktu via **NTP** (pool.ntp.org) + fallback ke lokal
- Auto-fix minimal **6 jam** dari sekarang
- Preview badge dengan warna berbeda (valid/warning/error)

### 📦 Self-Decrypting Archive (v2.0)
- Bikin `.exe` yang bisa dekripsi sendiri
- Penerima cukup double-click, masukkan password, file asli muncul
- Tidak perlu install SecureFile

### 🎨 GUI Modern
- **Drag & drop** file ke area drop
- **Show/Hide password** (tombol 👁 atau `Ctrl+H`)
- **Password generator** (tombol 🎲 atau `Ctrl+G`)
- **Password strength indicator** — real-time
- **Password match indicator** — cek konfirmasi cocok
- **Progress bar dinamis** — warna berubah sesuai progress
- **Recent files** — 5 file terakhir
- **Keyboard shortcuts** — Ctrl+O, Ctrl+D, Ctrl+Q, Ctrl+H, Ctrl+G, Ctrl+C, Enter, Esc
- **Error handling ramah** — pesan manusiawi
- **Clear file** (tombol ✕ atau `Ctrl+D`)
- **3 checkbox dalam 1 baris** — Hapus asli, SDA, Time-lock

### 🖱️ Context Menu Windows
- **Install/Uninstall** via menu File
- **Klik kanan file** → "🔐 Enkripsi dengan SecureFile"
- **Klik kanan .psec** → "🔓 Dekripsi dengan SecureFile"
- **Auto-update** kalau `.exe` dipindahkan
- **Tanpa admin** (pakai HKCU)

### 💻 CLI
- `securefile_cli2.py encrypt <file>` — enkripsi
- `securefile_cli2.py decrypt <file.psec>` — dekripsi
- `securefile_cli2.py info <file.psec>` — info file
- Opsi `--delete` — hapus file asli setelah enkripsi
- Opsi `--unlock "2027-01-01 12:00"` — time-lock

---

## 📸 Screenshot

> *Tambahkan screenshot aplikasi di sini*

---

## 🚀 Instalasi

### Prasyarat
- Python 3.10 atau lebih baru
- Windows 10/11 (untuk context menu & SDA)
- Linux/macOS (GUI & CLI saja)

### Dari Source Code

```bash
# 1. Clone repository
git clone https://github.com/username/securefile.git
cd securefile

# 2. Buat virtual environment
python -m venv venv

# 3. Aktifkan venv
# Windows:
venv\Scripts\activate
# Linux/Mac:
source venv/bin/activate

# 4. Install dependencies
pip install -r requirements.txt

# 5. Jalankan aplikasi
python src/securefile_ui2.py
