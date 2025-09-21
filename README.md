# 🌾 Rice Image Classification using CNN & GAN

## 📌 Deskripsi
Project ini bertujuan untuk melakukan **klasifikasi varietas beras** berdasarkan citra digital. Model dibangun menggunakan **Convolutional Neural Network (CNN)** yang dipadukan dengan **data sintetis dari Generative Adversarial Network (GAN)** untuk meningkatkan performa klasifikasi.  
Varietas beras yang diprediksi mencakup lima kelas utama:
- Arborio  
- Basmati  
- Ipsala  
- Jasmine  
- Karacadag  

Dengan memanfaatkan CNN dan augmentasi data dari GAN, project ini berfokus pada peningkatan akurasi model dalam mengenali varietas beras meskipun jumlah data terbatas.

---

## 📂 Dataset
### 📑 Sumber Data  
Dataset diperoleh dari **Kaggle**:  
🔗 [Rice Image Dataset – Kaggle](https://www.kaggle.com/datasets/muratkokludataset/rice-image-dataset/code)  

### 📊 Keterangan Data  
Dataset terdiri dari 75.000 citra grayscale (masing-masing kelas memiliki 15.000 citra).  

| Kelas      | Jumlah Data | Deskripsi                                                                 |
|------------|-------------|---------------------------------------------------------------------------|
| Arborio    | 15.000      | Varietas beras dari Italia, sering digunakan untuk risotto.               |
| Basmati    | 15.000      | Beras panjang aromatik dari Asia Selatan.                                |
| Ipsala     | 15.000      | Varietas khas dari wilayah Turki.                                        |
| Jasmine    | 15.000      | Beras harum asal Thailand dengan tekstur lembut.                         |
| Karacadag  | 15.000      | Varietas beras tradisional yang berasal dari Turki.                      |

---

## 🧹 Tahapan Analisis
1. **Import Libraries** 📚  
   Mengimpor library utama seperti TensorFlow/Keras, OpenCV, NumPy, Matplotlib, dan Scikit-learn.  

2. **Load Dataset** 📂  
   Membaca dataset citra, mendefinisikan label kelas, dan menyiapkan data untuk proses selanjutnya.  

3. **Data Preprocessing** 🧹  
   - Konversi gambar ke grayscale  
   - Resize ke ukuran 100x100  
   - Gaussian blur & histogram equalization  
   - Normalisasi nilai pixel  
   - One-hot encoding pada label  
   - Split data menjadi train dan test set  

4. **Generator GAN** 🤖  
   Melatih GAN untuk setiap kelas beras (Arborio, Basmati, Ipsala, Jasmine, Karacadag) untuk menghasilkan citra sintetis.  

5. **Data Augmentation** 🔄  
   Menggabungkan data asli dengan data sintetis hasil GAN untuk memperbesar jumlah data train.  

6. **Arsitektur CNN** 🧩  
   - Layer konvolusi (Conv2D) dengan ReLU  
   - MaxPooling untuk ekstraksi fitur  
   - Dropout untuk mencegah overfitting  
   - Dense layer dengan softmax untuk klasifikasi 5 kelas  

7. **Training Model** 🏋️‍♂️  
   Melatih CNN dengan data train (gabungan asli + sintetis) menggunakan optimizer Adam dan loss categorical crossentropy.  

8. **Evaluasi Model** 📈  
   - Classification Report (precision, recall, f1-score per kelas)  
   - Confusion Matrix untuk visualisasi prediksi model  

---

## 📈 Hasil
Hasil evaluasi model dengan data uji (1.500 citra) menunjukkan performa sangat baik:  
- **Akurasi keseluruhan: 97%**  
- Hampir semua kelas beras memiliki nilai precision, recall, dan f1-score > 0.95  
- **Basmati, Ipsala, dan Jasmine** mencapai f1-score **0.99**  
- **Arborio dan Karacadag** memiliki f1-score **0.95**  

✨ Secara keseluruhan, model terbukti efektif dalam mengklasifikasikan varietas beras, dan berpotensi untuk digunakan dalam sistem berbasis citra di dunia nyata.  
