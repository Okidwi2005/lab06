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
