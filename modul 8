package main

import "fmt"

type Buku struct {
	ID        string
	Judul     string
	Penulis   string
	Penerbit  string
	Eksemplar int
	Tahun     int
	Rating    int
}

func DaftarkanBuku(pustaka []Buku, n int) {
	for i := 0; i < n; i++ {
		fmt.Scan(
			&pustaka[i].ID,
			&pustaka[i].Judul,
			&pustaka[i].Penulis,
			&pustaka[i].Penerbit,
			&pustaka[i].Eksemplar,
			&pustaka[i].Tahun,
			&pustaka[i].Rating,
		)
	}
}

func CetakTerfavorit(pustaka []Buku, n int) {
	maxIdx := 0

	for i := 1; i < n; i++ {
		if pustaka[i].Rating > pustaka[maxIdx].Rating {
			maxIdx = i
		}
	}

	fmt.Println("Buku Terfavorit:")
	fmt.Println(pustaka[maxIdx].Judul,
		pustaka[maxIdx].Penulis,
		pustaka[maxIdx].Penerbit,
		pustaka[maxIdx].Tahun)
}

func UrutBuku(pustaka []Buku, n int) {
	for i := 1; i < n; i++ {
		temp := pustaka[i]
		j := i - 1

		for j >= 0 && temp.Rating > pustaka[j].Rating {
			pustaka[j+1] = pustaka[j]
			j--
		}

		pustaka[j+1] = temp
	}
}

func Cetak5Terbaru(pustaka []Buku, n int) {
	limit := 5
	if n < 5 {
		limit = n
	}

	fmt.Println("5 Buku Rating Tertinggi:")

	for i := 0; i < limit; i++ {
		fmt.Println(pustaka[i].Judul)
	}
}

func CariBuku(pustaka []Buku, n int, r int) {

	kiri := 0
	kanan := n - 1

	for kiri <= kanan {

		tengah := (kiri + kanan) / 2

		if pustaka[tengah].Rating == r {

			fmt.Println("Data Buku:")
			fmt.Println("Judul :", pustaka[tengah].Judul)
			fmt.Println("Penulis :", pustaka[tengah].Penulis)
			fmt.Println("Penerbit :", pustaka[tengah].Penerbit)
			fmt.Println("Tahun :", pustaka[tengah].Tahun)
			fmt.Println("Eksemplar :", pustaka[tengah].Eksemplar)
			fmt.Println("Rating :", pustaka[tengah].Rating)
			return

		} else if r > pustaka[tengah].Rating {

			kanan = tengah - 1

		} else {

			kiri = tengah + 1
		}
	}

	fmt.Println("Tidak ada buku dengan rating seperti itu")
}

func main() {

	var n int

	fmt.Scan(&n)

	pustaka := make([]Buku, n)

	DaftarkanBuku(pustaka, n)

	CetakTerfavorit(pustaka, n)

	UrutBuku(pustaka, n)

	Cetak5Terbaru(pustaka, n)

	var ratingCari int

	fmt.Scan(&ratingCari)

	CariBuku(pustaka, n, ratingCari)
}
