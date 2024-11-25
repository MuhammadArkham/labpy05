## PRAKTIKUM 5

NAMA : Muhammad Arkhamullah Rifai Asshidiq

Mata kuliah : Bahasa pemrograman

NIM : 312410545

## Tugas Praktikum 5
```python
mahasiswa = {}

def tambah_data():
    while True:
        nama = input("Nama        : ")
        nim = input("NIM         : ")
        tugas = float(input("Nilai Tugas : "))
        uts = float(input("Nilai UTS   : "))
        uas = float(input("Nilai UAS   : "))
        
        nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        
        mahasiswa[nim] = {
            'nama': nama, 
            'tugas': tugas, 
            'uts': uts, 
            'uas': uas, 
            'akhir': nilai_akhir
            }
        
        lanjut = input("\nTambah data (y/t) ? ")
        if lanjut.lower() == 't':
            break

def ubah_data():
    nim = input("Masukkan NIM mahasiswa yang akan diubah: ")
    if nim in mahasiswa:
        print("\nPilih data yang akan diubah:")
        print("1. Nama")
        print("2. Nilai Tugas")
        print("3. Nilai UTS")
        print("4. Nilai UAS")
        
        pilihan = input("Masukkan pilihan (1-4): ")
        
        if pilihan == '1':
            mahasiswa[nim]['nama'] = input("Masukkan nama baru: ")
        elif pilihan == '2':
            tugas = float(input("Masukkan nilai tugas baru: "))
            mahasiswa[nim]['tugas'] = tugas
        elif pilihan == '3':
            uts = float(input("Masukkan nilai UTS baru: "))
            mahasiswa[nim]['uts'] = uts
        elif pilihan == '4':
            uas = float(input("Masukkan nilai UAS baru: "))
            mahasiswa[nim]['uas'] = uas
        
        mahasiswa[nim]['akhir'] = (
            mahasiswa[nim]['tugas'] * 0.3 + 
            mahasiswa[nim]['uts'] * 0.35 + 
            mahasiswa[nim]['uas'] * 0.35
        )
        print("Data berhasil diubah!")
    else:
        print("NIM tidak ditemukan!")

def hapus_data():
    nim = input("Masukkan NIM mahasiswa yang akan dihapus: ")
    if nim in mahasiswa:
        del mahasiswa[nim]
        print("Data berhasil dihapus!")
    else:
        print("NIM tidak ditemukan!")

def tampilkan_data():
    if not mahasiswa:
        print("Tidak ada data!")
        return
    
    print("\n" + "="*72)
    print("|                        Daftar Nilai Mahasiswa                        |")
    print("="*72)
    print("| No |     Nama       |     NIM      | Tugas  |  UTS  |  UAS  | Akhir  |")
    print("="*72)
    
    for i, (nim, data) in enumerate(mahasiswa.items(), 1):
        print("| {:<2} | {:<14} | {:<12} | {:<6} | {:<5} | {:<5} | {:<7.2f}|".format(
            i, data['nama'], nim, data['tugas'], data['uts'], data['uas'], data['akhir'] ))
    print("="*72)

def cari_data():
    nim = input("Masukkan NIM mahasiswa yang dicari: ")
    if nim in mahasiswa:
        data = mahasiswa[nim]
        print("\nData Mahasiswa:")
        print(f"Nama        : {data['nama']}")
        print(f"NIM         : {nim}")
        print(f"Nilai Tugas : {data['tugas']}")
        print(f"Nilai UTS   : {data['uts']}")
        print(f"Nilai UAS   : {data['uas']}")
        print(f"Nilai Akhir : {data['akhir']:.2f}")
    else:
        print("NIM tidak ditemukan!")

def main():
    while True:
        print("\nProgram Input Nilai Mahasiswa")
        print("="*30)
        print("1. Tambah Data")
        print("2. Ubah Data")
        print("3. Hapus Data")
        print("4. Tampilkan Data")
        print("5. Cari Data")
        print("6. Keluar")
        
        pilihan = input("Masukkan pilihan (1-6): ")
        
        if pilihan == '1':
            tambah_data()
        elif pilihan == '2':
            ubah_data()
        elif pilihan == '3':
            hapus_data()
        elif pilihan == '4':
            tampilkan_data()
        elif pilihan == '5':
            cari_data()
        elif pilihan == '6':
            print("Terima kasih!")
            break
        else:
            print("Pilihan tidak valid!")

if __name__ == "__main__":
    main()
```

## Hasil kode Program
![Foto](https://github.com/MuhammadArkham/Foto/blob/main/Screenshot%202024-11-21%20195823.png?raw=true)
![Foto](https://github.com/MuhammadArkham/Foto/blob/main/Screenshot%202024-11-21%20195854.png?raw=true)
![Foto](https://github.com/MuhammadArkham/Foto/blob/main/Screenshot%202024-11-21%20200245.png?raw=true)

## Gambar Flowchart
![Foto](https://github.com/MuhammadArkham/labpy05/blob/main/Flowchart%20.png?raw=true)

## Penjelasan alur algoritma program

 program ini dirancang untuk mengelola data mahasiswa dengan mudah. Menggunakan struktur dictionary sebagai tempat penyimpanan, program ini memungkinkan pengguna untuk melakukan berbagai tindakan, seperti menambahkan, mengedit, menghapus, melihat, dan mencari informasi serta nilai akademik mahasiswa secara efisien.

__Struktur Dasar Kode ini memiliki beberapa komponen utama:__

Program menggunakan dictionary mahasiswa untuk menyimpan data
Setiap mahasiswa diidentifikasi dengan NIM sebagai key
Data mahasiswa meliputi: nama, nilai tugas, UTS, UAS, dan nilai akhir


Fungsi-fungsi Utama:
```python
tambah_data()
```
Memungkinkan input data mahasiswa baru
Menghitung nilai akhir dengan bobot: Tugas (30%), UTS (35%), UAS (35%)
Memiliki opsi untuk menambah data lagi atau berhenti
```python
ubah_data()
```
Mencari mahasiswa berdasarkan NIM
Memungkinkan perubahan nama atau nilai
Menghitung ulang nilai akhir jika nilai diubah
```python
C) hapus_data()
```
Menghapus data mahasiswa berdasarkan NIM
Memberikan konfirmasi keberhasilan/kegagalan
```python
tampilkan_data()
```
Menampilkan tabel berisi semua data mahasiswa
Format tabel rapi dengan header dan separator
```python
cari_data()
```
Mencari dan menampilkan detail mahasiswa berdasarkan NIM
Menampilkan semua informasi mahasiswa termasuk nilai akhir
```python
main()

Menu utama program dengan 6 pilihan
Loop terus berjalan sampai user memilih keluar
