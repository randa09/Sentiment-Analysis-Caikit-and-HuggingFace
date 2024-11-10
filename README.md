# Layanan Inference Sentimen Teks

Repositori ini memberikan contoh cara menggunakan layanan inference berbasis gRPC untuk analisis sentimen teks. Kode ini menjalankan analisis sentimen pada dua teks sampel dalam bahasa Indonesia menggunakan model analisis sentimen yang di-host secara lokal melalui server gRPC.

## Pengertian Text Sentiment Analysis Menggunakan Caikit dan Hugging Face

**Analisis Sentimen Teks** adalah proses mengidentifikasi dan mengklasifikasikan emosi atau opini dalam teks, apakah positif, negatif, atau netral. Dalam proyek ini, analisis sentimen dilakukan menggunakan **Caikit**, sebuah framework yang memfasilitasi pembangunan dan integrasi layanan inference berbasis Machine Learning, dan model dari **Hugging Face**, platform populer yang menyediakan model pra-latih untuk berbagai tugas NLP (Natural Language Processing). Dengan menggunakan model dari Hugging Face, kita dapat menjalankan analisis sentimen teks secara akurat untuk memahami opini atau sentimen dari teks yang diberikan.

## Deskripsi

Kode ini menggunakan `ServicePackageFactory` dari Caikit untuk menyiapkan klien inference untuk analisis sentimen. Teks input dikirim ke model, dan hasil prediksi sentimen dikembalikan untuk setiap teks yang diberikan.

## Persyaratan

Pastikan Anda telah menginstal dependensi berikut untuk menjalankan kode ini:
- **gRPC**: Digunakan untuk panggilan prosedur jarak jauh (remote procedure call).
- **Caikit Runtime**: Menyediakan `ServicePackageFactory` untuk konfigurasi layanan.
- **Model Data Sentimen Teks**: Termasuk kelas `TextInput` untuk menangani input teks sebagai pesan protocol buffer.

## Rangkuman Kode

- `ServicePackageFactory` membuat klien layanan inference.
- Sebuah saluran gRPC lokal dibuat pada `localhost` di port `8085`.
- Dua teks sampel dikirim ke model analisis sentimen:
  1. "Aku ingin mendapatkan dia"
  2. "Aku ingin diterima lulus"
- Untuk setiap teks, permintaan prediksi sentimen dibuat dan dikirim.
- Hasil analisis sentimen dicetak di konsol.

## Cara Menggunakan

1. **Menyiapkan Klien**: Klien diinisialisasi dengan saluran gRPC yang mengarah ke `localhost:8085`.
2. **Inference**: Untuk setiap teks sampel, permintaan sentimen dibuat dan dikirim. ID model ditentukan dalam metadata sebagai `text_sentiment`.
3. **Output**: Hasil analisis sentimen untuk setiap teks dicetak.

## Contoh Output

```plaintext
Teks: Aku ingin mendapatkan dia
RESPON: <Hasil Prediksi Sentimen>

Teks: Aku ingin diterima lulus
RESPON: <Hasil Prediksi Sentimen>



