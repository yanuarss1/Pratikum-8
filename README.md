# Pratikum-8
# 312410107
# Dwi Yanuar Prasetia
# TI.24.A1 

# Deskripsi Program Daftar Nilai Mahasiswa
Daftar Nilai Mahasiswa adalah sebuah program berbasis Python untuk mengelola data nilai mahasiswa. Program ini memungkinkan pengguna untuk menambah, menampilkan, menghapus, dan mengubah data nilai mahasiswa dengan mudah melalui antarmuka berbasis teks. Data disimpan dalam bentuk dictionary, sehingga pengelolaan data menjadi cepat dan efisien.

# Fitur program 
- Tambah Data: Menambahkan nama dan nilai mahasiswa ke dalam daftar.
- Tampilkan Data: Menampilkan daftar semua mahasiswa beserta nilainya.
- Hapus Data: Menghapus data mahasiswa berdasarkan nama.
- Ubah Data: Mengubah nilai mahasiswa tertentu.
- Exit Program: Keluar dari program.

# Flowchart 
![Flowchart](https://github.com/user-attachments/assets/de5470e0-9e04-4cea-9d76-2b999fe5fe5b)

# Kode Program 
``` Python
class DaftarNilaiMahasiswa:
    def __init__(self):
        self.data = {}

    def tambah(self, nama, nilai):
        self.data[nama] = nilai
        print(f"Data {nama} dengan nilai {nilai} berhasil ditambahkan.")

    def tampilkan(self):
        if not self.data:
            print("Belum ada data yang ditambahkan.")
        else:
            print("Daftar Nilai Mahasiswa:")
            for nama, nilai in self.data.items():
                print(f"{nama}: {nilai}")

    def hapus(self, nama):
        if nama in self.data:
            del self.data[nama]
            print(f"Data {nama} berhasil dihapus.")
        else:
            print(f"Data dengan nama {nama} tidak ditemukan.")

    def ubah(self, nama, nilai_baru):
        if nama in self.data:
            self.data[nama] = nilai_baru
            print(f"Data {nama} berhasil diubah menjadi {nilai_baru}.")
        else:
            print(f"Data dengan nama {nama} tidak ditemukan.")


# Contoh penggunaan program
if __name__ == "__main__":
    daftar_nilai = DaftarNilaiMahasiswa()
    
    while True:
        print("\nMenu:")
        print("1. Tambah data")
        print("2. Tampilkan data")
        print("3. Hapus data")
        print("4. Ubah data")
        print("5. Keluar")
        
        pilihan = input("Pilih menu (1-5): ")
        
        if pilihan == "1":
            nama = input("Masukkan nama: ")
            try:
                nilai = float(input("Masukkan nilai: "))  # Pastikan nilai adalah angka
                daftar_nilai.tambah(nama, nilai)
            except ValueError:
                print("Nilai harus berupa angka.")
        elif pilihan == "2":
            daftar_nilai.tampilkan()
        elif pilihan == "3":
            nama = input("Masukkan nama yang akan dihapus: ")
            daftar_nilai.hapus(nama)
        elif pilihan == "4":
            nama = input("Masukkan nama yang akan diubah: ")
            try:
                nilai_baru = float(input("Masukkan nilai baru: "))  # Pastikan nilai baru adalah angka
                daftar_nilai.ubah(nama, nilai_baru)
            except ValueError:
                print("Nilai baru harus berupa angka.")
        elif pilihan == "5":
            print("Program selesai.")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.")

  ```

## Output Program 
````
Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama: vivit nurul hidayah
Masukkan nilai: 98
Data vivit nurul hidayah dengan nilai 98.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 2                  
Daftar Nilai Mahasiswa:
vivit nurul hidayah: 98.0

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 1
Masukkan nama: jeon jungkook
Masukkan nilai: 90
Data jeon jungkook dengan nilai 90.0 berhasil ditambahkan.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 2
Daftar Nilai Mahasiswa:
vivit nurul hidayah: 98.0
jeon jungkook: 90.0

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 3
Masukkan nama yang akan dihapus: jeon jungkook
Data jeon jungkook berhasil dihapus.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 4
Masukkan nama yang akan diubah: vivit nurul hidayah
Masukkan nilai baru: 99
Data vivit nurul hidayah berhasil diubah menjadi 99.0.

Menu:
1. Tambah data
2. Tampilkan data
3. Hapus data
4. Ubah data
5. Keluar
Pilih menu (1-5): 5
Program selesai.
````
# Diagram Class 
```
+-------------------------+
|  DaftarNilaiMahasiswa   |
+-------------------------+
| - data: dict            |
+-------------------------+
| + __init__()            |
| + tambah(nama, nilai)   |
| + tampilkan()           |
| + hapus(nama)           |
| + ubah(nama, nilai_baru)|
+-------------------------+
```
# Cara Kerja Program 
1. Inisialisasi
- Program dimulai dengan membuat objek dari class DaftarNilaiMahasiswa.
- Data mahasiswa disimpan dalam dictionary kosong.
2. Tampilkan Menu
- Program menampilkan menu utama dengan opsi:
    - Tambah data
    - Tampilkan data
    - Hapus data
    - Ubah data
    - Keluar
3. Proses Berdasarkan Pilihan
- Tambah Data: Menambahkan nama dan nilai mahasiswa.
- Tampilkan Data: Menampilkan semua data mahasiswa.
- Hapus Data: Menghapus data mahasiswa berdasarkan nama.
- Ubah Data: Mengubah nilai mahasiswa tertentu.
- Keluar: Mengakhiri program.
4. Validasi Input
- Nilai mahasiswa diverifikasi sebagai angka (float).
- Program memberikan pesan error jika input tidak valid.
5. Sesi Berulang
- Program berjalan dalam loop hingga pengguna memilih "Keluar".
