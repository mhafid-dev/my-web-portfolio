# Design Analysis — STRATOS Dashboard

Analisis visual language dari referensi dashboard "STRATOS" (travel/expense management admin panel).

## 1. Color Palette

**Base (dark theme, near-black, bukan pure black)**
- Background utama: `#0A0A0C` – `#0D0D10` (hitam kebiruan/off-black)
- Surface panel/card: `#131316` – `#17171B` (satu level lebih terang dari background, border tipis membedakan)
- Border/divider: `#232327` – `#2A2A2E` (abu gelap, low-contrast, hanya untuk pemisah halus)

**Text**
- Primary text: `#F5F5F5` (hampir putih, dipakai untuk angka besar & heading)
- Secondary/label text: `#8A8A90` – `#9A9AA0` (abu redup, untuk label uppercase kecil & metadata)
- Muted/disabled: `#5A5A60` (contoh: status "DRAFT")

**Accent / Brand**
- Merah-oranye terang: `#FF3B30` – `#FF4433` — warna signature brand. Dipakai untuk: logo mark, nav item aktif, tombol primer ("BOOK TRIP"), badge peringatan/error, alert dot.

**Semantic status colors**
- Sukses/Approved/Completed: hijau terang `#2ECC71` / `#3DDC84`, dengan background hijau sangat gelap-transparan sebagai pill badge
- Pending/Warning: kuning-amber `#E8B339` / `#D9A441`
- Error/Out of Policy/Overdue: merah `#FF4433` (sama dengan accent brand — sengaja overload agar "urgent" selalu terbaca sebagai warna brand)
- Neutral/Draft: abu `#5A5A60`

**Karakteristik palet**
- Sangat low-saturation di background & surface, tapi high-saturation dan punchy di accent & semantic colors → menciptakan kontras tinggi yang membuat data/status langsung "melompat" ke mata.
- Termasuk kategori *dark mode operational/fintech UI* — mirip aesthetic trading terminal, bukan dark mode konsumer yang soft.

## 2. Typography Style

- **Font family**: monospace atau grotesque-mono hybrid (kesan seperti `JetBrains Mono`, `IBM Plex Mono`, atau `Space Mono`) — terlihat dari lebar karakter seragam pada angka dan label.
- **Case**: hampir seluruh label, nav, dan heading section memakai **UPPERCASE**, sering dengan letter-spacing yang dilebarkan (tracking positif, ~0.05–0.1em). Ini kuat menjadi ciri khas sistem ini.
- **Hierarchy**:
  - Angka metrik besar (mis. `$48,320`, `24`, `91%`) → bold, ukuran besar (~28–32px), warna putih penuh — jadi focal point tiap card.
  - Section label (`// OVERVIEW`, `// RECENT TRIPS`) → kecil (~11–12px), uppercase, prefix `//` seperti komentar kode — motif berulang yang memperkuat kesan "developer/technical console".
  - Body/data row text → medium (~13–14px), regular weight, campuran huruf besar-kecil untuk nama & rute, tetap uppercase untuk kategori (`ENGINEERING`, `SALES`).
  - Micro text (delta indicator `+12.4% VS LAST MO`, timestamp) → paling kecil, warna muted.
- **Numeric alignment**: angka-angka (cost, currency) rata kanan dan tabular, khas dashboard finansial agar mudah di-scan vertikal.

## 3. Spacing Pattern

- **Grid-based, sangat terstruktur**: layout memakai grid kolom dengan gutter konsisten (~16–24px) antar card di top-stats row (4 kolom sejajar).
- **Density tinggi tapi tidak sesak**: padding internal card sedang (~20–24px), cukup napas tapi tetap compact — cocok untuk aplikasi data-heavy yang perlu menampilkan banyak informasi tanpa scroll berlebihan.
- **Baris tabel (table rows)**: padding vertikal konsisten (~14–16px per row), dipisahkan hairline border tipis, bukan zebra-striping — menjaga tampilan tetap flat dan minim noise.
- **Sidebar**: grouping berbasis section header kecil (`// OVERVIEW`, `// MANAGE`) dengan spacing lebih lega di antar grup dibanding antar item dalam grup — pola "visual chunking".
- **Corner radius**: kecil/tajam (~4–6px), bukan rounded besar → memperkuat kesan "teknis/presisi" dibanding UI yang playful.
- **Alignment**: sangat grid-locked — label, angka, dan badge status semuanya align konsisten di kolom yang sama antar card/row, menciptakan ritme visual yang rapi.

## 4. Overall Aesthetic Feel

- **"Command center" / operational console** — jauh dari SaaS dashboard umum yang soft & rounded; ini terasa seperti terminal trading, monitoring tool, atau ops dashboard (mengingatkan pada Linear, Vercel dashboard, atau terminal Bloomberg-lite).
- **Kata kunci**: *technical, precise, high-contrast, data-dense, monospace-driven, dark-first, utilitarian-brutalist*.
- **Motif berulang yang mendefinisikan identitas**:
  - Prefix `//` di setiap section title (komentar-kode sebagai elemen dekoratif)
  - Badge status berbentuk pill kecil dengan ikon (⊘, ⚠) + uppercase text
  - Satu warna accent merah-oranye dipakai konsisten untuk brand DAN urgency, menciptakan bahasa visual yang efisien
  - Micro-indicator tren (↗ +12.4%) di bawah tiap angka besar
- **Kesan yang ingin dibangun**: kepercayaan lewat presisi dan clarity, bukan lewat dekorasi. Cocok untuk audiens profesional (finance ops, admin, travel manager) yang butuh scan data cepat, bukan pengalaman visual yang "menghibur".
- **Kontras dark UI**: alih-alih flat gray-on-black yang membosankan, palet ini hidup karena accent merah yang berani dan badge semantik hijau/kuning yang jenuh — jadi tetap "dark mode" tapi tidak terasa mati/monoton.
