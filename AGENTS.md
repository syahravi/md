# md (Markdown editor)

Editor Markdown satu halaman dengan pratinjau langsung dan LaTeX (MathJax), fork "Writing" milik Joseph Ernest (MIT) yang di-brand ulang seperti syahravi.id. UI bahasa Inggris ("I" → "you"), audiens umum, dideploy ke `md.syahravi.id`.

## Development

- Situs statis, tanpa build dan tanpa `package.json`. Buka `index.html`, atau layani foldernya: `rtk npx wrangler dev`.
- Semua perintah shell lewat `rtk`.
- Kode editor upstream (`Markdown.*.js`, `mathjax-editing_writing.js`) jangan diubah tanpa alasan; hanya `index.html`, `styles.css`, dan aset brand yang milik proyek ini.
- Cek visual di 320, 768, dan 1440 px sebelum bilang selesai. Pintasan keyboard, mode gelap, dan `@media print` harus tetap jalan.
- OG image: render ulang `og-image.png` dari `scripts/og-image.html` (perintah Edge di komentar file).
- Deploy memakai `wrangler.jsonc`; file non-situs disaring di `.assetsignore`. Jangan deploy tanpa diminta.

## Batas produk

- Tetap satu halaman yang langsung berupa editor (Landing Page = Working Page): tanpa akun, backend, atau data yang dikirim ke server. Klaim "teks tidak meninggalkan browser" di dialog bantuan dan README harus tetap benar; satu-satunya request pihak ketiga adalah MathJax dari cdnjs.
- Kunci localStorage `writing`, `latex`, `darkmode`, `serif` dipertahankan agar dokumen pengguna tetap terbaca.
- Mode gelap tetap ada sebagai toggle pengguna (keputusan pemilik 2026-11-25), dibuat dari token yang ada tanpa warna baru. Lisensi MIT dan atribusi Joseph Ernest tetap tercantum.

## Konteks lintas proyek

Konvensi lintas proyek Syahravi ada di Notion, halaman "Konteks":
https://app.notion.com/p/syahravi/Konteks-422a8d79be748108a83cd8e4574c05f6
Akses lewat Notion API, token di env `NOTION_API_TOKEN` (cara pakai: Konteks › Meta › "AGENTS.md — Konteks"). Jangan menulis nilai token ke file, log, atau pesan.

- Catatan proyek ini: halaman "md (Markdown editor)" di database Projects (https://app.notion.com/p/md-Markdown-editor-423a8d79be7481c79da8f227db112015)
- Wajib dibaca: Bahasa › "Bahasa & tone", Teknis › "Stack default", Teknis › "Konvensi kode", Teknis › "Deploy Cloudflare", Desain › "Brand pribadi", Desain › "Prinsip desain"
- Brand: mengikuti syahravi.id (Desain › "Brand pribadi", "Prinsip desain"); alur tool baru: Meta › "Alur tool baru (vibe coding)". tokens.css disalin dari repo syahravi.id (tanpa blok "Trusted Partner"), jangan diubah di sini.
- Kalau aturan Konteks bertentangan dengan repo ini, Konteks yang menang. Fakta proyek (stack, versi, token desain, domain) tetap dari repo; selisihnya dilaporkan. Kalau aturan Konteks dinilai keliru, tetap ikuti, lalu sampaikan kritik membangun dan saran yang didukung riset (sumber ditautkan) ke user.
- Akhir sesi: kalau fakta proyek berubah atau ada temuan selisih, perbarui halaman proyek ini di Notion lewat API (Meta › "Alur proyek", "Penutup sesi"). Aturan lintas proyek tidak diubah langsung; usulan masuk "Keputusan terbuka".
