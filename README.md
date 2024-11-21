# labpy05

LATIHAN 1

Soal
• Buat Dictionary daftar kontak
• Nama sebagai key, dan nomor sebagai value
• Tampilkan kontaknya Ari
• Tambah kontak baru dengan nama Riko, nomor 087654544
• Ubah kontak Dina dengan nomor baru 088999776
• Tampilkan semua Nama
• Tampilkan semua Nomor
• Tampilkan daftar Nama dan nomornya
• Hapus kontak Dina.

KODE PYTHON

    # 1. Buat Dictionary daftar kontak
    daftar_kontak = {
    "Krisna": "089615429182",
    "Anggri": "081231294126",
    "Ani": "085631826513"
    }

    # 2. Tampilkan kontaknya Krisna
    print("Kontak Krisna:", daftar_kontak.get("Krisna"))

    # 3. Tambah kontak baru dengan nama Anggri, nomor 081231294126
    daftar_kontak["Anggri"] = "081231294126"
    print("Kontak Anggri telah ditambahkan.")

    # 4. Ubah kontak Ani dengan nomor baru 085631826513
    daftar_kontak["Ani"] = "085631826513"
    print("Kontak Ani telah diubah.")

    # 5. Tampilkan semua Nama
    print("Semua Nama:", list(daftar_kontak.keys()))

    # 6. Tampilkan semua Nomor
    print("Semua Nomor:", list(daftar_kontak.values()))

    # 7. Tampilkan daftar Nama dan nomornya
    print("Daftar Nama dan Nomornya:")
    for nama, nomor in daftar_kontak.items():
    print(f"{nama}: {nomor}")

    # 8. Hapus kontak Ani
    if "Ani" in daftar_kontak:
    del daftar_kontak["Ani"]
    print("Kontak Ani telah dihapus.")
    else:
    print("Kontak Ani tidak ditemukan.")

PENJELASAN:
1. Membuat Dictionary Daftar Kontak ( Di sini, sebuah dictionary bernama daftar_kontak dibuat. Kunci (key) dari dictionary ini adalah nama-nama kontak (Krisna, Anggri, Ani), dan nilainya (value) adalah nomor telepon yang sesuai. )
2. Menampilkan Kontak Krisna ( Menggunakan metode get(), kode ini menampilkan nomor telepon yang terdaftar untuk kontak "Krisna". Jika "Krisna" tidak ada dalam dictionary, get() akan mengembalikan None tanpa menghasilkan error. )
3. Menambahkan Kontak Baru ( Di sini, kontak baru dengan nama "Anggri" dan nomor "081231294126" ditambahkan ke dalam dictionary. Jika nama tersebut sudah ada, nilainya akan diperbarui. )  Secara keseluruhan, kode ini menunjukkan bagaimana cara membuat, mengubah, menampilkan, dan menghapus data dalam sebuah dictionary yang digunakan untuk menyimpan daftar kontak.
4. Mengubah Kontak Ani ( Kontak "Ani" diubah dengan nomor baru "085631826513". Jika "Ani" tidak ada, maka kontak baru akan ditambahkan. ) 
5. Menampilkan Semua Nama (digunakan untuk mendapatkan semua kunci (nama) dari dictionary, yang kemudian diubah menjadi list untuk ditampilkan)
6. Menampilkan Semua Nomor (digunakan untuk mendapatkan semua nilai (nomor telepon) dari dictionary, yang juga diubah menjadi list untuk ditampilkan.)
7. Menampilkan Daftar Nama dan Nomornya (digunakan untuk mendapatkan pasangan kunci-nilai dari dictionary. Dalam loop, setiap nama dan nomor ditampilkan dalam format yang rapi.)
8.Menghapus Kontak Ani

INPUT
<img width="482" alt="Cuplikan layar 2024-11-21 114403" src="https://github.com/user-attachments/assets/0543cc56-c8a0-46ea-a661-b7f163ac7cab">
<img width="278" alt="Cuplikan layar 2024-11-21 114416" src="https://github.com/user-attachments/assets/ea9aaded-ab49-47b5-af85-2d196e21b660">
OUTPUT
<img width="370" alt="Cuplikan layar 2024-11-21 114444" src="https://github.com/user-attachments/assets/993dddd1-7350-4cc9-b5a7-020f7505e7cc">

PRAKTIKUM 5
Soal
Buat program sederhana yang akan menampilkan daftar nilai mahasiswa, dengan ketentuan : 
1. Program dibuat dengan menggunakan Dictionary
2. Tampilkan menu pilihan: (Tambah Data, Ubah Data, Hapus Data, Tampilkan Data, Cari Data)
3. Nilai Akhir diambil dari perhitungan 3 komponen nilai (tugas: 30%, uts: 35%, uas: 35%)
4. Buat flowchart dan penjelasan programnya

KODE PYTHON:
    
    #Pastikan dictionary mahasiswa sudah didefinisikan
    mahasiswa = {}

    def tambah_data():
    print("\n=== TAMBAH DATA MAHASISWA ===")
    nama = input("Masukkan Nama: ")
    
    if nama in mahasiswa:  # Cek apakah nama sudah ada
        print("Data mahasiswa sudah ada!")
        return
    
    try:
        # Input nilai
        tugas = float(input("Nilai Tugas (0-100): "))
        uts = float(input("Nilai UTS (0-100): "))
        uas = float(input("Nilai UAS (0-100): "))
        
        # Validasi rentang nilai
        if not (0 <= tugas <= 100 and 0 <= uts <= 100 and 0 <= uas <= 100):
            print("Nilai harus berada dalam rentang 0-100!")
            return
        
        # Hitung nilai akhir
        nilai_akhir = (tugas * 0.3) + (uts * 0.35) + (uas * 0.35)
        
        # Simpan ke dictionary
        mahasiswa[nama] = {
            "tugas": tugas,
            "uts": uts,
            "uas": uas,
            "nilai_akhir": nilai_akhir
        }
        print("Data berhasil ditambahkan!")
    
    except ValueError:
        print("Input tidak valid! Pastikan untuk memasukkan angka.")

    # Contoh pemanggilan fungsi
    tambah_data()
    
PENJELASAN : 
1. Fungsi lihat_data():
        Menampilkan daftar nilai mahasiswa dalam format tabel.
        Jika tidak ada data, menampilkan pesan bahwa tidak ada data.
        Menghitung nilai akhir berdasarkan bobot: 30% untuk tugas, 35% untuk UTS, dan 35% untuk UAS.
        Menggunakan enumerate untuk menampilkan nomor urut mahasiswa.
2. Fungsi tambah_data():
        Meminta input dari pengguna untuk menambahkan data mahasiswa baru.
        Data yang dimasukkan (NIM, nama, nilai tugas, UTS, dan UAS) disimpan dalam dictionary dan ditambahkan ke list data_mahasiswa.
        Menampilkan pesan konfirmasi bahwa data berhasil ditambahkan.
3. Fungsi ubah_data():
        Menampilkan data yang ada dengan memanggil lihat_data().
        Meminta pengguna untuk memasukkan nomor data yang ingin diubah.
        Jika nomor valid, pengguna diminta untuk memasukkan data baru, yang kemudian menggantikan data lama di list.
        Menampilkan pesan konfirmasi bahwa data berhasil diubah.
4. Fungsi hapus_data():
        Menampilkan data yang ada dengan memanggil lihat_data().
        Meminta pengguna untuk memasukkan nomor data yang ingin dihapus.
        Jika nomor valid, data dihapus dari list menggunakan pop().
        Menampilkan pesan konfirmasi bahwa data berhasil dihapus.
5. Fungsi cari_data():
        Meminta pengguna untuk memasukkan NIM yang ingin dicari.
        Mencari data mahasiswa berdasarkan NIM dan menampilkan hasilnya dalam format tabel.
        Jika tidak ditemukan, menampilkan pesan bahwa data tidak ditemukan.

INPUT
<img width="596" alt="Cuplikan layar 2024-11-21 113251" src="https://github.com/user-attachments/assets/447558f9-5cca-42ec-a84b-116747254394">
<img width="464" alt="Cuplikan layar 2024-11-21 113305" src="https://github.com/user-attachments/assets/4b54af16-eb15-4d5a-85d7-7428c08d19d1">
OUTPUT
<img width="363" alt="Cuplikan layar 2024-11-21 113332" src="https://github.com/user-attachments/assets/3bb2dd99-1fc9-4164-a861-cd70ed1b2c0a">

FLOWCHART
![FLOWCHART PRAKTIKUM 5](https://github.com/user-attachments/assets/7abe3ef3-2dc7-4c1a-92bf-d0031d1c2eac)



