
NO 4

    Teori yang mendukung mengenai project terkait

1. Konversi Warna:
    Digunakan fungsi cv2.cvtColor() untuk mengubah mode warna gambar dari BGR (Blue-Green-Red) ke HSV (Hue-Saturation-Value). Konversi ini memudahkan dalam mendefinisikan rentang warna yang akan di-segmentasi.

2. Segmentasi Warna:
    Setelah konversi warna ke mode HSV, digunakan fungsi cv2.inRange() untuk membuat mask atau membatasi rentang warna yang diinginkan. Setiap objek yang memiliki warna dalam rentang yang ditentukan akan diberi nilai 255 pada mask dan sisanya menjadi 0.
    Dalam contoh ini, dilakukan segmentasi untuk warna jeruk, apel, dan pisang dengan menentukan rentang warna yang dianggap mewakili setiap buah.

3. Penerapan Mask:
    Fungsi cv2.bitwise_and() digunakan untuk menerapkan mask pada gambar asli. Ini menghasilkan citra hasil segmentasi yang hanya menampilkan bagian yang memiliki nilai non-nol pada mask.

4. Pemrosesan Morfologi:
    Digunakan fungsi cv2.morphologyEx() dengan parameter cv2.MORPH_OPEN untuk melakukan operasi morfologi "opening" pada mask. Operasi ini melibatkan pengaburan dan dilasi untuk mengurangi noise dan menghaluskan bentuk objek.
    Struktur elemen yang digunakan adalah cv2.getStructuringElement(cv2.MORPH_ELLIPSE, (5, 5)), yang merupakan kernel elips dengan ukuran 5x5.

5. Deteksi Kontur:
    Digunakan fungsi cv2.findContours() untuk mendeteksi kontur objek pada mask yang telah diproses. Hasilnya adalah daftar kontur dan hierarki mereka.
    Parameter cv2.RETR_EXTERNAL digunakan untuk mendapatkan hanya kontur eksternal terluar.
    Parameter cv2.CHAIN_APPROX_SIMPLE digunakan untuk menyimpan hanya titik-titik sudut yang diperlukan untuk menggambarkan kontur.

6. Visualisasi Hasil:
    Menggunakan matplotlib untuk membuat subplot gambar hasil.
    Menggunakan cv2.cvtColor() untuk mengubah mode warna dari BGR ke RGB sebelum menampilkan gambar.
    Menggunakan imshow() untuk menampilkan gambar pada setiap subplot.
    Menggunakan set_title() untuk memberikan judul pada setiap subplot.
    Menggunakan axis('off') untuk menghilangkan sumbu koordinat pada setiap subplot.
    Menggunakan tight_layout() untuk menampilkan tata letak gambar yang rapi.
    Terakhir, plt.show() digunakan untuk menampilkan semua subplot gambar.

    Menjelaskan tahapan cara menyelesaikan project secara rinci

1. Mengimpor library: Import library yang diperlukan yaitu cv2 (OpenCV untuk pemrosesan citra), numpy (untuk manipulasi array), dan matplotlib.pyplot (untuk visualisasi gambar).

2. Membaca gambar: Menggunakan fungsi cv2.imread() untuk membaca gambar 'fruit.jpg' dan menyimpannya dalam variabel img.

3. Konversi warna: Menggunakan fungsi cv2.cvtColor() untuk mengubah mode warna gambar dari BGR ke HSV. Hasil konversi disimpan dalam variabel hsv_img.

4. Menentukan rentang warna: Menginisialisasi nilai-nilai ambang bawah dan atas untuk tiga jenis warna (jeruk, apel, dan pisang) dalam format HSV. Rentang warna ini digunakan untuk membuat mask dan membatasi objek yang akan ditemukan.

5. Segmentasi warna: Menggunakan fungsi cv2.inRange() untuk membuat mask berdasarkan rentang warna yang telah ditentukan. Masing-masing mask digunakan untuk segmentasi jeruk, apel, dan pisang.

6. Penerapan mask: Menggunakan fungsi cv2.bitwise_and() untuk menerapkan mask pada gambar asli. Ini menghasilkan citra hasil segmentasi yang hanya menampilkan bagian yang memiliki nilai non-nol pada mask. Hasil segmentasi jeruk, apel, dan pisang disimpan dalam variabel result_orange, result_red, dan result_yellow.

7. Pemrosesan morfologi: Membentuk kernel dengan menggunakan cv2.getStructuringElement() untuk operasi morfologi. Kemudian, melakukan operasi morfologi "opening" pada masing-masing mask menggunakan fungsi cv2.morphologyEx(). Operasi ini dilakukan untuk mengurangi noise dan menghaluskan bentuk objek. Hasil mask setelah pemrosesan morfologi disimpan dalam variabel cleaned_mask_orange, cleaned_mask_red, dan cleaned_mask_yellow.

8. Deteksi kontur: Menggunakan fungsi cv2.findContours() untuk mendeteksi kontur pada mask setelah pemrosesan morfologi. Hasilnya adalah daftar kontur dan hierarki mereka. Kontur jeruk, apel, dan pisang disimpan dalam variabel contours_orange, contours_red, dan contours_yellow.

9. Visualisasi hasil: Membuat subplot gambar menggunakan plt.subplots() dengan ukuran 2x2. Kemudian, menggunakan imshow() untuk menampilkan gambar pada setiap subplot dengan menggunakan cv2.cvtColor() untuk mengubah mode warna dari BGR ke RGB sebelum menampilkan gambar. Menambahkan judul pada setiap subplot menggunakan set_title() dan menghilangkan sumbu koordinat menggunakan axis('off'). Terakhir, menggunakan tight_layout() untuk menampilkan tata letak gambar yang rapi. Seluruh subplot gambar ditampilkan menggunakan plt.show().


