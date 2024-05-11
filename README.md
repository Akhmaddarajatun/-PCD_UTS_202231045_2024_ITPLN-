
# Project UTS Pengolahan Citra Digital

# untuk membuat sebuah library
1.	import cv2: Mengimpor library OpenCV untuk pengolahan gambar.
2.	import numpy as np: Mengimpor library NumPy untuk operasi numerik.
3.	from matplotlib import pyplot as plt: Mengimpor modul pyplot dari library Matplotlib untuk menampilkan gambar.
# untuk memasukan file gambar
1. img = cv2.imread("tulis.jpg")yaitu untuk memasukan sebuah file gambar dengan nama file ”tulis.jpg”
# untuk menambahkan kecerahan gambar
1. cv2.cvtColor(image, cv2.COLOR_BGR2GRAY): untuk Mengubah citra warna (BGR) menjadi citra skala abu-abu (grayscale).
2. cv2.convertScaleAbs(image,alpha=alpha,beta=beta):Mengatur kontras dan kecerahan citra menggunakan formula baru:
- alpha: Faktor kontras (nilai di atas 1 meningkatkan kontras).
- beta: Penambahan kecerahan (nilai positif meningkatkan kecerahan, nilai negatif mengurangi kecerahan).  
3. plt.figure(figsize=(10, 5)):untuk Membuat figur matplotlib dengan ukuran 10x5 inch.
4. plt.subplot(1, 2, 1):untuk Membagi figur menjadi 1 baris dan 2 kolom, kemudian fokus pada subplot pertama.
5. plt.title('Original Image'):untuk Menambahkan judul pada subplot pertama.
6. plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) untuk Menampilkan citra asli yang sudah dikonversi ke skema warna RGB (dari BGR).
7. plt.axis('off'):untuk Menyembunyikan sumbu pada plot.
8. plt.subplot(1, 2, 2):untuk Memilih subplot kedua pada figur.
9. plt.title('Brightened Image'):untuk Menambahkan judul pada subplot kedua.
10. plt.imshow(cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)):untuk Menampilkan citra yang sudah disesuaikan kecerahan dan kontrasnya, dengan konversi warna dari BGR ke RGB.
11. plt.axis('off'):untuk Menyembunyikan sumbu pada plot.
12. plt.show():untuk Menampilkan hasil plot dalam jendela tampilan.
# untuk mengubah gambar ke RGB(Red,Green,Blue)
1. Baris pertama gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY) mengubah gambar ke skala abu-abu (grayscale).
2. Berikutnya, baris-baris selanjutnya menggunakan plt.subplot untuk mengatur layout gambar dalam grid 2x2 di matplotlib.
3. Pada plt.subplot(2, 2, 1), gambar asli ditampilkan dengan menggunakan plt.imshow(cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)) setelah dikonversi kembali ke warna RGB agar dapat ditampilkan dengan benar.
4. plt.subplot(2, 2, 2) menampilkan saluran merah (red channel) dari gambar dengan plt.imshow(cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)[:,:,0], cmap="gray").
5. plt.subplot(2, 2, 3) menampilkan saluran hijau (green channel) dari gambar dengan plt.imshow(cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)[:,:,1], cmap="gray").
6. plt.subplot(2, 2, 4) menampilkan saluran biru (blue channel) dari gambar dengan plt.imshow(cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)[:,:,2], cmap="gray").
7. Terakhir, plt.show() digunakan untuk menampilkan semua subplot yang telah dibuat.

# untuk menampilkan sebuah histogram warna merah
1. `cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)[:,:,0]`: Baris ini mengonversi citra `adjusted` dari format BGR (Blue-Green-Red) menjadi RGB (Red-Green-Blue), kemudian hanya mengambil saluran warna merah (red) dari citra tersebut. Hasilnya adalah citra dalam skala abu-abu (grayscale) yang hanya menunjukkan intensitas warna merah.

2. `fig, axs = plt.subplots(1,2, figsize=(15,5))`: Ini membuat sebuah figure (gambar) dengan dua subplot sejajar (1 baris, 2 kolom) menggunakan Matplotlib. Ukuran gambar adalah 15 x 5 inci.

3. `hist = cv2.calcHist([merah],[0],None,[256],[0,256])`: Baris ini menghitung histogram dari citra yang hanya berisi saluran warna merah (`merah`). Histogram adalah representasi distribusi intensitas piksel di dalam citra.

4. `axs[0].imshow(merah, cmap='gray')`: Ini menampilkan citra `merah` di subplot pertama dengan menggunakan skala warna abu-abu (gray). Citra ini hanya akan menunjukkan intensitas warna merah.

5. `axs[1].plot(hist)`: Ini membuat plot garis dari histogram yang sudah dihitung sebelumnya (`hist`) di subplot kedua. Plot ini akan menunjukkan distribusi intensitas piksel warna merah di citra.

6. `plt.show()`: Baris terakhir ini menampilkan gambar dan plot yang sudah dibuat.

# untuk menampilkan histogram hijau
1. `cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)[:,:,1]`: Kode ini mengubah citra yang disimpan dalam variabel `adjusted` dari mode warna BGR (Blue-Green-Red) ke mode RGB (Red-Green-Blue), dan kemudian memilih saluran warna hijau saja (indeks [1]). Hasilnya adalah citra dalam skala abu-abu yang menunjukkan saluran warna hijau dari citra tersebut.

2. `fig, axs = plt.subplots(1,2, figsize=(15,5))`: Kode ini membuat gambar (figure) dengan dua subplot yang akan menampung visualisasi citra dan histogram. Citra dan histogram akan ditampilkan secara berdampingan dalam satu baris (1) dan dua kolom (2), dengan ukuran gambar (figure) sebesar (15,5) dalam satuan inch.

3. `hist = cv2.calcHist([hijau],[0],None,[256],[0,256])`: Kode ini menghitung histogram dari citra dalam skala abu-abu (hijau) yang telah dipilih sebelumnya. Histogram digunakan untuk menunjukkan distribusi intensitas piksel di dalam citra. Parameter `[256]` menentukan jumlah bin histogram, yaitu 256 bin untuk rentang intensitas piksel dari 0 hingga 255.

4. `axs[0].imshow(hijau, cmap='gray')`: Kode ini menampilkan citra dalam subplot pertama (`axs[0]`) dengan menggunakan skala warna abu-abu (cmap='gray').

5. `axs[1].plot(hist)`: Kode ini menampilkan histogram (yang telah dihitung sebelumnya) dalam subplot kedua (`axs[1]`) dengan menggunakan plot garis.

6. `plt.show()`: Kode ini menampilkan seluruh gambar (figure) beserta subplot-subplotnya.

# untuk menampilkan histogram biru
1. `cv2.cvtColor(adjusted, cv2.COLOR_BGR2RGB)[:,:,2]`: Kode ini mengubah warna gambar yang disimpan dalam variabel `adjusted` dari format BGR (Blue-Green-Red) menjadi RGB (Red-Green-Blue), dan kemudian hanya mengambil saluran warna biru (indeks ke-2). Hasilnya adalah gambar dalam skala abu-abu yang mewakili saluran biru dari gambar asli.

2. `cv2.calcHist([biru],[0],None,[256],[0,256])`: Fungsi ini digunakan untuk menghitung histogram dari saluran warna biru yang telah diambil dari gambar. Parameter `[biru]` menunjukkan array gambar input, `[0]` mengindikasikan saluran yang ingin dihitung histogramnya (dalam hal ini, saluran tunggal dari gambar skala abu-abu), `None` menunjukkan bahwa kita tidak menggunakan maska, `[256]` menunjukkan jumlah bin histogram, dan `[0,256]` menunjukkan rentang nilai piksel.

3. `fig, axs = plt.subplots(1,2, figsize = (15,5))`: Ini membuat sebuah gambar subplot dengan 1 baris dan 2 kolom. Ukuran gambar subplot adalah 15x5.

4. `axs[0].imshow(biru, cmap='gray')`: Ini menampilkan gambar skala abu-abu yang merupakan saluran biru dari gambar di subplot pertama (`axs[0]`). Pengaturan `cmap='gray'` digunakan untuk menampilkan gambar dalam skala abu-abu.

5. `axs[1].plot(hist)`: Ini memplot histogram yang dihitung sebelumnya di subplot kedua (`axs[1]`). Histogram ini menunjukkan distribusi intensitas warna (biru) di seluruh gambar.

6. `plt.show()`: Ini digunakan untuk menampilkan gambar subplot beserta histogram yang dihasilkan.

# untuk menampilkan ambang batas

1. Import Libraries:
- Memuat pustaka yang diperlukan: OpenCV (`cv2`), NumPy (`np`), dan matplotlib (`plt`).

2. Baca Gambar:
- Menggunakan OpenCV (`cv2.imread`) untuk membaca gambar dari file "tulis.jpg" dan menyimpannya dalam variabel `img`.

3. Konversi ke Grayscale:
- Mengonversi gambar ke citra skala abu-abu menggunakan `cv2.cvtColor` dengan parameter `cv2.COLOR_RGB2GRAY`.

4. Inisialisasi Plot:
- Membuat subplot `2x2` menggunakan `plt.subplots`, yang akan menampung empat citra.

5. Citra Biner (NONE):
- Menerapkan thresholding ke citra abu-abu (`gray`) tanpa menggunakan batas ambang (None) dengan `cv2.THRESH_BINARY`.

6. Konversi ke HSV:
- Mengonversi gambar asli ke ruang warna HSV (`cv2.COLOR_BGR2HSV`).

7. Mask Warna Biru:
- Mendefinisikan range warna biru dalam format HSV (`blue_lower` dan `blue_upper`).
- Menerapkan operasi `cv2.inRange` untuk membuat mask dari warna biru dalam gambar.

8. Citra Biner (RED-BLUE):
- Menggunakan thresholding pada citra abu-abu untuk mendapatkan citra biner dengan batas ambang 43.

9. Citra Biner (RED-GREEN-BLUE):
- Menggunakan thresholding pada citra abu-abu untuk mendapatkan citra biner dengan batas ambang 80.

10. Menampilkan Hasil:
- Menampilkan keempat citra (hasil dari thresholding dan segmentasi) dalam subplot menggunakan `plt.imshow` dan `plt.show`.
