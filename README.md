# PRAKTIKUM 8

Nama : Dhea Dwi Adelia

NIM  : 312210116

Kelas : TI.22.A.1

## Tugas Praktikum 8
Buat program sederhana dengan mengaplikasikan penggunaan class. Buatlah class untuk menampilkan daftar nilai mahasiswa, dengan ketentuan:

- Method tambah() untuk menambah data
- Method tampilkan() untuk menampilkan data
- Method hapus(nama) untuk menghapus data berdasarkan nama
- Method ubah(nama) untuk mengubah data berdasarkan nama
- Buat diagram class, flowchart dan penjelasan programnya pada README.md.
- Commit dan push repository ke github.


### Script :
    class mahasiswa:
        def __init__(self, nama, nim, tugas, uts, uas):
            self.nama = nama
            self.nim = nim
            self.tugas = tugas
            self.uts = uts
            self.uas = uas

        def tambah(self,nama,nim,tugas,uts,uas):
            data.nama.append(nama)
            data.nim.append(nim)
            data.tugas.append(tugas)
            data.uts.append(uts)
            data.uas.append(uas)

        def lihat(self):
            for i in range(len(data.nama)):
                print("|", i+1, "  |", end="")
                print('{0:<25}'.format(self.nama[i]), end="")
                print("|", self.nim[i], end="")
                print(" |", self.tugas[i], end="")
                print("    |", self.uts[i], end="")
                print("  |", self.uas[i], " | ", end="")
                print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")

        def ubah(self,nama,nim,tugas,uts,uas):
            self.nama[no] = nama
            self.nim[no] = nim
            self.tugas[no] = tugas
            self.uts[no] = uts
            self.uas[no] = uas

        def hapus(self):
            del self.nama[no]
            del self.nim[no]
            del self.tugas[no]
            del self.uts[no]
            del self.uas[no]

    data = mahasiswa([],[],[],[],[])

    while True:
        menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
        if menu == "t" or menu == "T":
           print("\nTambah Data")
           data.tambah(
               input("Masukkan Nama : "),
               input("Masukkan NIM : "),
               int(input("Nilai Tugas : ")),
               int(input("Nilai UTS : ")),
               int(input("Nilai UAS : "))
               )
           print("\nData berhasil ditambahkan")

        elif menu == "l" or menu == "L":
            print("\nDaftar Nilai")
            print("==========================================================================")
            print("| No  |          Nama           |    NIM    | TUGAS | UTS | UAS |  AKHIR |")
            print("==========================================================================")
            if len(data.nama) != 0:
                data.lihat()
            else:
                print("                         TIDAK ADA DATA                               ")
            print("==========================================================================")

        elif menu == "u" or menu == "U":
            print("\nUbah Data")
            ubah = input("Masukkan Nama : ")
            if ubah in data.nama:
               no = data.nama.index(ubah)
               print("Masukkan Data Yang Baru : ")
               data.ubah(
                   input("NIM : "),
                   input("Nama : "),
                   int(input("Nilai Tugas : ")),
                   int(input("Nilai UTS : ")),
                   int(input("Nilai UAS : "))
                   )
            else:
                print(ubah, "tidak ada di dalam data")

        elif menu == "h" or menu == "H":
            print("\nHapus Data")
            hapus = input("Masukkan Nama : ")
            if hapus in data.nama:
                no = data.nama.index(hapus)
                data.hapus()
                print("Data", hapus, "Berhasil dihapus")
            else:
                print(hapus, "tidak ada di dalam data")

        elif menu == "k" or menu == "K":
            print("\nTerimakasih\n")
            break

        else:
            print("\nPerintah yang dimasukkan salah!\n")
            

![Screenshot (181)](https://user-images.githubusercontent.com/115794875/207289260-14ac4e97-61bc-4421-9acb-6e2890c01b78.png)
![Screenshot (182)](https://user-images.githubusercontent.com/115794875/207289470-73177ec7-d6f9-40b9-bc8f-8c4dfae4caae.png)
![Screenshot (183)](https://user-images.githubusercontent.com/115794875/207289538-c3b5180a-62dd-47f3-b61f-deff204adf9f.png)
![Screenshot (184)](https://user-images.githubusercontent.com/115794875/207289599-2cf156a5-1e54-42bf-8779-d0fb2529096f.png)


## Hasil Run & Penjelasan Program :
- Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut Nama, NIM, nilai tugas, nilai UTS dan nilai UAS. Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan **def__init__ dan juga self.**

      class mahasiswa:
          def __init__(self, nama, nim, tugas, uts, uas):
              self.nama = nama
              self.nim = nim
              self.tugas = tugas
              self.uts = uts
              self.uas = uas

- Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi Nama, NIM, nilai tugas, nilai UTS dan nilai UAS.

      data = mahasiswa([],[],[],[],[])  

- Kita akan buat beberapa method untuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() supaya data yang terakhir ditambahkan ada di urutan list paling akhir.

      def tambah(self,nama,nim,tugas,uts,uas):
              data.nama.append(nama)
              data.nim.append(nim)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)

- Ini tampilan jika kita menginput method : `Tambah()`

![image](https://user-images.githubusercontent.com/115794875/207290191-5c8db60a-80f9-468f-a691-b22c00a992da.png)

- Fungsi membuat method lihat() yaitu untuk menampilkan seluruh data yang sudah kita tambahkan tadi. Jika tidak ada data sama sekali, maka akan muncul tulisan **TIDAK ADA DATA.**

      def lihat(self):
              for i in range(len(data.nama)):
                  print("|", i+1, "  |", end="")
                  print('{0:<25}'.format(self.nama[i]), end="")
                  print("|", self.nim[i], end="")
                  print(" |", self.tugas[i], end="")
                  print("    |", self.uts[i], end="")
                  print("  |", self.uas[i], " | ", end="")
                  print(f'{((self.tugas[i]*30/100) + (self.uts[i]*35/100) + (self.uas[i]*35/100)) :.2f}', " |")
                  
- Ini tampilan jika kita menginput method : `Lihat()`

![image](https://user-images.githubusercontent.com/115794875/207290416-d32c1b2e-c7c8-44fa-b1cf-369047f4af5c.png)

- Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.

      def ubah(self,nama,nim,tugas,uts,uas):
              self.nama[no] = nama
              self.nim[no] = nim
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas
              
- Ini tampilan jika kita menginput method : `Ubah()`

![image](https://user-images.githubusercontent.com/115794875/207290702-fa7555ff-19ff-4635-9116-bf1cff6180d4.png)

- Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).

      def hapus(self):
              del self.nama[no]
              del self.nim[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]
              
- Ini tampilan jika kita menginput method : `Hapus()`

![image](https://user-images.githubusercontent.com/115794875/207290874-4d8e2b02-3de2-48fa-97be-6a41cc2aaac7.png)

- Ini tampilan jika kita menginput method : 'Keluar()'

![image](https://user-images.githubusercontent.com/115794875/207291095-632cd1bf-2049-4cdd-911d-d740cb155070.png)


## Diagram Class Praktikum 8

![Diagram Kelas](https://user-images.githubusercontent.com/115678171/207250890-b0888c56-9f40-48fb-a411-f873e2c2194c.jpg)

## Flowchart Praktikum 8

![flowchart22_page-0001](https://user-images.githubusercontent.com/115794875/207291238-450c7ecd-5f48-4ed2-a3b3-84cfbead1afd.jpg)

## Sekian, Terima kasih
