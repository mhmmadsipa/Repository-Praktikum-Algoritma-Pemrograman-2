# <h1 align="center">Laporan Praktikum Modul 2</h1>
<p align="center">Muhammad Syifa Ramadhani - 10908250083</p>

## Unguided 

### 1. Telusuri program berikut dengan cara mengkompilasi dan mengeksekusi program. Silakan masukan data yang sesuai sebanyak yang diminta program. Perhatikan keluaran yang diperoleh. Coba terangkan apa sebenarnya yang dilakukan program tersebut?

#### soal1.go

```go
package main
import "fmt"

func main() {
	var (
		satu, dua, tiga string
		temp string
	)
	fmt.Print("Masukan input string: ")
	fmt.Scanln(&satu)
	fmt.Print("Masukan input string: ")
	fmt.Scanln(&dua)
	fmt.Print("Masukan input string: ")
	fmt.Scanln(&tiga)
	fmt.Println("Output awal = " + satu + " " + dua + " " + tiga)
	temp = satu
	satu = dua
	dua = tiga
	tiga = temp
	fmt.Println("Output akhir = " + satu + " " + dua + " " + tiga)
}
```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul2/output/Output1.png)

**Penjelasan:**
Program ini digunakan untuk menerima tiga buah data bertipe string dari pengguna. Setelah semua data dimasukkan, program akan menampilkan urutan awal sesuai input.


'''
### 2. Siswa kelas IPA di salah satu sekolah menengah atas di Indonesia sedang mengadakan praktikum kimia. Di setiap percobaan akan menggunakan 4 tabung reaksi, yang mana susunan warna cairan di setiap tabung akan menentukan hasil percobaan. Siswa diminta untuk mencatat hasil percobaan tersebut. Percobaan dikatakan berhasil apabila susunan warna zat cair pada gelas 1 hingga gelas 4 secara berturutan adalah ‘merah’, ‘kuning’, ‘hijau’, dan ‘ungu’ selama 5 kali percobaan berulang. Buatlah sebuah program yang menerima input berupa warna dari ke 4 gelas reaksi sebanyak 5 kali percobaan. Kemudian program akan menampilkan true apabila urutan warna sesuai dengan informasi yang diberikan pada paragraf sebelumnya, dan false untuk urutan warna lainnya.
#### soal2.go

```go
package main
import "fmt"

func main() {
	var a, b, c, d string
	berhasil := true
	for i := 1; i <= 5; i++ {
		fmt.Print("percobaan ", i, ": ")
		fmt.Scan(&a, &b, &c, &d)
		if !(a == "merah" && b == "kuning" && c == "hijau" && d == "ungu") {
			berhasil = false
		}
	}
	if berhasil {
		fmt.Print("BERHASIL : true")
	} else {
		fmt.Print("BERHASIL : false")
	}
}
```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul2/output/Output2.png)

**Penjelasan:**
Program ini bertujuan untuk mengevaluasi hasil percobaan berdasarkan urutan warna yang dimasukkan pengguna. Terdapat lima kali percobaan yang harus dilakukan.
Pada setiap percobaan, program akan membaca empat warna. Jika urutan warna tidak sesuai dengan ketentuan (merah, kuning, hijau, ungu), maka status keberhasilan akan berubah menjadi salah.


'''
### 3. PT POS membutuhkan aplikasi perhitungan biaya kirim berdasarkan berat parsel. Maka, buatlah program BiayaPos untuk menghitung biaya pengiriman tersebut dengan ketentuan sebagai berikut! Dari berat parsel (dalam gram), harus dihitung total berat dalam kg dan sisanya (dalam gram). Biaya jasa pengiriman adalah Rp. 10.000,- per kg. Jika sisa berat tidak kurang dari 500 gram, maka tambahan biaya kirim hanya Rp. 5,- per gram saja. Tetapi jika kurang dari 500 gram, maka tambahan biaya akan dibebankan sebesar Rp. 15,- per gram. Sisa berat (yang kurang dari 1kg) digratiskan biayanya apabila total berat ternyata lebih dari 10kg.
#### soal3.go

```go
package main
import "fmt"

func main() {
	var parsel, biaya, detail, total int

	fmt.Print("Berat parsel dalam gram: ")
	fmt.Scan(&parsel)

	kg := parsel / 1000
	gr := parsel % (kg * 1000)
	biaya = kg * 10000

	fmt.Println("Detail berat:", kg, "kg", "+", gr, "gr")

	if kg > 10 {
		detail = gr * 5
		total = biaya
	} else if gr >= 500 {
		detail = gr * 5
		total = biaya + detail
	} else {
		detail = gr * 15
		total = biaya + detail
	}

	fmt.Println("detail biaya: ", "Rp.", biaya, " + Rp.", detail)
	fmt.Print("Total biaya: Rp.", total)
}
```
### Output Unguided :

##### Output 
![Output1](https://github.com/mhmmadsipa/Repository-Praktikum-Algoritma-Pemrograman-2/blob/main/Modul2/output/Output3.png)

**Penjelasan:**
Program ini digunakan untuk menghitung total biaya pengiriman berdasarkan berat parsel yang dimasukkan dalam satuan gram. Berat tersebut kemudian dikonversi menjadi kilogram dan sisa gram.
Biaya utama dihitung dari jumlah kilogram dengan tarif tertentu. Sisa berat dalam gram akan dikenakan biaya tambahan dengan ketentuan berbeda tergantung jumlahnya.
