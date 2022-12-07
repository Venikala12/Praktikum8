 # Praktikum 8 
## Tugas Praktikum
#### Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:
- Method **tambah()** untuk menambahkan data
- Method **tampilkan()** untuk menampilkan data
- Method **hapus(nama)** untuk menghapus data bedasarkan nama
- Method **ubah(nama)** untuk mengubah data bedasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md
- Commit dan push repository ke Github
###### ^^ Terima Kasih ^^
### Daftar Nilai Mahasiswa menggunakan *class*
- Pertama, kita membuat class induk terlebih dahulu
```
class Data():
    def __init__(self,nama,nim,uts,uas,tugas,total):
```
- Kemudian kita masukan fungsi **tambah()** pada induk class
###### Fungsi untuk Menambahkan Data
```
print("Tambah Data")
    def tambah(self):
        self.nama = input("Nama           : ")
        self.nim = int(input("NIM            : "))
        self.uts = int(input("Nilai UTS      : "))
        self.uas = int(input("Nilai UAS      : "))
        self.tugas = int(input("Nilai Tugas    : "))
        self.total = self.uts*35/100 + self.uas*35/100 + self.tugas*30/100
        data[self.nama] = self.nim, self.uts, self.uas, self.tugas, self.total
```
- Setelah itu kita membuat class kedua, yaitu turunan dari class induk
```
class Mahasiswa(Data):
```
- Kemudian kita masukan sisa fungsinya pada turunan terakhir
###### Fungsi untuk Menampilkan Data
```
def tampilkan(self):
        print("Tampilkan Data")
        if data.items():
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            i = 0
            for z in data.items():
                i += 1
                print("| {no:2d} | {0:15s} | {1:15d} | {2:5d} | {3:5d} | {4:7d} | {5:7.2f} |"
                    .format(z[0][:13], z[1][0], z[1][1], z[1][2], z[1][3], z[1][4], no=i))
            print("=" * 78)
        else:
            print("="*78)
            print("|                               Daftar Mahasiswa                             |")
            print("="*78)
            print("|No. | Nama            |       NIM       |  UTS  |  UAS  |  Tugas  |  Akhir  |")
            print("="*78)
            print("|                                TIDAK ADA DATA                              |")
            print("="*78)
        return
```
###### Fungsi untuk Menghapus Data bedasarkan Nama
```
def hapus(self):
        print("Hapus Data")
        self.nama = input("Masukkan Nama  : ")
        if self.nama in data.keys():
            del data[self.nama]
        else:
            print("Nama {0} Tidak Ditemukan".format(self.nama))
        return
```
###### Fungsi untuk Mengubah Data bedasarkan Nama
```
def ubah(self):
        print("Ubah Data")
        self.nama = input("Masukkan Nama  : ")
        if self.nama in data.keys():
            self.nim = int(input("NIM            : "))
            self.uts = int(input("Nilai UTS      : "))
            self.uas = int(input("Nilai UAS      : "))
            self.tugas = int(input("Nilai Tugas    : "))
            self.total = self.uts*35/100 + self.uas*35/100 + self.tugas*30/100
            data[self.nama] = self.nim, self.uts, self.uas, self.tugas, self.total
        else:
            print("Nama {0} tidak ditemukan".format(self.nama))
```
- Cara memanggil class cukup mudah, hanya dengan menambahkan 1 variabel sebagai dorongan class beserta fungsinya, seperti ini:
```
dataMhs = Mahasiswa("nama","nim","uts","uas","tugas","total")
dataMhs.tambah()
dataMhs.tampilkan()
dataMhs.ubah()
dataMhs.hapus()
dataMhs.tampilkan()
```
#### Tampilan Program Ketika Dijalankan
![gambar](pr8/8.1.png)
