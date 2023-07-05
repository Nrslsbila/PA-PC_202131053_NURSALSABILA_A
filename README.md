
# TEORI

Pada pengolahan citra, "remove background" merujuk pada proses menghapus latar belakang dari gambar atau citra digital, sehingga objek utama dalam gambar dapat dipisahkan dari latar belakangnya. Hal ini dapat berguna dalam berbagai konteks, seperti fotografi, desain grafis, pengenalan pola, dan kecerdasan buatan.

Untuk mencapai remove background, terdapat berbagai teori dan metode yang dapat digunakan. Menggabungkan beberapa pendekatan sering kali menghasilkan hasil yang lebih baik, tergantung pada kompleksitas citra, objek, dan latar belakangnya. Dalam beberapa kasus, teknik yang lebih canggih seperti deep learning dapat digunakan untuk mencapai segmentasi yang lebih akurat dan presisi yang lebih tinggi.

Dalam perkembangan teknologi, remove background semakin didukung oleh alat dan perangkat lunak yang lebih canggih. Ada banyak aplikasi dan perangkat lunak pengolahan citra yang secara otomatis menyediakan fitur remove background, menggunakan algoritma dan model pembelajaran mesin terkini untuk dengan cepat dan mudah memisahkan objek dari latar belakang.

Dengan demikian, remove background merupakan komponen penting dalam pengolahan citra. Hal ini memungkinkan pemisahan objek dari latar belakang dan memberikan fleksibilitas serta kemampuan kreatif yang lebih besar dalam berbagai konteks aplikasi pengolahan citra.


# Tahapan Pengerjaan Project
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

## Read and Show Image
Pada bagian ini, kita akan melakukan proses pembacaan gambar menggunakan fungsi cv.imread() dari OpenCV yang disimpan dalam vaiabel "image". Kemudian kita akan melakukan konversi gambar dari format BGR 


## Sumber

[ResearchGate - Pengolahan Citra Digital Menggunakan Python](https://www.researchgate.net/publication/358220979_Pengolahan_Citra_Digital_Menggunakan_Python)

[Medium - Effortlessly Remove Backgrounds in Python ](https://medium.com/@HeCanThink/rembg-effortlessly-remove-backgrounds-in-python-c2248501f992)

[KodingAkademi- Mengenal Library yang Sering Digunakan di Python](https://www.kodingakademi.id/matplotlib-mengenal-library-yang-sering-digunakan-di-python/)

[Medium - Background removal in images using OpenCV GrabCut algorithm+ ](https://medium.datadriveninvestor.com/background-removal-in-images-using-opencv-grabcut-algorithm-f2a35949417c)