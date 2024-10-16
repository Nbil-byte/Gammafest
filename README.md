


# Handwriting Recognition Training for Election Survey with MMOCR

Proyek ini merupakan penyelesaian dari sebuah kompetisi yang berfokus pada pengenalan tulisan tangan untuk mendukung survei dalam konteks pemilihan umum. Dalam kompetisi ini, peserta diminta untuk membangun model yang dapat mengenali angka dalam gambar digit tulisan tangan yang merepresentasikan jumlah suara untuk setiap pasangan calon di Tempat Pemungutan Suara (TPS). Proyek ini menggunakan [MMOCR](https://github.com/open-mmlab/mmocr), sebuah toolbox untuk deteksi dan pengenalan teks, untuk melatih model pengenalan tulisan tangan.

## Overview Kompetisi

Dalam skenario pemilihan umum yang terjadi di negara fiktif Nusantara, terdapat tiga pasangan calon yang bersaing untuk memenangkan pemilihan. Salah satu pasangan, paslon nomor urut 2, meminta dilakukan survei terkait persentase suara yang mereka peroleh di setiap TPS. Gambar digit tulisan tangan yang dikumpulkan mencakup suara sah dari ketiga pasangan calon. Peserta kompetisi diminta untuk membangun model pembelajaran mesin yang dapat mengenali angka dalam gambar tersebut, lalu menghitung persentase suara sah untuk pasangan calon nomor 2 di setiap TPS.

### Formula untuk Menghitung Persentase Suara Paslon Nomor 2:

\[
\text{persentase} = \left( \frac{\text{jumlah suara sah paslon 02 di suatu TPS}}{\text{total suara sah semua paslon di TPS tersebut}} \right) \times 100
\]

## Project Structure

Proyek ini terutama berpusat pada sebuah Jupyter Notebook (`handwriting_training.ipynb`), yang terdiri dari beberapa bagian:

1. **Dataset Preparation**: Instruksi untuk memformat anotasi dari [Label Studio](https://labelstud.io/) ke format yang kompatibel dengan MMOCR.
2. **Model Training**: Kode untuk melatih model pengenalan teks menggunakan kerangka kerja MMOCR.
3. **Google Colab Integration**: Notebook ini dirancang untuk dijalankan di Google Colab, memanfaatkan Google Drive untuk menyimpan dataset dan hasil pelatihan.

## Getting Started

### Prerequisites

- Lingkungan Google Colab (opsional, namun disarankan)
- Akun Google Drive untuk menyimpan dataset dan hasil pelatihan
- Python 3.x
- MMOCR terinstal (`pip install mmocr`)

### Installation

1. Clone repository ini:
   ```bash
   git clone https://github.com/Nbil-byte/Gammafest/tree/master
   cd Gammafest
   pip install -e .
   ```

2. Instal dependensi tambahan yang diperlukan oleh notebook, seperti:
   ```bash
   pip install label-studio
   ```

### Dataset Preparation

Pastikan anotasi dari Label Studio sudah diformat agar bisa dikonversi dan digunakan dalam MMOCR. Notebook ini menyertakan kode untuk konversi tersebut.

1. Unggah dataset ke Google Drive atau direktori lokal.
2. Sesuaikan jalur dataset dalam notebook agar sesuai dengan lokasi dataset Anda.

### Running the Notebook

1. Buka notebook `handwriting_training.ipynb` di Google Colab atau lingkungan Jupyter yang Anda pilih.
2. Mount Google Drive Anda dengan menjalankan sel berikut:
   ```python
   from google.colab import drive
   drive.mount('/content/drive')
   ```
3. Ikuti langkah-langkah dalam notebook untuk mengonfigurasi dataset dan memulai proses pelatihan model.

### Configuration

Untuk memodifikasi konfigurasi model, seperti arsitektur model atau hyperparameters pelatihan, lihat file konfigurasi yang disediakan oleh MMOCR. Anda dapat menentukan konfigurasi kustom dengan mengedit bagian yang relevan dalam notebook.

## Results

Setelah proses pelatihan selesai, model dan metrik evaluasi akan disimpan di direktori yang ditentukan di Google Drive (atau direktori lokal Anda). Anda kemudian dapat menggunakan model yang telah dilatih untuk melakukan inferensi pada data tulisan tangan baru.
