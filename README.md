# Sistem Persamaan Linier, Determinan, dan Aplikasinya
# Algeo01-20023
Kelompok BONEK
* 13520023 - Ahmad Alfani Handoyo
* 13520094 - Saul Sayers
* 13520151 - Rizky Ramadhana P. K.
## Menjalankan Program
Pertama-tama masuk ke folder '/src' lalu compile file .java dengan command
```javac *.java```
Hasil compile program ini ditampung pada folder '/bin'. Untuk menjalankan program, masuk ke folder '/bin' lalu jalankan command
```java Main```
dimana Main adalah nama class utama di mana progam berada.
## Menu Utama
Setelah menjalankan program, akan ditampilkan menu seperti berikut
```
------------------------------------------------------
Selamat datang di program matriks kelompok 21 BONEK 
------------------------------------------------------ 
1. Sistem Persamaan Linear     
2. Determinan Matriks          
3. Matrix Balikan              
4. Interpolasi Polinom       
5. Regresi Linear Berganda  
6. CLOSE PROGRAM            
Ketik menu yang ingin dipilih:
```
Masukkan opsi yang ingin dijalankan berupa sebuah angka di antara 1 sampai 6 (inklusif)
## Sistem Persamaan Linear
Apabila dipilih menu 1, maka akan terdapat beberapa pilihan kembali. Masing-masing pilihan berkaitan dengan metode penyelesaian sistem persamaan linear yang akan digunakan.
```
-------------------------------------------------------
1. Metode eliminasi Gauss
2. Metode eliminasi Gauss-Jordan
3. Metode matriks balikan
4. Kaidah Cramer
Masukkan pilihan anda:
```
### Metode Eliminasi Gauss
Mula-mula akan diminta matriks *augmented* dari sistem persamaan linear yang akan diselesaikan. Misal, sebuah sistem persamaan linear terdiri dari tiga persamaan di bawah ini
> x+y+z=10;
> 2x+y+z=12;
> x+2y+z=13

Maka matriks *augmented* nya adalah <br>
1 1 1 10 <br>
2 1 1 12 <br>
1 2 1 13 <br>

Sehingga, untuk menyelesaikan sistem persamaan linear tersebut pengguna harus berinteraksi dengan program seperti berikut (angka setelah tanda ':' adalah input dari pengguna)

```
Ketik 1 untuk menambah matriks by input user
Ketik 2 untuk input matriks dari file txt
Masukkan sub-pilihan anda: 1
Masukkan baris matriksnya: 3
Masukkan kolom matriksnya: 4
Masukkan nilai untuk baris ke-1 kolom ke-1: 1
Masukkan nilai untuk baris ke-1 kolom ke-2: 1
Masukkan nilai untuk baris ke-1 kolom ke-3: 1
Masukkan nilai untuk baris ke-1 kolom ke-4: 10
Masukkan nilai untuk baris ke-2 kolom ke-1: 2
Masukkan nilai untuk baris ke-2 kolom ke-2: 1
Masukkan nilai untuk baris ke-2 kolom ke-3: 1
Masukkan nilai untuk baris ke-2 kolom ke-4: 12
Masukkan nilai untuk baris ke-3 kolom ke-1: 1 
Masukkan nilai untuk baris ke-3 kolom ke-2: 2
Masukkan nilai untuk baris ke-3 kolom ke-3: 1
Masukkan nilai untuk baris ke-3 kolom ke-4: 13 
```
Program akan menjalankan eliminasi Gauss pada matriks *augmented* tersebut. Proses eliminasi akan berjalan seperti di bawah ini
```
Matrix awal
1.00 1.00 1.00 10.00
2.00 1.00 1.00 12.00
1.00 2.00 1.00 13.00
Tukar baris ke-1 dan baris ke-2
2.00 1.00 1.00 12.00
1.00 1.00 1.00 10.00
1.00 2.00 1.00 13.00
Baris ke-2 dikurangi baris ke-1 dikali 0.50
2.00 1.00 1.00 12.00
0.00 0.50 0.50 4.00
1.00 2.00 1.00 13.00
Baris ke-3 dikurangi baris ke-1 dikali 0.50
2.00 1.00 1.00 12.00
0.00 0.50 0.50 4.00
0.00 1.50 0.50 7.00
Baris ke-3 dikurangi baris ke-2 dikali 3.00
2.00 1.00 1.00 12.00
0.00 0.50 0.50 4.00
0.00 0.00 -1.00 -5.00
Baris ke-1 dibagi dengan 2.00
1.00 0.50 0.50 6.00
0.00 0.50 0.50 4.00
0.00 0.00 -1.00 -5.00
Baris ke-2 dibagi dengan 0.50
1.00 0.50 0.50 6.00
0.00 1.00 1.00 8.00
0.00 0.00 -1.00 -5.00
Baris ke-3 dibagi dengan -1.00
1.00 0.50 0.50 6.00
0.00 1.00 1.00 8.00
-0.00 -0.00 1.00 5.00
```
Di akhir proses eliminasi, akan dihasilkan sebuah matriks eselon baris. Lalu program akan melakukan substitusi balik dan menghasilkan solusi seperti berikut
```
Penyelesaian persamaan tersebut adalah
[2.0, 3.0, 5.0] 
```
### Metode Eliminasi Gauss Jordan
Pada metode eliminasi Gauss Jordan, langkah-langkah yang dilakukan mirip dengan metode eliminasi Gauss. Hanya saja, pada akhir proses eliminasi akan dihasilkan matriks eselon baris tereduksi. Berikut adalah simulasi proses eliminasi sebuah matriks *augmented* menuju sebuah matriks eselon baris tereduksi. (Studi kasus 1a)
```
Matrix awal
1.00 1.00 -1.00 -1.00 1.00
2.00 5.00 -7.00 -5.00 -2.00
2.00 -1.00 1.00 3.00 4.00
5.00 2.00 -4.00 2.00 6.00
Tukar baris ke-1 dan baris ke-2
2.00 5.00 -7.00 -5.00 -2.00
1.00 1.00 -1.00 -1.00 1.00
2.00 -1.00 1.00 3.00 4.00
5.00 2.00 -4.00 2.00 6.00
Baris ke-2 dikurangi baris ke-1 dikali 0.50
2.00 5.00 -7.00 -5.00 -2.00
0.00 -1.50 2.50 1.50 2.00
2.00 -1.00 1.00 3.00 4.00
5.00 2.00 -4.00 2.00 6.00

(... tidak ditampilkan pada simulasi ini untuk mempersingkat ...)

Baris ke-3 dibagi dengan 0.50
1.00 0.00 0.00 0.67 0.00
-0.00 1.00 -0.00 -2.67 -0.00
0.00 0.00 1.00 -1.00 0.00
0.00 0.00 0.00 0.00 1.00
Baris ke-4 dibagi dengan 1.00
1.00 0.00 0.00 0.67 0.00
-0.00 1.00 -0.00 -2.67 -0.00
0.00 0.00 1.00 -1.00 0.00
0.00 0.00 0.00 0.00 1.00 
```
Perlu diperhatikan bahwa tidak semua sistem persamaan linear akan memiliki solusi tunggal. Pada contoh di atas, tidak ada solusi yang memenuhi sistem persamaan tersebut. Sehingga program akan memberi tampilan sebagai berikut
```
Tidak memiliki solusi
```
### Metode Matriks Balikan
Dengan metode ini, matriks akan disajikan dalam model *Ax = B* 
Misal, sebuah sistem persamaan linear terdiri dari empat persamaan di bawah ini
> a+b-c-d=1;
> 2a+5b-7c-5d=-2;
> 2a-b+c+3d=4;
> 5a+2b-4c+2d=6

Sehingga, untuk menyelesaikan sistem persamaan linear tersebut pengguna 
harus berinteraksi dengan program. Pengguna akan diminta untuk mengisi matriks A terlebih dahulu, kemudian mengisi matriks B seperti berikut (angka setelah tanda ':' adalah input dari pengguna)

```
Menggunakan metode matriks balikan, bentuk matriks Ax = B
Silahkan menginput matriks A:
Ketik 1 untuk menambah matriks by input user
Ketik 2 untuk input matriks dari file txt
Masukkan sub-pilihan anda: 1
Masukkan baris matriksnya: 4
Masukkan kolom matriksnya: 4
Masukkan nilai untuk baris ke-1 kolom ke-1: 1
Masukkan nilai untuk baris ke-1 kolom ke-2: 1
Masukkan nilai untuk baris ke-1 kolom ke-3: -1
Masukkan nilai untuk baris ke-1 kolom ke-4: -1
Masukkan nilai untuk baris ke-2 kolom ke-1: 2
Masukkan nilai untuk baris ke-2 kolom ke-2: 5
Masukkan nilai untuk baris ke-2 kolom ke-3: -7
Masukkan nilai untuk baris ke-2 kolom ke-4: -5
Masukkan nilai untuk baris ke-3 kolom ke-1: 2
Masukkan nilai untuk baris ke-3 kolom ke-2: -1
Masukkan nilai untuk baris ke-3 kolom ke-3: 1
Masukkan nilai untuk baris ke-3 kolom ke-4: 3
Masukkan nilai untuk baris ke-4 kolom ke-1: 5
Masukkan nilai untuk baris ke-4 kolom ke-2: 2
Masukkan nilai untuk baris ke-4 kolom ke-3: -4
Masukkan nilai untuk baris ke-4 kolom ke-4: 2
Determinan matriks A adalah 0 sehingga tidak bisa menggunakan metode ini karena tidak ada inversnya.
Akan dikembalikan ke menu utama
```

Contoh studi kasus yang dipilih memiliki determinan Matriks A yang bernilai 0.
Dengan demikian, metode balikan matriks tidak dapat digunakan karena Matriks A tidak memiliki invers,<br>
sehingga pengguna tidak diminta untuk mengisi matriks B.

### Metode Cramer
Dengan metode ini, matriks akan disajikan dalam model *Ax = B* 
Misal, sebuah sistem persamaan linear terdiri dari empat persamaan di bawah 
ini
> a+b-c-d=1;
> 2a+5b-7c-5d=-2;
> 2a-b+c+3d=4;
> 5a+2b-4c+2d=6

Sehingga, untuk menyelesaikan sistem persamaan linear tersebut pengguna 
harus berinteraksi dengan program. Pengguna akan diminta untuk mengisi 
matriks A terlebih dahulu, kemudian mengisi matriks B seperti berikut 
(angka setelah tanda ':' adalah input dari pengguna)

```
Menggunakan metode Cramer, bentuk matriks Ax = B
Silahkan menginput matriks A:
Ketik 1 untuk menambah matriks by input user
Ketik 2 untuk input matriks dari file txt
Masukkan sub-pilihan anda: 1
Masukkan baris matriksnya: 4
Masukkan kolom matriksnya: 5
Masukkan nilai untuk baris ke-1 kolom ke-1: 1
Masukkan nilai untuk baris ke-1 kolom ke-2: -1
Masukkan nilai untuk baris ke-1 kolom ke-3: 0
Masukkan nilai untuk baris ke-1 kolom ke-4: 0
Masukkan nilai untuk baris ke-1 kolom ke-5: 1
Masukkan nilai untuk baris ke-2 kolom ke-1: 1
Masukkan nilai untuk baris ke-2 kolom ke-2: 1
Masukkan nilai untuk baris ke-2 kolom ke-3: 0
Masukkan nilai untuk baris ke-2 kolom ke-4: -3
Masukkan nilai untuk baris ke-2 kolom ke-5: 0
Masukkan nilai untuk baris ke-3 kolom ke-1: 2
Masukkan nilai untuk baris ke-3 kolom ke-2: -1
Masukkan nilai untuk baris ke-3 kolom ke-3: 0
Masukkan nilai untuk baris ke-3 kolom ke-4: 1
Masukkan nilai untuk baris ke-3 kolom ke-5: -1
Masukkan nilai untuk baris ke-4 kolom ke-1: -1
Masukkan nilai untuk baris ke-4 kolom ke-2: 2
Masukkan nilai untuk baris ke-4 kolom ke-3: 0
Masukkan nilai untuk baris ke-4 kolom ke-4: -2
Masukkan nilai untuk baris ke-4 kolom ke-5: -1
Matriks A tidak persegi, tidak bisa menggunakan metode ini.
Akan dikembalikan ke menu utama
```

Contoh studi kasus kami menggunakan Matriks A yang tidak berbentuk persegi <br>
Dengan demikian, metode ini tidak dapat digunakan karena membutuhkan determinan matriks A.
## Determinan Matriks
Apabila dipilih menu 2, maka akan terdapat beberapa pilihan kembali. Masing-masing pilihan berkaitan dengan metode perhitungan determinan yang akan digunakan. <br>
Syarat dari perhitungan determinan adalah matriks yang dimasukkan harus berupa matriks persegi.
```
Ketik 1 untuk menggunakan metode OBE
Ketik 2 untuk menggunakan metode Kofaktor
Masukkan pilihan anda: 
```

Apabila syarat tidak persegi tidak terpenuhi, maka akan terjadi contoh luaran seperti berikut:
```
Masukkan baris matriksnya: 1
Masukkan kolom matriksnya: 3
Masukkan nilai untuk baris ke-1 kolom ke-1: 1
Masukkan nilai untuk baris ke-1 kolom ke-2: 2
Masukkan nilai untuk baris ke-1 kolom ke-3: 3
Matriks bukan persegi, tidak bisa dicari determinannya
```
### Metode OBE
Metode perhitungan determinan ini menggunakan operasi baris elementer.
Matriks akan dioperasikan sehingga berbentuk segitiga atas (elemen matriks bagian bawah diagonal utama merupakan 0 semua).
Apabila matriks sudah berupa segitiga atas dari awal, maka tidak perlu dioperasikan.
Setelah menjadi segitiga atas, maka perhitungan determinan cukup dengan mengalikan seluruh elemen pada diagonal utama.

Pengguna akan diminta untuk menginput matriks yang akan dihitung determinannya seperti berikut:
```
Masukkan baris matriksnya: 3
Masukkan kolom matriksnya: 3
Masukkan nilai untuk baris ke-1 kolom ke-1: 4
Masukkan nilai untuk baris ke-1 kolom ke-2: 2
Masukkan nilai untuk baris ke-1 kolom ke-3: 8
Masukkan nilai untuk baris ke-2 kolom ke-1: 2
Masukkan nilai untuk baris ke-2 kolom ke-2: 1
Masukkan nilai untuk baris ke-2 kolom ke-3: 5
Masukkan nilai untuk baris ke-3 kolom ke-1: 3
Masukkan nilai untuk baris ke-3 kolom ke-2: 2
Masukkan nilai untuk baris ke-3 kolom ke-3: 4
Matrix awal
4.00 2.00 8.00
2.00 1.00 5.00
3.00 2.00 4.00
Baris ke-2 dikurangi baris ke-1 dikali 0.50
4.00 2.00 8.00
0.00 0.00 1.00
3.00 2.00 4.00
Baris ke-3 dikurangi baris ke-1 dikali 0.75
4.00 2.00 8.00
0.00 0.00 1.00
0.00 0.50 -2.00
Tukar baris ke-2 dan baris ke-3
4.00 2.00 8.00
0.00 0.50 -2.00
0.00 0.00 1.00
Baris ke-3 dikurangi baris ke-2 dikali 0.00
4.00 2.00 8.00
0.00 0.50 -2.00
0.00 0.00 1.00
Bentuk matriksnya setelah operasi segitiga adalah:
4.00 2.00 8.00
0.00 0.50 -2.00
0.00 0.00 1.00
Determinan perkalian diagonal utamanya adalah (plus minus bergantung banyaknya operasi swap): -2.0
```
### Metode Kofaktor
Metode perhitungan determinan ini menggunakan minor dan kofaktor pada matriks tersebut.
Perhitungan determinan akan menggunakan elemen pada baris pertama yang masing-masing dikalikan dengan kofaktornya.
Masing - masing kofaktor akan dihitung dengan mencari minornya yang kemudian determinannya akan dihitung pula menggunakan fungsi determinan metode kofaktor itu sendiri (rekursi).

Pengguna akan diminta untuk menginput matriks yang akan dihitung determinannya seperti berikut:
```
Masukkan baris matriksnya: 3
Masukkan kolom matriksnya: 3
Masukkan nilai untuk baris ke-1 kolom ke-1: 2
Masukkan nilai untuk baris ke-1 kolom ke-2: 0
Masukkan nilai untuk baris ke-1 kolom ke-3: 1
Masukkan nilai untuk baris ke-2 kolom ke-1: 3
Masukkan nilai untuk baris ke-2 kolom ke-2: 1
Masukkan nilai untuk baris ke-2 kolom ke-3: 2
Masukkan nilai untuk baris ke-3 kolom ke-1: 4
Masukkan nilai untuk baris ke-3 kolom ke-2: 2
Masukkan nilai untuk baris ke-3 kolom ke-3: 3
Mencari determinan dengan menggunakan kofaktor pada baris pertama.
Determinannya adalah: 2.0*-1.0 + 0.0*-1.0 + 1.0*2.0: 0.0
```
## Matrix Balikan
### Metode OBE
### Metode Adjoint
## Interpolasi Polinom
Pada subprogram ini, akan diterima n buah titik pada bidang dua dimensi (x,y) lalu program akan membuat sebuah polinomial berderajat n-1 yang memiliki n buah konstanta yang harus dicari. Misal, terdapat 7 titik seperti pada tabel berikut (studi kasus 6a)
x|0.1|0.3|0.5|0.7|0.9|1.1|1.3
-|-|-|-|-|-|-|-
f(x)|0.003|0.067|0.148|0.248|0.370|0.518|0.697

Maka titik-titik tersebut harus dimasukkan ke dalam program melalui interaksi sebagai berikut
```
Jumlah titik yang ingin dimasukkan :
7
Masukkan absis titik ke-1
0.1
Masukkan ordinat titik ke-1
0.003
Masukkan absis titik ke-2
0.3
Masukkan ordinat titik ke-2
0.067
Masukkan absis titik ke-3
0.5
Masukkan ordinat titik ke-3
0.148
Masukkan absis titik ke-4
0.7
Masukkan ordinat titik ke-4
0.248
Masukkan absis titik ke-5
0.9
Masukkan ordinat titik ke-5
0.370
Masukkan absis titik ke-6
1.1
Masukkan ordinat titik ke-6
0.518
Masukkan absis titik ke-7
1.3
Masukkan ordinat titik ke-7
0.697
```
Lalu dari kumpulan titik tersebut, program akan menyusun sistem persamaan linear dengan n buah konstanta yang harus dicari dalam bentuk sebuah matriks *augmented*. Proses mengisi matriks *augmented* tidak dibahas dalam simulasi ini. Sebagai contoh, dari tujuh titik-titik di atas akan terbentuk matriks *augmented* seperti di bawah ini.
```
Matrix awal
1.00 0.10 0.01 0.00 0.00 0.00 0.00 0.00
1.00 0.30 0.09 0.03 0.01 0.00 0.00 0.07
1.00 0.50 0.25 0.13 0.06 0.03 0.02 0.15
1.00 0.70 0.49 0.34 0.24 0.17 0.12 0.25
1.00 0.90 0.81 0.73 0.66 0.59 0.53 0.37
1.00 1.10 1.21 1.33 1.46 1.61 1.77 0.52
1.00 1.30 1.69 2.20 2.86 3.71 4.83 0.70
```
Lalu program akan menjalankan proses eliminasi Gauss untuk mendapatkan solusi dari sistem persamaan linear di atas. Pada kasus ini akan didapatkan solusi sebagai berikut
```
Koefisien-koefisien dari polinomial yang bersesuaian, dimulai dari derajat 0 di paling kiri
[-0.022976562500000387, 0.24000000000000693, 0.19739583333329394, 9.985982746837269E-14, 0.026041666666540748, 7.710258574544819E-14, -1.827238296772476E-14] 
```
Kemudian program akan meminta nilai absis yang ingin diinterpolasi menggunakan polinomial yang sudah dibuat. Untuk simulasi ini, akan digunakan nilai 0,2. Program lalu memberi nilai ordinat yang bersesuaian dan menampilkannya di layar.
```
Masukkan nilai ordinat yang ingin diinterpolasi
0.2
Hasil interpolasi adalah : 0.03 
```
## Regresi Linear Berganda
Pada subprogram ini, akan diterima n buah titik dan k buah variabel peubah lalu program akan membuat sebuah persamaan regresi yang memiliki k buah koefisien (untuk tiap variabel peubah, dinotasikan dengan b_k) dengan 1 konstanta (b_0). Contohnya terdapat pada studi kasus 7 yang memiliki 20 titik dan 3 variabel peubah.

Maka titik-titik tersebut harus dimasukkan ke dalam program melalui interaksi sebagai berikut
```
Jumlah variabel peubah yang ingin dimasukkan :
3
Jumlah titik yang ingin dimasukkan :
20
Masukkan nilai dari X11: 72.4
Masukkan nilai dari X21: 76.3
Masukkan nilai dari X31: 29.18
Masukkan nilai dari Y1: 0.9
Masukkan nilai dari X12: 41.6
Masukkan nilai dari X22: 70.3
Masukkan nilai dari X32: 29.35
Masukkan nilai dari Y2: 0.91
Masukkan nilai dari X13: 34.3
Masukkan nilai dari X23: 77.1
Masukkan nilai dari X33: 29.24
Masukkan nilai dari Y3: 0.96
.....(semua titik lain).....
Masukkan nilai dari X120: 54.9
Masukkan nilai dari X220: 70.9
Masukkan nilai dari X320: 29.37
Masukkan nilai dari Y20: 0.95
```

Lalu program akan menyusun semua titik tersebut menjadi sebuah matriks augmented sesuai persamaan *Normal Estimation Equation
for Multiple Linear Regression*.
```
Matrix awal
20.00 863.10 1530.40 587.84 19.42 
863.10 54876.89 67000.09 25283.40 779.48
1530.40 67000.09 117912.32 44976.87 1483.44
587.84 25283.40 44976.87 17278.51 571.12
```

Kemudian, program akan menjalankan proses eliminasi Gauss untuk mendapatkan nilai dari tiap b_k. 
```
nilai dari B yang bersesuaian, dimulai dari derajat 0 di paling kiri
[-3.507778140873786, -0.0026249907458798733, 7.989410472207764E-4, 0.1541550301979756]
```

Kemudian program akan meminta nilai absis dari tiap variabel peubah yang ingin ditaksir menggunakan persamaan regresi yang sudah dibuat. Untuk kasus ini, kita menggunakan studi kasus 7 sebagai berikut
```
Masukkan nilai nilai Xk yang ingin ditaksir fungsinya
Masukkan nilai dari X1: 50
Masukkan nilai dari X2: 76
Masukkan nilai dari X3: 29.3
Hasil taksiran adalah : 0.94
```

