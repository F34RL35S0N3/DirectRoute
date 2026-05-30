## 1️⃣ Daftar Dependensi & Teknologi

Proyek ini dibangun menggunakan arsitektur modern berbasis microservices & serverless:

### Frontend
- **React 18** - UI Framework
- **Vite** - Build tool dan dev server
- **TypeScript** - Type-safe development
- **TailwindCSS** - Styling dengan Glassmorphism UI
- **Mapbox-gl / react-map-gl** - Interactive mapping
- **Lucide-react** - Icon library

### Backend
- **Node.js (v18+)** - Runtime environment
- **Express.js** - Web framework (AI Proxy, Scraping Cache, API Handler)

### Database & Authentication
- **Supabase** - PostgreSQL database dengan Row Level Security (RLS)
- **Database Triggers** - Automated events

### External APIs & AI
- **Google Maps API** - Geocoding dan route optimization (distance matrix)
- **Serper API** - Market research dan data aggregation
- **LLM API** - OpenRouter / Ollama untuk AI Agents

---

## 2️⃣ Panduan Singkat Cara Menjalankan Aplikasi Secara Lokal

Proyek terbagi menjadi dua bagian: `/frontend` dan `/backend`. Keduanya harus dijalankan secara bersamaan.

### Prasyarat
- Node.js v18+
- Akun Supabase
- API Keys: Google Maps, Serper.dev, OpenRouter/OpenAI

### Setup Database (Supabase)
1. Buat proyek baru di [Supabase](https://supabase.com/)
2. Buka **SQL Editor** di Supabase
3. Jalankan file SQL dari `backend/supabase/sql/` secara berurutan (dari `00_core_schema.sql` hingga `42_soft_delete_orders.sql`)

### Menjalankan Backend
```bash
cd backend
npm install

# Buat file .env dengan isi:
PORT=3000
SECRET_KEY=kunci_rahasia_jwt
SERPER_API_KEY=your_serper_api_key
GOOGLE_MAPS_API_KEY=your_google_maps_key
OPENROUTER_API_KEY=your_openrouter_key

npm start
# (Windows: jalankan ./run-server.ps1)
```
Backend akan berjalan di `http://localhost:3000`

### Menjalankan Frontend
Buka terminal baru:
```bash
cd frontend
npm install

# Buat file .env.local dengan isi:
VITE_SUPABASE_URL=your_supabase_url
VITE_SUPABASE_ANON_KEY=your_anon_key
VITE_API_BASE_URL=http://localhost:3000

npm run dev
```
Frontend akan berjalan di `http://localhost:5173`

---

## 3️⃣ Cara Menjalankan Fitur Utama

Setelah aplikasi berjalan dan Anda login sebagai **Seller (Petani/UMKM)**:

### Menggunakan Price Strategist (AI Pricing)
1. Masuk ke **Seller Dashboard**
2. Isi form penawaran produk (nama komoditas, lokasi, stok dalam kg)
3. Klik tombol **"Gunakan AI"**
4. AI secara otomatis menarik data harga dari BPS/PIHPS dan memberikan rekomendasi harga pasaran (*Fair Price*)

### Menggunakan Outreach Agent (AI Communication)
1. Setelah harga disetujui, sistem menampilkan **Dynamic Outreach AI**
2. Pilih gaya penawaran (formal/kasual)
3. Salin draf pesan atau kirim langsung ke WhatsApp pembeli B2B

### Menggunakan Logistics Orchestrator (Route Optimization)
1. Tunggu pembeli melakukan pemesanan di Buyer Dashboard
2. Order akan muncul di Seller Dashboard
3. Centang order dan klik **"Cari Rute Optimal"**
4. Google Maps akan menampilkan rute pengiriman multi-drop paling efisien (max 500kg)

---

## 📊 Dampak
Sistem ini diproyeksikan mampu:
- **Meningkatkan margin petani hingga +40%**
- **Mengurangi biaya logistik sebesar 20%**
- **Menciptakan direct route (rute langsung)** yang adil untuk semua pihak

*Saatnya petani jadi Juragan di negerinya sendiri.* 🇮🇩
