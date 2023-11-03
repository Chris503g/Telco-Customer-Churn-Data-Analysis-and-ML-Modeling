# Telco Customer Churn Data Analysis and ML Modeling

## Context
Di industri telekomunikasi yang sangat kompetitif, banyak penyedia layanan menawarkan beragam layanan termasuk paket ponsel, layanan internet, dan TV kabel. Persaingan yang ketat ini menjadi tantangan besar bagi perusahaan telekomunikasi dalam mempertahankan pelanggan. Perpindahan pelanggan dapat berdampak langsung pada pendapatan perusahaan.

Pelanggan mungkin berhenti berlangganan layanan telekomunikasi karena berbagai alasan, termasuk ketidakpuasan dengan kualitas layanan, harga yang tinggi, penawaran lebih menarik dari pesaing, atau masalah teknis. Sifat dinamis dan terus berubahnya preferensi pelanggan dan kondisi pasar menegaskan perlunya pendekatan proaktif dalam mempertahankan pelanggan.

## Problem Statement

Perusahaan perlu mengidentifikasi faktor-faktor utama yang menyebabkan pelanggan beralih dari layanan mereka. Hal ini bertujuan untuk merumuskan strategi yang efektif dalam mempertahankan pelanggan dan mengurangi angka churn. Dengan ini, perusahaan dapat meningkatkan penjualan, mempertahankan pangsa pasar pelanggan, dan mengoptimalkan faktor-faktor yang menjadi daya tarik utama layanan mereka.

## Goals

1. Mengembangkan kemampuan untuk memprediksi churn pelanggan.
2. Memahami faktor-faktor yang mempengaruhi keputusan pelanggan dalam churn.

## Analytic Approach

- **Data Analysis:** Menganalisis data untuk mengidentifikasi faktor-faktor churn pelanggan dari perusahaan telekomunikasi.
- **ML Modeling:** Membangun model klasifikasi untuk memprediksi probabilitas seorang customer akan churn atau tidak.

## Metric Evaluation

- **True Negative (TN):** Jumlah pengamatan yang benar-benar diprediksi tidak akan churn dan sebenarnya tidak churn.
- **False Positive (FP):** Jumlah pengamatan yang diprediksi akan churn tetapi sebenarnya tidak churn.
- **False Negative (FN):** Jumlah pengamatan yang diprediksi tidak akan churn tetapi sebenarnya churn.
- **True Positive (TP):** Jumlah pengamatan yang benar-benar diprediksi akan churn dan sebenarnya churn.

### Type 1 Error: False Positive
- **Konsekuensi:** Mengakibatkan pengeluaran tambahan untuk retain customer yang sebenarnya tidak perlu mendapatkan perhatian tambahan.

### Type 2 Error: False Negative
- **Konsekuensi:** Mengakibatkan kehilangan customer karena tidak memberikan perhatian atau layanan tambahan kepada mereka.

#### Biaya Dampak False Negatives (FN) dan False Positives (FP)

- **Biaya FN:** Kehilangan pendapatan bulanan, biaya rekrutmen pelanggan baru (diperkirakan sekitar $100 - $200 per pelanggan).
- **Biaya FP:** Biaya tambahan untuk mempertahankan pelanggan yang sebenarnya tidak akan churn (sekitar $50 - $100 per bulan per pelanggan).

**Recall (True Positive):** Metrik evaluasi yang fokus pada perbaikan performa model untuk mengurangi False Negatives dan dampak finansial yang diakibatkannya.

## Data Understanding

- **Data Source:** [Telco Customer Churn Dataset](https://www.kaggle.com/datasets/blastchar/telco-customer-churn)

### Attribute Information

| Attribute         | Data Type  | Description                                      |
|-------------------|------------|--------------------------------------------------|
| customerID        | Object     | Pengidentifikasi unik untuk setiap pelanggan.            |
| gender            | Object     | Jenis kelamin pelanggan.                              |
| SeniorCitizen     | Int64      | Menunjukkan apakah pelanggan adalah warga senior (1 untuk ya, 0 untuk tidak). |
| Partner           | Object     | Menunjukkan apakah pelanggan memiliki pasangan.       |
| Dependents        | Object     | Menunjukkan apakah pelanggan memiliki tanggungan.      |
| tenure            | Int64      | Jumlah bulan pelanggan telah menggunakan layanan perusahaan. |
| PhoneService      | Object     | Menunjukkan apakah pelanggan menggunakan layanan telepon. |
| MultipleLines     | Object     | Menunjukkan apakah pelanggan memiliki beberapa jalur telepon. |
| InternetService   | Object     | Jenis layanan internet yang diikuti oleh pelanggan. |
| OnlineSecurity    | Object     | Menunjukkan apakah pelanggan memiliki layanan keamanan online. |
| OnlineBackup      | Object     | Menunjukkan apakah pelanggan memiliki layanan cadangan online. |
| DeviceProtection  | Object     | Menunjukkan apakah pelanggan memiliki layanan perlindungan perangkat. |
| TechSupport       | Object     | Menunjukkan apakah pelanggan memiliki layanan dukungan teknis. |
| StreamingTV       | Object     | Menunjukkan apakah pelanggan memiliki layanan TV streaming. |
| StreamingMovies   | Object     | Menunjukkan apakah pelanggan memiliki layanan streaming film. |
| Contract          | Object     | Jenis kontrak (misalnya, bulan demi bulan, satu tahun, dua tahun). |
| PaperlessBilling  | Object     | Menunjukkan apakah pelanggan menggunakan tagihan tanpa kertas. |
| PaymentMethod     | Object     | Metode pembayaran yang digunakan oleh pelanggan. |
| MonthlyCharges    | Float64    | Biaya langganan bulanan yang dibayarkan oleh pelanggan. |
| TotalCharges      | Object     | Total biaya yang dibayarkan oleh pelanggan. |
| Churn             | Object     | Menunjukkan apakah pelanggan telah berhenti berlangganan (ya atau tidak). |


**Dataset ini mencakup informasi tentang:**
- **Pelanggan yang meninggalkan layanan dalam sebulan terakhir** –  *Churn column*
- **Layanan yang diikuti setiap pelanggan** – *phone, multiple lines, internet, online security, online backup, device protection, tech support, and streaming TV and movies*
- **Informasi akun pelanggan** – *how long they’ve been a customer, contract, payment method, paperless billing, monthly charges, and total charges*
- **Info demografis tentang pelanggan** – *gender, age range, and if they have partners and dependents*

## Predictive Analysis and ML Modeling

1. **Eksplorasi Data:** Menjelajahi dan membersihkan data untuk persiapan model.
2. **Pemodelan ML:** Menggunakan metode klasifikasi untuk membangun model prediksi churn pelanggan.

