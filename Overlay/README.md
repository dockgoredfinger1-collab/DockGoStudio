# 🎮 Stream Overlay Manager

All-in-one overlay untuk OBS/Prism Studio — gabungkan Saweria Alert, Leaderboard, Running Text, TikTok Counter, dan custom widget dalam satu Browser Source.

---

## 📁 Struktur File

```
repo-kamu/
├── index.html       ← Form setup (isi URL overlay)
├── overlay.html     ← Overlay utama (dipasang di OBS/Prism)
├── control.html     ← Panel kontrol toggle (buka di browser/HP)
├── overlay-bg.mp4   ← Video background kamu (upload sendiri)
└── README.md
```

---

## 🚀 Cara Deploy ke GitHub Pages

### 1. Buat Repository
- Buka [github.com](https://github.com) → **New repository**
- Nama repo bebas, misal: `stream-overlay`
- Set ke **Public**
- Klik **Create repository**

### 2. Upload File
- Di halaman repo → klik **Add file** → **Upload files**
- Upload semua file: `index.html`, `overlay.html`, `control.html`, `README.md`
- **Upload juga file video** kamu (misal `overlay-bg.mp4`) ke folder yang sama
- Klik **Commit changes**

### 3. Aktifkan GitHub Pages
- Masuk ke **Settings** → scroll ke **Pages**
- Di **Source**, pilih branch: `main`, folder: `/ (root)`
- Klik **Save**
- Tunggu 1-2 menit → URL GitHub Pages kamu akan muncul

  Contoh URL: `https://username.github.io/stream-overlay/`

---

## 🎯 Cara Pakai

### Setup Awal
1. Buka `https://username.github.io/stream-overlay/index.html`
2. Isi semua URL overlay (Saweria, dll)
3. Masukkan nama file video background (yang sudah diupload ke GitHub)
4. Klik **Generate Link Overlay**
5. Copy link overlay yang muncul

### Pasang di OBS/Prism
1. Tambahkan **Browser Source** baru
2. Paste link overlay
3. Set **Width: 1920**, **Height: 1080**
4. Centang **Shutdown source when not visible** (opsional)
5. Klik OK

### Panel Kontrol
1. Klik tombol **🎛️ Buka Panel Kontrol** setelah generate
2. Buka di browser lain atau HP
3. Toggle tiap overlay on/off secara real-time
4. Tap TikTok counter manual
5. Edit dan update running text

> ⚠️ Panel kontrol dan overlay harus dibuka di **browser yang sama** agar BroadcastChannel bekerja. Di HP, buka `control.html` di browser HP yang sama jaringannya.

---

## 🔧 Daftar Parameter URL

Kamu juga bisa edit URL overlay manual:

| Parameter | Keterangan |
|-----------|-----------|
| `video` | Nama file video background (misal `overlay-bg.mp4`) |
| `alert` | URL Saweria Alert widget |
| `leaderboard` | URL Saweria Leaderboard widget |
| `ticker` | Teks ticker, pisah dengan `\|` |
| `tiktok` | URL widget TikTok pihak ketiga (opsional) |
| `custom1` | URL custom widget 1 |
| `custom2` | URL custom widget 2 |
| `hidden` | Slot yang disembunyikan saat mulai, pisah koma (misal `custom1,custom2`) |

---

## 🗺️ Layout Default

```
┌─────────────────────────────────────────┐
│ [TikTok]              [Leaderboard]     │
│  kiri atas             kanan atas       │
│                                         │
│ [Custom1]                               │
│                                         │
│              [Alert]        [Custom2]   │
│─────────────────────────────────────────│
│           [Running Text Ticker]         │
└─────────────────────────────────────────┘
```

---

## 💡 Tips

- **Video background** sebaiknya WebM dengan alpha channel untuk transparansi penuh
- **Saweria URL** ambil dari dashboard Saweria → Widget → salin URL embed
- Gunakan **HP sebagai remote control** buka `control.html` dari HP saat streaming
- Untuk **TikFinity/StreamerBot**, masukkan URL widget-nya ke field TikTok Counter
