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

[penjelasan]
Program ini bertujuan untuk menampilkan deret indeks dari 0 hingga n serta deret bilangan Fibonacci hingga suku ke-n dengan menggunakan bahasa pemrograman Go. Nilai n diinput oleh pengguna, kemudian program mencetak indeks menggunakan perulangan. Untuk menghitung bilangan Fibonacci, digunakan fungsi rekursif, di mana jika n ≤ 1 maka nilai dikembalikan langsung, sedangkan jika n > 1 maka dihitung sebagai penjumlahan dua suku sebelumnya, yaitu Fibonacci(n-1) + Fibonacci(n-2).


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

[penjelasan]
Program ini bertujuan untuk menampilkan pola bintang berbentuk segitiga dengan jumlah baris sesuai nilai n yang diinput oleh pengguna. Fungsi sangbintang menggunakan konsep rekursi, di mana jika n sama dengan 0 maka fungsi berhenti (basis rekursi), sedangkan jika n lebih dari 0 maka fungsi akan memanggil dirinya sendiri dengan nilai n-1 terlebih dahulu. Setelah pemanggilan rekursif selesai, program mencetak n buah karakter "*" pada satu baris menggunakan perulangan, sehingga setiap baris memiliki jumlah bintang yang bertambah secara bertahap dari 1 hingga n. Dengan cara ini, pola yang dihasilkan akan berbentuk segitiga siku-siku yang tersusun dari atas ke bawah.
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

[penjelasan]
Program ini bertujuan untuk menampilkan semua faktor dari suatu bilangan n yang diinput oleh pengguna dengan menggunakan pendekatan rekursif. Fungsi faktor(n, i) bekerja dengan memeriksa setiap bilangan i mulai dari 1 hingga n, di mana jika i lebih besar dari n maka proses dihentikan (basis rekursi). Pada setiap langkah, program mengecek apakah n habis dibagi i (n % i == 0), dan jika iya maka nilai i dicetak sebagai faktor dari n. Setelah itu, fungsi memanggil dirinya sendiri dengan nilai i+1 untuk melanjutkan pengecekan hingga seluruh kemungkinan faktor diperiksa. Dengan cara ini, semua faktor dari n akan ditampilkan secara berurutan.

'''
