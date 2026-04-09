# <h1 align="center">Laporan Praktikum Modul 4</h1>
<p align="center">Muhammad Syifa Ramadhani - 10908250083</p>

## Unguided 

### 1. 
Minggu ini, mahasiswa Fakultas Informatika mendapatkan tugas dari mata kuliah matematika diskrit untuk mempelajari kombinasi dan permutasi.

```go
package main

import "fmt"

func faktorial(n int, hasil *int) {
	*hasil = 1
	for i := 1; i <= n; i++ {
		*hasil *= i
	}
}

func permutasi(n, r int, hasil *int) {
	var nf, nrf int
	faktorial(n, &nf)
	faktorial(n-r, &nrf)
	*hasil = nf / nrf
}

func kombinasi(n, r int, hasil *int) {
	var nf, rf, nrf int
	faktorial(n, &nf)
	faktorial(r, &rf)
	faktorial(n-r, &nrf)
	*hasil = nf / (rf * nrf)
}

func main() {
	var a, b, c, d, p1, c1, p2, c2 int
	fmt.Scan(&a, &b, &c, &d)

	permutasi(a, c, &p1)
	kombinasi(a, c, &c1)
	permutasi(b, d, &p2)
	kombinasi(b, d, &c2)

	fmt.Println(p1, c1)
	fmt.Println(p2, c2)
}

```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul4/output/output1.png)

**Penjelasan:**  
Program ini digunakan untuk menghitung nilai permutasi dan kombinasi dari dua pasangan bilangan yang dimasukkan oleh pengguna. Perhitungan dilakukan dengan bantuan fungsi `faktorial` yang menggunakan perulangan untuk mendapatkan nilai n!.Berbeda dari sebelumnya, hasil perhitungan disimpan melalui parameter pointer, sehingga nilai dapat langsung diubah tanpa perlu menggunakan return. Fungsi `permutasi` dan `kombinasi` memanfaatkan nilai faktorial tersebut untuk menghitung hasil sesuai dengan rumus yang digunakan.
Pada bagian utama program, pengguna memasukkan empat bilangan, kemudian program menghitung permutasi dan kombinasi untuk masing-masing pasangan, lalu menampilkannya dalam dua baris output.


'''
### 2. Kompetisi pemrograman tingkat nasional berlangsung ketat. Setiap peserta diberikan 8 soal yang harus dapat diselesaikan dalam waktu 5 jam saja. Peserta yang berhasil menyelesaikan soal paling banyak dalam waktu paling singkat adalah pemenangnya. Buat program gema yang mencari pemenang dari daftar peserta yang diberikan. Program harus dibuat modular, yaitu dengan membuat prosedur hitungSkor yang mengembalikan total soal dan total skor yang dikerjakan oleh seorang peserta, melalui parameter formal. Pembacaan nama peserta dilakukan di program utama, sedangkan waktu pengerjaan dibaca di dalam prosedur.
#### soal2.go

```go
package main

	import "fmt"

	func hitungSkor(soal *int, skor *int) {
		var time int
		*soal = 0
		*skor = 0
		for i := 0; i < 8; i++ {
			fmt.Scan(&time)
			if time <= 300 {
				*soal++
				*skor += time
			}
		}
	}
	
	func main() {
    var name, winner string
    var soal, skor, jmlsoal, jmlskor int
    jmlskor = 999999

	fmt.Scan(&name)

	for name != "selesai" {
		hitungSkor(&soal, &skor)
		
        if soal > jmlsoal || (soal == jmlsoal && skor < jmlskor) {
            jmlsoal = soal
            jmlskor = skor
            winner = name
    		}
		fmt.Scan(&name)
	}
		
	if winner != "" {
		fmt.Printf("%s %d %d\n", winner, jmlsoal, jmlskor)
		}
	}

```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul4/output/output2.png)

**Penjelasan:**  
Program ini bertujuan untuk menentukan pemenang dalam sebuah kompetisi pemrograman berdasarkan jumlah soal yang berhasil diselesaikan dan total waktu pengerjaan.Program membaca nama peserta satu per satu hingga pengguna memasukkan kata "selesai" sebagai tanda berhenti. Untuk setiap peserta, prosedur `hitungSkor` akan dipanggil untuk membaca waktu pengerjaan dari 8 soal.Jika waktu pengerjaan suatu soal tidak melebihi 300 menit, maka soal tersebut dianggap berhasil dan jumlah soal serta total waktu akan diperbarui. Penggunaan pointer memungkinkan perubahan nilai dilakukan langsung pada variabel asal tanpa pengembalian nilai.
Setelah itu, program membandingkan hasil setiap peserta. Pemenang ditentukan berdasarkan jumlah soal terbanyak, dan jika jumlah soal sama, maka dipilih peserta dengan total waktu paling kecil.
'''
