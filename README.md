
# TEORI

Pada pengolahan citra, "remove background" merujuk pada proses menghapus latar belakang dari gambar atau citra digital, sehingga objek utama dalam gambar dapat dipisahkan dari latar belakangnya. Hal ini dapat berguna dalam berbagai konteks, seperti fotografi, desain grafis, pengenalan pola, dan kecerdasan buatan.

Untuk mencapai remove background, terdapat berbagai teori dan metode yang dapat digunakan. Menggabungkan beberapa pendekatan sering kali menghasilkan hasil yang lebih baik, tergantung pada kompleksitas citra, objek, dan latar belakangnya. Dalam beberapa kasus, teknik yang lebih canggih seperti deep learning dapat digunakan untuk mencapai segmentasi yang lebih akurat dan presisi yang lebih tinggi.

Dalam perkembangan teknologi, remove background semakin didukung oleh alat dan perangkat lunak yang lebih canggih. Ada banyak aplikasi dan perangkat lunak pengolahan citra yang secara otomatis menyediakan fitur remove background, menggunakan algoritma dan model pembelajaran mesin terkini untuk dengan cepat dan mudah memisahkan objek dari latar belakang.

Dengan demikian, remove background merupakan komponen penting dalam pengolahan citra. Hal ini memungkinkan pemisahan objek dari latar belakang dan memberikan fleksibilitas serta kemampuan kreatif yang lebih besar dalam berbagai konteks aplikasi pengolahan citra.


# Tahapan Pengerjaan Project, Penjelasan, & Teori Tambahan
- Import Library
- Read and Show Image
- Convert Image to Binary with Thresholding Method
- Contour from Binary
- Mask
- Contour Image on Mask
- Merge the Original Images with Masks Using the Bitwise AND Operator
- Remove Background
- Save Image

## Library yang Digunakan
Pada tahapan ini, kita akan melakukan import library yang mendukung proses kita dalam mengolah citra.
### OpenCV
OpenCV adalah perpustakaan(Library) open-source yang dikembangkan oleh Intel pada tahun 2000. Hal ini sebagianbesar digunakan dalam tugas-tugas computer visi seperti deteksi objek, deteksi wajah, pengenalan wajah, segmentasi gambar, dll tetapi juga berisi banyak fungsi berguna yang mungkin perlu dalam Pengolahan citra digital. OpenCV dapat digunakan untuk melakukan berbagai operasi terhadap citra dan video dengan berbagai algoritma terbaru serta banyak digunakan pada berbagai sistem pengolahan citra yang populer.
untuk melakukan instalasi = pip install opencv-python

### NumPy
Gambar pada dasarnya adalah array nilai piksel di mana setiap piksel diwakili oleh nilai 1 (skala abu-abu) atau 3 (RGB). Oleh karena itu, NumPy dapat dengan mudah melakukan tugas seperti pemotongan gambar, penyembunyian, atau manipulasi nilai piksel.
untuk melakukan instalasi = pip install numpy

### Pillow/PIL
PIL (Python Imaging Library) adalah open-source library untuk tugas pemrosesan gambar yang membutuhkan bahasa pemrograman python. PIL dapat melakukan tugas pada gambar seperti membaca, mengubah skala, menyimpan dalam format gambar yang berbeda.
untuk melakukan instalasi = pip install Pillow

### rembg
Modul rembg di Python adalah pustaka yang digunakan untuk menghapus latar belakang dari gambar. Ini didasarkan pada algoritma Rembg, yang menggunakan jaringan saraf untuk melakukan tugas penghapusan latar belakang. Algoritma dilatih untuk mengidentifikasi dan memisahkan objek latar depan dari latar belakangnya dalam gambar, sehingga menghasilkan gambar dengan latar belakang transparan.
untuk melakukan instalasi = pip install rembg

### Matplotlib
Matplotlib adalah sebuah open source library yang memiliki kemampuan untuk mendukung berbagai jenis gambar. Library ini digunakan untuk membuat berbagai jenis visualisasi data seperti plot, histogram, bar chart, dan jenis-jenis grafik lainnya. Selain itu, ini juga sering digunakan dalam konteks server aplikasi web, shell, dan skrip python untuk mempermudah visualisasi data.
untuk melakukan instalasi = pip install matplotlib

### Read and Show Image
Pada bagian ini, kita akan melakukan proses pembacaan gambar menggunakan fungsi cv.imread() dari OpenCV yang disimpan dalam vaiabel "image". Kemudian kita akan melakukan konversi gambar dari format BGR menjadi RGB menggunakan fungsi "cv.cvtColor()" yang disimpan dalam variabel "rgb". Setelah itu kita akan menampilkan objek yang telah kita input menggunakan fungsi 'plt.imshow()' dari matplotlib dan menggunakan fungsi 'plt.title()' untuk memberikan judul pada gambar. 

### Convert Image to Binary with Thresholding Method
Untuk menghapus latar belakang, citra asli tadi perlu kita ubah ke skala abu-abu terlebih dahulu menggunakan cv.cvtColor() dengan konversi dari BGR ke grayscale. Selanjutnya, digunakan teknik thresholding dengan metode Otsu (cv.THRESH_OTSU) untuk menghasilkan gambar biner (thresh). Dalam gambar biner, latar belakang akan menjadi hitam dan objek utama akan menjadi putih.

### Contour from Binary
Setelah mendapatkan gambar biner, kita akan melakukan pencarian kontur menggunakan cv.findContours() dari OpenCV untuk mengidentifikasi tepi objek pada gambar. Kontur adalah garis kurva yang menghubungkan piksel-piksel yang memiliki intensitas atau warna yang serupa. Dalam konteks penghapusan latar belakang, kontur digunakan untuk menentukan batas objek utama yang ingin dipertahankan, sementara latar belakang dihapus.

### Mask
Pada bagian ini, maska hitam dibuat dengan ukuran yang sama seperti gambar asli menggunakan np.zeros() untuk mengisolasi objek yang ingin dipertahankan, yaitu objek tanpa latar belakang.

### Contour Image on Mask
Setelah itu, kontur gambar digunakan untuk menggambar batas objek pada maska dengan warna putih (255) menggunakan fungsi cv.drawContours().

### Merge the Original Images with Masks Using the Bitwise AND Operator
Pada langkah ini, kita menggunakan maska untuk memisahkan objek pada gambar asli menggunakan operasi bitwise AND. Hasilnya disimpan dalam variabel `rmv` yang merupakan gambar tanpa latar belakang. Operasi bitwise AND bekerja pada setiap piksel gambar asli dan maska. Piksel maska putih (nilai 255) akan mempertahankan piksel gambar asli, sementara piksel maska hitam (nilai 0) akan menghapus piksel gambar asli. Dengan demikian, gambar yang dihasilkan akan mempertahankan objek yang ditandai oleh maska dan menghapus latar belakangnya. Pada bagian ini, sebenarnya kita sudah berhasil melakukan penghapusan latar belakang pada gambar. Hanya saja, karena saya ingin mendapatkan hasil yang lebih baik maka kita akan melangkah ke step selanjutnya.

### Remove Background
Pada step ini, kita akan melakukan penghapusan latar belakang menggunakan library 'rembg' yang disimpan dalam variabel output kemudian kita akan menampilkan hasilnya menggunakan 'plt.imshow' dan memberikan judul menggunakan plt.title.

### Show Original and Output Image
Pada bagian ini, kita akan menampilkan gambar asli dan hasil dari citra yang telah kita proses.

### Save Image
Terakhir, setelah semua proses dilakukan kita akan melakukan penyimpanan gambar menggunakan cv.imwrite() dan disimpan dalam file output.png dengan format png


# Sumber
## Jurnal
[ResearchGate - Autonomous image background removal for accurate and efficient close-range photogrammetry](https://www.researchgate.net/publication/365500074_Autonomous_image_background_removal_for_accurate_and_efficient_close-range_photogrammetry)

[CoreIT - Deteksi Obyek Manusia Pada Basis Data Video Menggunakan Metode Background Subtraction Dan Operasi Morfologi](https://ejournal.uin-suska.ac.id/index.php/coreit/article/view/2391/pdf)

## Referensi Program
[ResearchGate - Pengolahan Citra Digital Menggunakan Python](https://www.researchgate.net/publication/358220979_Pengolahan_Citra_Digital_Menggunakan_Python)

[Medium - Effortlessly Remove Backgrounds in Python ](https://medium.com/@HeCanThink/rembg-effortlessly-remove-backgrounds-in-python-c2248501f992)

[KodingAkademi- Mengenal Library yang Sering Digunakan di Python](https://www.kodingakademi.id/matplotlib-mengenal-library-yang-sering-digunakan-di-python/)

[Medium - Background removal in images using OpenCV GrabCut algorithm+ ](https://medium.datadriveninvestor.com/background-removal-in-images-using-opencv-grabcut-algorithm-f2a35949417c)
