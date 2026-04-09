# <h1 align="center">Laporan Praktikum Modul 3</h1>
<p align="center">Muhammad Syifa Ramadhani - 10908250083</p>

## Unguided 

### 1. 
Minggu ini, mahasiswa Fakultas Informatika mendapatkan tugas dari mata kuliah matematika diskrit untuk mempelajari kombinasi dan permutasi.

```go
package main

import "fmt"

func faktorial(n int) int {
	hasil := 1
	for i := 2; i <= n; i++ {
		hasil = hasil * i
	}
	return hasil
}
func permutasi(n, r int) int {
	return faktorial(n) / faktorial(n-r)
}
func kombinasi(n, r int) int {
	return faktorial(n) / (faktorial(r) * faktorial(n-r))
}
func main() {
	var a, b, c, d int
	fmt.Scan(&a, &b, &c, &d)
	fmt.Println(permutasi(a, c), kombinasi(a, c))
	fmt.Println(permutasi(b, d), kombinasi(b, d))
}
```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul3/Output/Output1.png)

**Penjelasan:**  
Program ini digunakan untuk melakukan perhitungan permutasi dan kombinasi berdasarkan nilai yang dimasukkan oleh pengguna. Perhitungan diawali dengan fungsi `faktorial` yang bertugas menghitung nilai faktorial suatu bilangan menggunakan perulangan.
Selanjutnya, fungsi `permutasi` memanfaatkan hasil faktorial untuk menghitung banyaknya susunan yang mungkin dengan rumus n!/(n−r)!, sedangkan fungsi `kombinasi` digunakan untuk menghitung banyaknya pilihan dengan rumus n!/(r!(n−r)!).
Pada bagian utama program, pengguna diminta memasukkan empat buah bilangan. Program kemudian menghitung dan menampilkan hasil permutasi serta kombinasi dari dua pasang bilangan tersebut.


'''
### 2. Diberikan tiga buah fungsi matematika yaitu f (x) = x^2, g (x) = x − 2 dan h (x) = x + 1. Fungsi komposisi (fogoh)(x) artinya adalah f(g(h(x))). Tuliskan f(x), g(x) dan h(x) dalam bentuk function.
#### soal2.go

```go
package main

import "fmt"

func f(x int) int {
	return x * x
}
func g(x int) int {
	return x - 2
}
func h(x int) int {
	return x + 1
}
func main() {
	var a, b, c int
	fmt.Scan(&a, &b, &c)
	hasil1 := f(g(h(a)))
	hasil2 := g(h(f(b)))
	hasil3 := h(f(g(c)))

	fmt.Println(hasil1)
	fmt.Println(hasil2)
	fmt.Println(hasil3)
}

```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul3/Output/Output2.png)

**Penjelasan:**  
Program ini mengimplementasikan beberapa fungsi matematika sederhana dan menggabungkannya dalam bentuk komposisi fungsi. Terdapat tiga fungsi utama, yaitu f(x) = x², g(x) = x − 2, dan h(x) = x + 1.
Program menerima tiga buah input dari pengguna, kemudian setiap nilai akan diproses menggunakan kombinasi fungsi yang berbeda, seperti f(g(h(x))), g(h(f(x))), dan h(f(g(x))).
Hasil dari masing-masing proses tersebut kemudian ditampilkan, sehingga pengguna dapat melihat hasil dari berbagai komposisi fungsi yang telah diterapkan.


'''
### 3. [Lingkaran] Suatu lingkaran didefinisikan dengan koordinat titik pusat (cx, cy) dengan radius r. Apabila diberikan dua buah lingkaran, maka tentukan posisi sebuah titik sembarang (x, y) berdasarkan dua lingkaran tersebut.
#### soal3.go

```go
package main

import (
	"fmt"
	"math"
)

func jarak(a, b, c, d float64) float64 {
	return math.Sqrt((a-c)*(a-c) + (b-d)*(b-d))
}
func didalam(cx, cy, r, x, y float64) bool {
	return jarak(cx, cy, x, y) <= r
}
func main() {
	var cx1, cy1, r1, cx2, cy2, r2, x, y float64

	fmt.Scanln(&cx1, &cy1, &r1)
	fmt.Scanln(&cx2, &cy2, &r2)
	fmt.Scanln(&x, &y)

	in1 := didalam(cx1, cy1, r1, x, y)
	in2 := didalam(cx2, cy2, r2, x, y)

	if in1 && in2 {
		fmt.Println("Titik didalam lingkaran 1 dan 2")
	} else if in1 {
		fmt.Println("Titik didalam lingkaran 1")
	} else if in2 {
		fmt.Println("Titik didalam lingkaran 2")
	} else {
		fmt.Println("Titik diluar lingkaran 1 dan 2")
	}
}

```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul3/Output/Output3.png)

**Penjelasan:**  
Program ini digunakan untuk menentukan posisi suatu titik terhadap dua buah lingkaran. Setiap lingkaran didefinisikan oleh titik pusat dan jari-jari.
Fungsi `jarak` digunakan untuk menghitung jarak antara dua titik dengan menggunakan rumus jarak Euclidean. Selanjutnya, fungsi `didalam` akan mengecek apakah suatu titik berada di dalam lingkaran dengan membandingkan jarak titik terhadap pusat lingkaran dengan panjang jari-jarinya.Pada bagian utama, program membaca data dua lingkaran dan satu titik. Berdasarkan hasil pengecekan, program akan menentukan apakah titik tersebut berada di dalam salah satu lingkaran, di dalam keduanya, atau di luar kedua lingkaran.
