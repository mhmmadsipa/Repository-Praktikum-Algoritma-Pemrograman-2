# <h1 align="center">Laporan Praktikum Modul 5</h1>
<p align="center">Muhammad Syifa Ramadhani - 10908250083</p>

## Unguided 

### 1. 
Deret Fibonacci adalah deret dengan nilai suku ke-0 dan ke-1 yaitu 0 dan 1, sedangkan suku ke-n merupakan hasil penjumlahan dua suku sebelumnya.

```go
package main

import "fmt"

func main() {
	var n int
	fmt.Print("Masukkan jumlah bilangan Fibonacci: ")
	fmt.Scan(&n)

	fmt.Print("n: ")
	for i := 0; i <= n; i++ {
		fmt.Print(i, " ")
	}
	fmt.Println()

	fmt.Print("Sn: ")
	for i := 0; i <= n; i++ {
		fmt.Print(fibonacci(i), " ")
	}
}

func fibonacci(n int) int {
	if n <= 1 {
		return n
	}
	return fibonacci(n-1) + fibonacci(n-2)
}
```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul5/Output/Output1.png)

**Penjelasan:**  
Program ini digunakan untuk menampilkan deret bilangan Fibonacci hingga suku ke-n sesuai dengan nilai yang dimasukkan oleh pengguna. Program terlebih dahulu mencetak indeks bilangan dari 0 sampai n menggunakan perulangan.Perhitungan nilai Fibonacci dilakukan melalui fungsi rekursif. Jika nilai n kurang dari atau sama dengan 1, maka fungsi langsung mengembalikan nilai tersebut. Namun, jika n lebih besar dari 1, maka nilainya diperoleh dari penjumlahan dua nilai sebelumnya, yaitu fibonacci(n-1) dan fibonacci(n-2).
Hasil akhir yang ditampilkan berupa deret indeks dan deret Fibonacci yang bersesuaian.

'''
### 2.Buatlah sebuah program yang digunakan untuk menampilkan pola bintang berikut ini dengan menggunakan fungsi rekursif. N adalah masukan dari user.

```go
package main

import "fmt"

func sangbintang(n int) {
	if n == 0 {
		return
	}
	sangbintang(n - 1)
	for i := 0; i < n; i++ {
		fmt.Print("*")
	}
	fmt.Println()
}
func main() {
	var n int
	fmt.Scan(&n)
	sangbintang(n)
}


```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul5/Output/Output2.png)

**Penjelasan:**  
Program ini bertujuan untuk menampilkan pola bintang berbentuk segitiga berdasarkan nilai input dari pengguna. Proses pembentukan pola dilakukan dengan menggunakan pendekatan rekursif.Fungsi `sangbintang` akan berhenti ketika nilai n sama dengan 0 sebagai kondisi dasar. Jika tidak, fungsi akan memanggil dirinya sendiri dengan nilai n-1 terlebih dahulu. Setelah itu, program mencetak sejumlah karakter "*" sesuai nilai n pada baris tersebut.
Dengan mekanisme ini, jumlah bintang akan bertambah secara bertahap pada setiap baris, sehingga membentuk pola segitiga yang teratur dari atas ke bawah.

'''

### 3. Buatlah program yang mengimplementasikan rekursif untuk menampilkan faktor bilangan dari suatu N, atau bilangan yang apa saja yang habis membagi N.
```go
package main

import "fmt"

func faktor(n, i int) {
	if i > n {
		return
	}
	if n%i == 0 {
		fmt.Printf("%d ", i)
	}
	faktor(n, i+1)
}
func main() {
	var n int
	fmt.Scan(&n)
	faktor(n, 1)
	fmt.Println()
}

```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul5/Output/Output3.png)

**Penjelasan:**  
Program ini digunakan untuk menampilkan seluruh faktor dari suatu bilangan yang dimasukkan oleh pengguna. Proses dilakukan menggunakan metode rekursif dengan bantuan fungsi `faktor`.
Fungsi akan memeriksa setiap bilangan mulai dari 1 hingga n. Jika nilai i melebihi n, maka proses akan dihentikan sebagai kondisi dasar. Pada setiap langkah, program mengecek apakah n habis dibagi oleh i. Jika iya, maka nilai i akan ditampilkan sebagai faktor.
Setelah itu, fungsi akan memanggil dirinya sendiri dengan nilai i yang bertambah satu, hingga seluruh faktor dari bilangan tersebut ditemukan dan ditampilkan.

'''
