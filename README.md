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


### Rumus :
    class mahasiswa:
        def __init__(self, nim, nama, tugas, uts, uas):
            self.nim = nim
            self.nama = nama
            self.tugas = tugas
            self.uts = uts
            self.uas = uas

        def tambah(self,nim,nama,tugas,uts,uas):
            data.nim.append(nim)
            data.nama.append(nama)
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

        def ubah(self,nim,nama,tugas,uts,uas):
            self.nim[no] = nim
            self.nama[no] = nama
            self.tugas[no] = tugas
            self.uts[no] = uts
            self.uas[no] = uas

        def hapus(self):
            del self.nim[no]
            del self.nama[no]
            del self.tugas[no]
            del self.uts[no]
            del self.uas[no]

    data = mahasiswa([],[],[],[],[])

    while True:
        menu = input("\n[(L)ihat, (T)ambah, (U)bah, (H)apus, (K)eluar]:")
        if menu == "t" or menu == "T":
           print("\nTambah Data")
           data.tambah(
               input("Masukkan NIM : "),
               input("Masukkan Nama : "),
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
            
## Program :

![Screenshot_20221213_135356](https://user-images.githubusercontent.com/115678171/207250000-b495eb18-3143-4193-854d-33148c7a661d.png)

![Screenshot_20221213_135420](https://user-images.githubusercontent.com/115678171/207250029-eab8e3ea-62cb-4f35-ad24-a1ee7043ed6b.png)

![Screenshot_20221213_135457](https://user-images.githubusercontent.com/115678171/207250521-b012e655-b53e-4ca2-9ae1-d4e11947d4e3.png)

![Screenshot_20221213_135520](https://user-images.githubusercontent.com/115678171/207250547-900b9065-59b3-4055-a976-8e39c6892e89.png)


## Hasil Run & Penjelasan Program :
- Pertama kita mendeklarasikan sebuah class mahasiswa yang didalamnya terdapat atribut NIM, Nama, nilai tugas, nilai UTS dan nilai UAS. Jangan lupa, untuk mendeklarasikan sebuah class didalam OOP kita harus menggunakan **def__init__ dan juga self.**

      class mahasiswa:
          def __init__(self, nim, nama, tugas, uts, uas):
              self.nim = nim
              self.nama = nama
              self.tugas = tugas
              self.uts = uts
              self.uas = uas

- Seperti biasa, deklarasikan satu dictionary kosong sebagai tempat menyimpan data-data yang sudah kita input. Ada 5 list kosong yang nantinya berisi NIM, Nama, nilai tugas, nilai UTS dan nilai UAS.

      data = mahasiswa([],[],[],[],[])  

- Kita akan buat beberapa method untuk menambahkan, menampilkan, menghapus, mengubah data mahasiswa. Pertama membuat method tambah(), method ini berfungsi untuk menambahkan data. Dalam method ini kita menggunakan append() supaya data yang terakhir ditambahkan ada di urutan list paling akhir.

      def tambah(self,nim,nama,tugas,uts,uas):
              data.nim.append(nim)
              data.nama.append(nama)
              data.tugas.append(tugas)
              data.uts.append(uts)
              data.uas.append(uas)

- Ini tampilan jika kita menginput method : `Tambah()`

![Screenshot_20221213_135933](https://user-images.githubusercontent.com/115678171/207250612-88360501-2d93-484c-9447-55a100442709.png)

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

![Screenshot_20221213_135944](https://user-images.githubusercontent.com/115678171/207250676-cc3b0044-b5a8-402a-83a2-c42384ccc4c9.png)

- Fungsi membuat method ubah() yaitu untuk mengubah data. jika method ini diinput, maka data Nama, NIM, nilai tugas, nilai UTS, nilai UAS index nomor - (no) akan diubah sesuai dengan inputan dari user. Index ke - (no) akan dicari secara otomatis sesuai dengan nama yang ingin diubah oleh user.

      def ubah(self,nim,nama,tugas,uts,uas):
              self.nim[no] = nim
              self.nama[no] = nama
              self.tugas[no] = tugas
              self.uts[no] = uts
              self.uas[no] = uas
              
- Ini tampilan jika kita menginput method : `Ubah()`

![Screenshot_20221213_140022](https://user-images.githubusercontent.com/115678171/207250744-4d5931ae-79bc-4528-baba-e18e973e87f2.png)

- Terakhir kita membuat method hapus(), yang berfungsi untuk menghapus data berdasarkan nama. Kita bisa menggunakan del untuk menghapus datanya. Seperti sebelumnya, nomor index list yang akan dihapus disesuaikan dengan inputan dari user. Yaitu index nomor ke - (no).

      def hapus(self):
              del self.nim[no]
              del self.nama[no]
              del self.tugas[no]
              del self.uts[no]
              del self.uas[no]
              
- Ini tampilan jika kita menginput method : `Hapus()`

![Screenshot_20221213_140035](https://user-images.githubusercontent.com/115678171/207250792-e3446d28-e0ea-410e-9843-68e10df24990.png)


## Diagram Class Praktikum 8

![Diagram Kelas](https://user-images.githubusercontent.com/115678171/207250890-b0888c56-9f40-48fb-a411-f873e2c2194c.jpg)

## Flowchart Praktikum 8

![Flowchart](https://user-images.githubusercontent.com/115678171/207250962-5e5694c8-4181-4fbb-b5b1-4e246d4f56e4.png)

## Sekian, Terima kasih
