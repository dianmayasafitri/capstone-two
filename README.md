# Analisis Data Penjualan SaaS (SaaS Sales Data Analysis) 

Proyek ini menyajikan analisis komprehensif (Data Cleaning, EDA, dan Cohort Analysis) terhadap dataset penjualan Software as a Service (SaaS). Tujuannya adalah untuk mengidentifikasi karakteristik utama dari data penjualan guna menginformasikan keputusan strategis bisnis terkait optimasi keuntungan, retensi pelanggan, dan kebijakan diskon.
Analisis ini disusun untuk mendapatkan insight dari data dan memberikan action plan untuk meningkatkan retensi dan profit perusahaan dengan cara sebegai berikut:
- Mengidentifiksi hubungan antara volume penjualan (Sales), diskon (Discount), dan keuntungan (Profit).
- Mengidentifikasi negara, industri, dan produk mana saja yang berkontribusi signifikan pada profit.
- Mengevaluasi produk mana yang paling menguntungkan dan mana yang perlu ditinjau ulang. 
- Retensi Pelanggan (Cohort Analysis): Melacak perilaku pelanggan dari waktu ke waktu untuk mengidentifikasi churn rate dan meningkatkan Customer Lifetime Value/CLV pelanggan. CLV adalah perkiraan nilai keuntungan bersih total yang akan diperoleh perusahaan dari keseluruhan hubungan dengan satu pelanggan di masa depan.

## Sumber Data
Analisis menggunakan dataset SaaS-Sales.csv, yang berisi informasi detail transaksi penjualan SaaS.

## Deskripsi Kolom
Dataset ini terdiri dari 9.994 baris dan 19 kolom, beberapa di antaranya:
Kolom
Deskripsi
Contoh
Order Date
Tanggal pesanan dibuat.
11/9/2022
Country, Region
Detail geografis pelanggan.
United States, EMEA
Industry, Segment
Industri dan segmen pelanggan.
Finance, SMB
Product
Nama produk yang dipesan.
Marketing Suite
Sales
Nilai total penjualan.
22638.48
Discount
Persentase diskon yang diterapkan.
0.45
Profit
Keuntungan atau kerugian transaksi.
-383.0310

## Data Cleaning
- Missing Values: Ditemukan nol missing values.
- Tipe Data: Mengubah kolom Order Date ke format datetime.
- Standardisasi Teks: Melakukan standarisasi kolom Product (misalnya, FinanceHub menjadi Finance Hub dan memperbaiki Saa S menjadi SaaS) menggunakan Regular Expressions (re) untuk menyeragamkan penulisan.
- Data Duplikat: Ditemukan nol data duplikat.

## Summary Statistics (numerical & categorical)
- Rata-rata Keuntungan per transaksi adalah $28.66.
- Standard Deviasi Profit = 234.26 yang tinggi menunjukkan adanya variasi ekstrem.
- Pelanggan Terbesar: Allianz dengan 192 total transaksi.
- Fokus Geografis: United States dengan volume pesanan tertinggi (2.001 pesanan), dan region EMEA mendominasi secara keseluruhan (4.219 pesanan).
- Basis Pelanggan: Industri Finance dan segmen SMB (Small Medium Business) adalah basis pelanggan utama.

## Rekomendasi Bisnis
1. Analisis Diskon
Sebanyak 17.5% transaksi berakhir dengan kerugian. Analisis distribusi diskon menunjukkan bahwa:
- Transaksi Profit didominasi oleh diskon rendah (sekitar 0% dan 20%).
- Transaksi Loss (kerugian) sangat terkonsentrasi pada diskon tinggi (>20% hingga 80%).
*Rekomendasi: Kebijakan diskon tinggi adalah sumber utama kerugian. Perusahaan harus meninjau ulang atau membatasi diskon di atas 20% secara ketat.*

2. Kinerja Produk & Industri
- Tim manajemen harus memprioritaskan retensi pelanggan di 5 industri teratas yang menghasilkan profit: Finance, Energy, Tech, Manufacturing, dan Healthcare.
- Produk seperti SaaS Connector Pack - Gold dan One View menghasilkan margin keuntungan yang sangat kecil relatif terhadap biaya operasional.
*Rekomendasi: Kurangi promosi dan alokasi sumber daya pada produk dengan margin profit sangat kecil, dan fokuskan upaya ke produk dengan profit margin tinggi.*

3. Sales Value vs. Profitabilitas
- Uji statistik menunjukkan bahwa tidak ada perbedaan signifikan Sales antara Profit dan Loss (p-value = 0.05710018134522).
- Ini berarti bisa jadi ada faktor lain (misalnya diskon, segmentasi pelanggan, memaksimalkan sumber daya untuk pemasaran produk tertentu, dll.) yang lebih menjelaskan kenapa transaksi menjadi Profit atau Loss dibanding Sales itu sendiri.

4. Cohort Analysis
Analisis retensi pelanggan menunjukkan pola churn yang tajam dari Bulan ke-0 ke Bulan ke-1 dan di sepanjang 8 periode pertama.
- Periode Kritis: Mayoritas pelanggan pergi segera setelah bulan pertama atau kedua. Ini mengindikasikan masalah pada pengalaman onboarding atau Time-to-Value (TTV)—waktu yang dibutuhkan pelanggan untuk merasakan manfaat produk—atau kesenjangan antara janji pemasaran dengan realitas produk.
- Kunci Loyalitas: Pelanggan yang bertahan melewati 3-4 bulan pertama cenderung menjadi pelanggan yang loyal.
*Rekomendasi Retensi: Fokus harus dialihkan untuk mempercepat TTV dan memperbaiki proses onboarding untuk membantu pelanggan melewati periode kritis 3 bulan pertama.*

## Tools yang digunakan:
- Python
- Pandas & NumPy untuk pemrosesan data.
- Matplotlib & Seaborn untuk visualisasi data.
- SciPy.stats untuk pengujian statistik.

