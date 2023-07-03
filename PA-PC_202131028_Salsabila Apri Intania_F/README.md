
# Background Removal
## Salsabila Apri Intania


Background Removal adalah praktik untuk memisahkan subjek dalam sebuah foto dari latar belakangnya dengan cara membersihkan area di sekitarnya. Prosedur ini menghasilkan gambar yang lebih jelas dan sederhana yang menyoroti subjeknya. Salah satu alasan utama penggunaan teknik ini adalah karena banyak pasar online seperti Amazon mensyaratkan agar para penjual menyediakan foto produk dengan latar belakang putih. Oleh karena itu, layanan Background Removal semakin umum digunakan dalam industri e-commerce, dan penggunaan gambar produk dengan latar belakang putih terang telah menjadi standar industri.

Jadi, secara dasarnya penghilangan latar belakang adalah proses menghapus objek-objek dan latar belakang yang tidak diperlukan dalam sebuah gambar untuk membuatnya lebih menarik dan jelas.


## Rincian Code Background Removal

1. Buat folder di PC, Kemudian start jupyter notebook
2. Buat File Python di Jupyter notebook
3. Pertama import modul yang dibutuhkan seperti pada code dibawah :

```bash
from IPython import display
from rembg import remove
from PIL import Image
import cv2
from skimage.io import imread
import matplotlib.pyplot as plt
%matplotlib inline

#202131028_Salsabila Apri
```
4. Buat validasi gambar inputan sesuai persyaratan Project Akhir
```bash
#Membaca File gambar inputan
citra1 = imread(fname='fotoGalon.jpeg')
citra1 = cv2.cvtColor(citra1, cv2.COLOR_RGB2BGR)
citra2  = imread(fname='rincianGalon.jpeg')
citra2  = cv2.cvtColor(citra2, cv2.COLOR_RGB2BGR)

#Membuat Tabel untuk menampilkan gambar
fig, axes = plt.subplots(1,2, figsize=(10,10))
ax = axes.ravel()

#Menampilkan Gambar inputan sesuai tabel 
ax[0].imshow(citra1)
ax[0].set_title("Gambar Asli")
ax[1].imshow(citra2)
ax[1].set_title("Rincian Gambar")
```
5. Buka Gambar input yang akan di proses
```bash
file_name = 'fotoGalon.jpeg'

#Open Gambar Inputan
img = Image.open(file_name)

#Rename Gambar Input dengan 'Gambar_Asli'
img_name = 'Gambar_Asli'

#Simpan Gambar Inputan Sesuai Folder yang sudah dibuat
img.save('Original/'+ img_name +'.png')
img
```
6. Tentukan Folder Tujuan Export dari proses penghilangan Background
```bash
#menentukan folder tujuan outputan
output_path = "Result/"+img_name+"_cropped.png"
output_path
```
7. Proses Background Removal
```bash
with open(output_path, 'wb') as f: #dengan membuka folder tujuan
    input_pict = open(file_name,'rb').read() #buka gambar inputan
    subject = remove(input_pict) #proses remove background dengan fitur remove dari modul rembg
    f.write(subject) #simpan hasil proses pada folder tujuan
```
8. Done
## Authors

- [@SalsabilaApri](https://github.com/salsabilaapri)

