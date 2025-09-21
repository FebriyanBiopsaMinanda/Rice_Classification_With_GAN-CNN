🌾 Rice Image Classification using CNN & GAN  

📌 Deskripsi  
Project ini bertujuan untuk melakukan klasifikasi varietas beras berdasarkan citra digital menggunakan **Convolutional Neural Network (CNN)** yang dipadukan dengan **data sintetis dari Generative Adversarial Network (GAN)**.  
Varietas beras yang diklasifikasikan mencakup:  
- Arborio  
- Basmati  
- Ipsala  
- Jasmine  
- Karacadag  

Dengan pendekatan ini, model dapat belajar lebih baik dari data terbatas melalui augmentasi sintetis, serta meningkatkan akurasi dalam mengenali setiap jenis beras.  

📂 Dataset  
📑 **Sumber Data**  
Dataset diperoleh dari Kaggle:  
🔗 [Rice Image Dataset – Kaggle](https://www.kaggle.com/datasets/muratkokludataset/rice-image-dataset/code)  

📊 **Keterangan Data**  
Dataset terdiri dari 5 varietas beras dengan total **75.000 citra grayscale** (masing-masing 15.000 gambar per kelas).  

| Kelas       | Jumlah Data | Deskripsi                                                                 |
|-------------|-------------|---------------------------------------------------------------------------|
| Arborio     | 15.000      | Varietas beras populer dari Italia, banyak digunakan untuk risotto.       |
| Basmati     | 15.000      | Beras aromatik panjang, banyak dikonsumsi di Asia Selatan.               |
| Ipsala      | 15.000      | Beras khas dari wilayah Turki.                                           |
| Jasmine     | 15.000      | Beras aromatik asal Thailand, bertekstur lembut dan harum.               |
| Karacadag   | 15.000      | Varietas beras tradisional yang berasal dari Turki.                      |  

🧹 Tahapan Analisis  
1. **Import Libraries 📚**  
   Mengimpor library utama seperti TensorFlow, Keras, OpenCV, NumPy, Matplotlib, dan Scikit-learn.  

2. **Load Dataset 📂**  
   Membaca dataset citra, mendefinisikan kelas, dan menyiapkan data untuk proses lebih lanjut.  

3. **Data Preprocessing 🧹**  
   - Konversi gambar ke grayscale  
   - Resize gambar ke ukuran 100x100  
   - Gaussian blur & histogram equalization  
   - Normalisasi dan one-hot encoding label  
   - Split data menjadi train & test set  

4. **Generator GAN 🤖**  
   Melatih GAN untuk setiap kelas beras (Arborio, Basmati, Ipsala, Jasmine, Karacadag) sehingga dapat menghasilkan data sintetis untuk augmentasi.  

5. **Data Augmentation 🔄**  
   Menggabungkan data asli dengan data sintetis hasil GAN untuk memperbesar jumlah data train.  

6. **Arsitektur CNN 🧩**  
   - Layer konvolusi (Conv2D) dengan ReLU  
   - MaxPooling untuk ekstraksi fitur  
   - Dropout untuk mencegah overfitting  
   - Dense layer dengan softmax untuk klasifikasi 5 kelas  

7. **Training Model 🏋️‍♂️**  
   Melatih CNN dengan data train (gabungan asli + sintetis) menggunakan optimizer Adam dan loss categorical crossentropy.  

8. **Evaluasi Model 📈**  
   - Classification Report (precision, recall, f1-score per kelas)  
   - Confusion Matrix untuk visualisasi prediksi model  

📈 Hasil  
Hasil evaluasi model dengan data uji menunjukkan performa yang sangat tinggi:  

- **Akurasi keseluruhan: 97%**  
- Hampir semua kelas beras memiliki nilai precision, recall, dan f1-score > 0.95  
- Basmati, Ipsala, dan Jasmine mendapatkan f1-score **0.99**  
- Arborio dan Karacadag tetap memiliki performa tinggi dengan f1-score **0.95**  

✨ Secara keseluruhan, kombinasi preprocessing, augmentasi data sintetis melalui GAN, dan CNN terbukti efektif dalam klasifikasi citra beras. Model ini berpotensi untuk digunakan dalam sistem klasifikasi berbasis citra di dunia nyata.  
