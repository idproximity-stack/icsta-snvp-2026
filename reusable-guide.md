# Panduan Penggunaan Kembali (Reusable Guide) Template Landing Page Konferensi

Template ini dirancang agar **sangat mudah digunakan kembali (100% reusable)** untuk konferensi, seminar ilmiah, simposium, atau webinar lainnya tanpa harus menyusun ulang tata letak dan struktur kodenya.

---

## 🎯 1. Cara Mengganti Informasi Konferensi (Checklist Cepat)

Buka file [`index.html`](index.html), lalu cukup cari komentar `[REUSABLE]` atau ubah bagian-bagian berikut:

### A. Meta Tag & SEO (Baris 8 - 45)
- `<title>`: Ubah ke nama konferensi Anda (misal: `ICCS 2027 - International Conference on Computer Science`).
- `<meta name="description">`: Ringkasan 1-2 kalimat tentang acara, penyelenggara, dan target indeks publikasi.
- `<meta name="keywords">`: Kata kunci pencarian (nama konferensi, topik riset, nama kampus).
- `link rel="canonical"`: URL domain website Anda (misal: `https://namakonferensi.org/`).

### B. Google Event Schema / JSON-LD (Baris 47 - 120)
Google menggunakan blok ini untuk menampilkan **Rich Snippet Event** langsung di hasil pencarian.
Sesuaikan properti berikut:
```json
{
  "name": "Nama Lengkap Konferensi Anda",
  "alternateName": "Singkatan (misal: ICCS 2027)",
  "startDate": "2027-10-15T08:30:00+07:00",
  "endDate": "2027-10-17T17:00:00+07:00",
  "location": {
    "name": "Nama Hotel / Kampus Tempat Acara"
  },
  "organizer": {
    "name": "Nama Universitas / Asosiasi Penyelenggara"
  }
}
```

### C. Hero Section & Call for Papers (CFP)
- **Judul & Tema**: Cari teks `<h1>` di bagian `#home`, ubah judul besar dan tema acara.
- **Tracks & Subtopik**: Cari bagian `#tracks`, ubah nama 4 Track dan daftar bullet point topiknya sesuai bidang studi Anda.
- **Keynote Speakers**: Cari bagian `#speakers`, ganti foto, nama dosen/profesor, kampus asal, dan judul presentasi.

### D. Pengaturan Konfigurasi JavaScript (Baris Terakhir)
Di bagian paling bawah file `index.html` terdapat objek `EVENT_SETTINGS`:
```javascript
const EVENT_SETTINGS = {
  // 1. Batas Waktu Countdown (Format: YYYY-MM-DDTHH:MM:SS+07:00)
  submissionDeadline: '2026-08-15T23:59:59+07:00',
  
  // 2. Daftar Biaya Pendaftaran (Otomatis berganti saat tombol IDR/USD diklik)
  prices: {
    idr: {
      regular: "IDR 3.500.000",
      regularIeee: "IDR 3.000.000",
      student: "IDR 2.500.000",
      studentIeee: "IDR 2.000.000",
      attendee: "IDR 1.000.000",
      attendeeVirtual: "IDR 500.000"
    },
    usd: {
      regular: "$300 USD",
      regularIeee: "$250 USD",
      student: "$200 USD",
      studentIeee: "$150 USD",
      attendee: "$100 USD",
      attendeeVirtual: "$50 USD"
    }
  }
};
```

---

## 🚀 2. Mengapa Template Ini SEO-Friendly?

1. **Semantic HTML5 Tagging**: Menggunakan `<header>`, `<nav>`, `<main>`, `<section>`, `<article>`, `<figure>`, `<figcaption>`, dan `<footer>` secara teratur.
2. **Heading Hierarchy (H1 - H3)**: Hanya ada satu elemen `<h1>` di halaman untuk mempertahankan bobot SEO tertinggi.
3. **Optimasi Gambar**: Setiap tag `<img>` sudah dilengkapi atribut `alt` deskriptif berbasis kata kunci, `loading="lazy"` agar halaman ringan, serta dimensi `width` dan `height` eksplisit untuk mencegah *Cumulative Layout Shift (CLS)*.
4. **Open Graph & Twitter Cards**: Tautan halaman akan otomatis memunculkan thumbnail gambar, judul tebal, dan deskripsi saat dibagikan ke WhatsApp, Telegram, LinkedIn, Twitter/X, atau Facebook.
5. **Google Rich Snippet Ready**: Dilengkapi Schema `EducationEvent` JSON-LD standar Google.
6. **File Pendukung Crawling**: Disertakan [`robots.txt`](robots.txt) dan [`sitemap.xml`](sitemap.xml).

---

## 🌐 3. Cara Publikasi Gratis (Hosting)

Template ini berupa file HTML statis murni sehingga bisa di-hosting secara gratis di:
- **GitHub Pages**: Buat repositori baru &rarr; unggah `index.html`, `robots.txt`, `sitemap.xml` &rarr; aktifkan Pages di Settings.
- **Vercel / Netlify**: Cukup *drag and drop* folder proyek ke dashboard Vercel / Netlify.
- **cPanel / Web Hosting Kampus**: Unggah semua file langsung ke direktori `public_html`.
