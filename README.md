PANDUAN DOKUMENTASI KODE SKRIPSI KE GITHUB
Topik: Klasifikasi Cyberbullying dan Regulasi Hukum Indonesia pada Interaksi Penggemar Idol K-Pop Menggunakan CNN

Tujuan
Panduan ini membantu memindahkan notebook Google Colab ke GitHub agar kode penelitian terdokumentasi dan mudah ditunjukkan dalam skripsi. Dataset berada di Google Drive, jadi notebook dapat disimpan di GitHub tanpa harus mengunggah seluruh dataset.

A. PERSIAPAN
1. Pastikan semua notebook Colab penelitian sudah tersimpan.
2. Buka Google Colab dan periksa nama notebook. Jika perlu, gunakan nama yang jelas, misalnya:
   - 01_preprocessing.ipynb
   - 02_pelabelan_inset_lexicon.ipynb
   - 03_dictionary_based_classification.ipynb
   - 04_pelatihan_cnn.ipynb
   - 05_evaluasi_model.ipynb
   - 06_prediksi_teks.ipynb
   Nama tersebut hanya contoh. Sesuaikan dengan pembagian kode yang benar-benar ada di Colab. Jika semua tahapan ada dalam satu notebook, tidak perlu memecahnya hanya demi GitHub.
3. Pastikan notebook tidak menampilkan token, kata sandi, API key, atau informasi pribadi.
4. Jangan mengunggah dataset mentah, data pribadi, atau file model berukuran besar tanpa memeriksa izin dan kebutuhan. Untuk dokumentasi skripsi, kode dan petunjuk lokasi dataset biasanya cukup.

B. UNDUH NOTEBOOK DARI GOOGLE COLAB
Lakukan untuk setiap notebook yang ingin didokumentasikan.
1. Buka notebook di Google Colab.
2. Klik menu File.
3. Pilih Download (Unduh).
4. Pilih Download .ipynb.
5. Simpan file di komputer, misalnya dalam folder sementara bernama dokumentasi_kode_skripsi.
6. Ulangi untuk notebook lain yang memang digunakan dalam penelitian.
Catatan: file .ipynb menyimpan kode, teks penjelasan, dan output yang masih tersimpan di notebook. Sebelum membagikannya, bersihkan output yang memuat informasi sensitif atau data yang tidak boleh dipublikasikan.

C. BUAT REPOSITORY DI GITHUB
1. Buka https://github.com dan masuk ke akun.
2. Klik tombol + di bagian kanan atas, lalu pilih New repository.
3. Isi Repository name, misalnya: klasifikasi-cyberbullying-cnn
4. Isi Description, misalnya: Dokumentasi kode penelitian klasifikasi cyberbullying pada interaksi penggemar K-Pop menggunakan InSet Lexicon, Dictionary-Based Classification, dan CNN.
5. Pilih Public jika kode memang boleh dilihat umum, atau Private jika hanya ingin menyimpan secara terbatas. Ikuti arahan dosen jika repository harus dapat diakses untuk pemeriksaan.
6. Centang Add a README file agar repository langsung memiliki halaman penjelasan.
7. Klik Create repository.

D. UNGGAH NOTEBOOK KE REPOSITORY
Cara termudah adalah lewat situs GitHub, tanpa memasang software tambahan.
1. Buka repository yang baru dibuat.
2. Klik Add file, lalu pilih Upload files.
3. Seret file .ipynb yang sudah diunduh dari Colab ke area upload, atau klik choose your files untuk memilihnya.
4. Untuk susunan paling sederhana, unggah notebook langsung ke halaman utama repository. Jika ingin memakai folder notebooks, buat folder dengan Add file > Create new file, lalu beri nama notebooks/README.md dan simpan. Setelah itu buka folder notebooks dan unggah notebook ke sana.
5. Di bagian Commit changes, isi pesan seperti: Menambahkan notebook preprocessing dan pelabelan sentimen.
6. Klik Commit changes.
7. Ulangi untuk notebook lain.
8. Buka file notebook di GitHub untuk memastikan file berhasil diunggah dan dapat ditampilkan.

E. BAGAIMANA DENGAN DATASET DI GOOGLE DRIVE?
Pilihan yang disarankan untuk dokumentasi kode:
- Jangan unggah dataset ke GitHub jika tidak diperlukan atau belum dipastikan boleh dipublikasikan.
- Simpan dataset tetap di Google Drive.
- Tambahkan petunjuk pada README bahwa notebook memerlukan dataset yang disimpan di Google Drive.
- Pastikan akses Drive dibatasi sesuai kebutuhan dan izin pemilik data.
Jika dataset memang boleh dibagikan, pertimbangkan membagikan tautan Google Drive dengan akses yang sesuai atau mengunggah sampel kecil yang sudah aman. Jangan mengubah akses menjadi “siapa saja yang memiliki link” tanpa memastikan dataset memang boleh dipublikasikan.
Catatan: tautan Google Drive pribadi tidak otomatis dapat diakses orang lain. Pengguna yang menjalankan notebook perlu memiliki izin akses ke dataset.

F. PASTIKAN NOTEBOOK BISA DIJALANKAN KEMBALI
Jika notebook menghubungkan Google Drive, biasanya ada kode seperti:
    from google.colab import drive
    drive.mount('/content/drive')
Sesudah dijalankan, notebook meminta otorisasi akun Google. Path dataset harus disesuaikan dengan lokasi folder di Drive milik pengguna yang menjalankan notebook.
Contoh:
    import pandas as pd
    data_path = '/content/drive/MyDrive/folder_dataset/nama_file.csv'
    df = pd.read_csv(data_path)
Ganti folder_dataset dan nama_file.csv sesuai lokasi serta nama file yang benar. Jangan menyalin contoh ini jika path aslinya berbeda.

Jika notebook membutuhkan library tambahan, buat file requirements.txt. Isi dengan library yang benar-benar digunakan dan versi yang sesuai dengan lingkungan penelitian. Contoh awal berikut hanya contoh dan harus disesuaikan:
    pandas
    numpy
    scikit-learn
    tensorflow
    nltk
    Sastrawi
    matplotlib
    seaborn
Jangan memasukkan library yang tidak digunakan. Jika versi library penting untuk mereproduksi hasil, catat versi yang digunakan di Colab.

G. BUAT README.md
README adalah halaman pertama yang dilihat orang ketika membuka repository. Di GitHub, buka README.md lalu klik ikon pensil untuk mengedit. Contoh isi:

# Klasifikasi Cyberbullying Menggunakan CNN

Repository ini berisi notebook kode penelitian berjudul “Klasifikasi Cyberbullying dan Regulasi Hukum Indonesia pada Interaksi Penggemar Idol K-Pop Menggunakan Convolutional Neural Network”.

## Tahapan Penelitian
1. Preprocessing teks.
2. Pelabelan sentimen menggunakan InSet Lexicon.
3. Penyaringan data sentimen negatif menggunakan Dictionary-Based Classification.
4. Pelatihan model CNN untuk tiga kategori: hate speech, flaming and harassment, dan denigration.
5. Evaluasi model menggunakan metrik klasifikasi.
6. Prediksi teks dan pemetaan hasil klasifikasi ke referensi regulasi hukum Indonesia.

## Dataset
Dataset disimpan di Google Drive dan tidak disertakan di repository ini. Untuk menjalankan notebook, pengguna harus memiliki akses ke dataset dan menyesuaikan path file pada notebook.

## Cara Menjalankan
1. Buka notebook yang dibutuhkan di GitHub.
2. Unduh notebook atau buka melalui Google Colab.
3. Pastikan akses Google Drive tersedia.
4. Sesuaikan path dataset.
5. Jalankan sel notebook secara berurutan dari atas ke bawah.

## Catatan
Hasil prediksi dan pemetaan hukum merupakan keluaran penelitian untuk tujuan akademik dan edukasi, bukan pengganti penilaian ahli atau nasihat hukum.

Setelah selesai, klik Commit changes untuk menyimpan perubahan README.

H. CEK AKHIR SEBELUM LINK GITHUB DIBERIKAN
- Repository memiliki nama dan deskripsi yang jelas.
- Notebook yang diunggah adalah versi final yang sesuai dengan skripsi.
- Notebook tidak berisi password, token, atau informasi pribadi.
- Path Google Drive dijelaskan dan tidak diasumsikan berlaku untuk semua orang.
- Dataset tidak dipublikasikan tanpa izin.
- README menjelaskan urutan notebook dan cara menjalankannya.
- Tautan repository dapat dibuka oleh dosen sesuai pengaturan Public/Private.
- Salin URL repository dari address bar browser untuk dicantumkan di dokumen skripsi atau dikirim ke dosen.

CONTOH SUSUNAN REPOSITORY
klasifikasi-cyberbullying-cnn/
├── README.md
├── requirements.txt
└── notebooks/
    ├── 01_preprocessing.ipynb
    ├── 02_pelabelan_inset_lexicon.ipynb
    ├── 03_dictionary_based_classification.ipynb
    ├── 04_pelatihan_cnn.ipynb
    ├── 05_evaluasi_model.ipynb
    └── 06_prediksi_teks.ipynb

Susunan di atas hanya contoh. Gunakan hanya file dan tahapan yang memang ada dalam penelitian. Jika seluruh kode ada dalam satu notebook, repository cukup berisi README.md dan satu notebook utama.
