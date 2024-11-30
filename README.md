# Praktikum 6
## Deskripsi tugas
Buat program sederhana dengan mengaplikasikan penggunaan fungsi
yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan: 
  - Fungsi tambah() untuk menambah data
  - Fungsi tampilkan() untuk menampilkan data
  - Fungsi hapus(nama) untuk menghapus data berdasarkan nama
  - Fungsi ubah(nama) untuk mengubah data berdasarkan nama

## Kode program
```python
# Inisialisasi daftar nilai mahasiswa
daftar_nilai = []

# Fungsi untuk menambah data mahasiswa
def tambah(nama, nilai):
    daftar_nilai.append({"nama": nama, "nilai": nilai})
    print(f"Data mahasiswa '{nama}' berhasil ditambahkan.\n")

# Fungsi untuk menampilkan semua data mahasiswa
def tampilkan():
    if not daftar_nilai:
        print("Daftar nilai kosong.\n")
    else:
        print("Daftar Nilai Mahasiswa:")
        for i, data in enumerate(daftar_nilai, 1):
            print(f"{i}. Nama: {data['nama']}, Nilai: {data['nilai']}")
        print()

# Fungsi untuk menghapus data mahasiswa berdasarkan nama
def hapus(nama):
    global daftar_nilai
    daftar_nilai = [data for data in daftar_nilai if data["nama"].lower() != nama.lower()]
    print(f"Data mahasiswa dengan nama '{nama}' berhasil dihapus (jika ada).\n")

# Fungsi untuk mengubah data mahasiswa berdasarkan nama
def ubah(nama, nilai_baru):
    for data in daftar_nilai:
        if data["nama"].lower() == nama.lower():
            data["nilai"] = nilai_baru
            print(f"Data mahasiswa '{nama}' berhasil diubah menjadi nilai {nilai_baru}.\n")
            return
    print(f"Data mahasiswa dengan nama '{nama}' tidak ditemukan.\n")

# Menu utama
def menu():
    while True:
        print("=== Program Daftar Nilai Mahasiswa ===")
        print("1. Tambah Data")
        print("2. Tampilkan Data")
        print("3. Hapus Data")
        print("4. Ubah Data")
        print("5. Keluar")
        pilihan = input("Pilih menu (1-5): ")
        print()
        
        if pilihan == "1":
            nama = input("Masukkan nama mahasiswa: ")
            nilai = input("Masukkan nilai mahasiswa: ")
            tambah(nama, nilai)
        elif pilihan == "2":
            tampilkan()
        elif pilihan == "3":
            nama = input("Masukkan nama mahasiswa yang akan dihapus: ")
            hapus(nama)
        elif pilihan == "4":
            nama = input("Masukkan nama mahasiswa yang akan diubah: ")
            nilai_baru = input("Masukkan nilai baru: ")
            ubah(nama, nilai_baru)
        elif pilihan == "5":
            print("Program selesai. Terima kasih!")
            break
        else:
            print("Pilihan tidak valid. Silakan coba lagi.\n")

# Menjalankan program
menu()
```

## Output progran
![Screenshot 2024-11-30 140653](https://github.com/user-attachments/assets/a73d1610-4441-4bbf-9125-12eaf4102330)
![Screenshot 2024-11-30 140725](https://github.com/user-attachments/assets/f436c93b-1d73-4911-a965-ab8f8cacdb29)

## Penjelasan program
1. Program menggunakan daftar (list) untuk menyimpan data mahasiswa sebagai elemen berupa dictionary dengan kunci "nama" dan "nilai".
2. Fungsi yang disediakan:
  - Tambah(nama, nilai): Menambahkan data mahasiswa.
  - Tampilkan(): Menampilkan semua data mahasiswa.
  - Hapus(nama): Menghapus data mahasiswa berdasarkan nama (case-insensitive).
  - Ubah(nama, nilai_baru): Mengubah nilai mahasiswa berdasarkan nama.
3. Menu utama memungkinkan pengguna untuk memilih salah satu dari fungsi tersebut, dan prosesnya akan terus berjalan hingga pengguna memilih opsi "Keluar".

## Flowchart
![FLOWCHART06](https://github.com/user-attachments/assets/474243a8-720f-4231-b153-1a5eb87ad03e)
