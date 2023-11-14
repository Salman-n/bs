# SQL Fungsi Agregasi 
## Pengertian Fungsi Agregasi :smile:

!!! Info

    Fungsi Agregasi adalah sebuah fungsi yang akan menghasilkan sebuah value baru dari hasil perhitungan beberapa kolom pada sebuah query, maksudnya bahwa fungsi ini digunakan untuk menampilkan nilai-nilai atribut yang ada dalam tabel, sering pula ada kebutuhan untuk menampilkan data-data agregasi sehingga kita bisa mengembalikan semua data dari kolom tertentu, Anda dapat mengembalikan satu nilai dari kolom tertentu. Terdapat beberapa jenis fungsi agregasi SQL yang dapat kita gunakan, di antaranya:
    
    * COUNT
    * SUM
    * AVG
    * MIN & MAX

## Berikut Tabel Jenis Fungsi Agregasi 


| Fungsi  | Kegunaan | Sintaks                                |
|---------|--------- |---------|
| COUNT() | Mengembalikan jumlah total baris yang cocok dengan kueri. Maksudnya, fungsi yang akan menghitung jumlah value dari  sebuah kolom dari sebuah tabel. Fungsi COUNT ini dapat juga digabungkan dengan DISTINCT untuk menampilkan value yang unik dari sebuah kolom sehingga apabila ada value yang sama dari kolom tersebut atau NULL tidak akan dihitung. Fungsi COUNT dapat digunakan untuk kolom dengan tipe data string ataupun numerik. | {== SELECT COUNT (Nama_Kolom) FROM (Nama Tabel) ==}  atau  {== SELECT COUNT (DISTINCT Nama_Kolom) FROM Nama_Tabel==} |
| SUM()   | Mengembalikan jumlah nilai untuk semua baris dalam kolom yang dipilih. Fungsi ini hanya dapat digunakan apabila tipe data dari kolom tersebut adalah numerik (integer, biginteger atau float). Fungsi ini dituliskan dengan menuliskan SUM pada kolom yang akan dihitung. Fungsi SUM juga dapat digabungkan dengan klausa GROUP BY dan HAVING seperti yang telah dijelaskan di awal.    | {== SELECT SUM (Nama_Kolom) FROM Nama_Tabel ==}  atau  {== SELECT column1, column2, SUM(NAMA_KOLOM) AS NAMA_KOLOM_ALIASNYA FROM NAMA_TABEL GROUP BY column1, column2 HAVING condition; ==}    |
| AVG()   | Mengembalikan nilai mean-rata-rata dari semua nilai di kolom yang dipilih. Fungsi ini sama dengan metode mean atau nilai rata-rata pada perhitungan matematika dan statistika. Sama seperti SUM, fungsi AVG dapat juga digunakan dengan menambahkan GROUP BY serta HAVING pada syntax query-nya.  | {== SELECT AVG (Nama_kolom) FROM Nama_Tabel; ==}  atau  {== SELECT column1, column2, AVG(NAMA_KOLOM) AS NAMA_KOLOM_ALIASNYA FROM NAMA_TABEL GROUP BY column1, column2 HAVING condition; ==}    |
| MIN()   | Mengembalikan nilai terkecil di kolom yang dipilih. Fungsi ini juga bisa menggunakan HAVING atau GROUP BY.    | {== SELECT MIN(NAMA_KOLOM) from NAMA_TABEL ==} atau {== SELECT MIN(NAMA_KOLOM) AS NAMA_KOLOM_ALIASNYA from NAMA_TABEL GROUP BY condition ==}    |
| MAX()   | Mengembalikan nilai terbesar di kolom yang dipilih. Fungsi ini juga bisa menggunakan HAVING atau GROUP BY.    | {== SELECT MAX(NAMA_KOLOM) from NAMA_TABEL ==} atau {== SELECT MAX(NAMA_KOLOM) AS NAMA_KOLOM_ALIASNYA from NAMA_TABEL GROUP BY condition ==}   |

# Contoh Penerapan masing-masing SQL Fungsi Agregasi
!!! note ""
    Contoh kita akan membuat sebuah database 'HP' dengan terdiri 1 Tabel yaitu Tabel 'data_pembelian' dengan terdiri atas 5 Kolom diantaranya ada kolom 'id_ord', 'nama_pembeli', 'id_hp', 'jmlh_ord'.
    kita buat databasenya dulu bernama HP, setelah itu kita gunakan databasenya menggunakan perintah USE


![jkjk](https://i.ibb.co/ZxQgD3s/image.png)

!!! note ""
    Lalu, kita buat table baru bernama 'data_pembelian' dengan kolom nya terdiri dari 'id_ord', 'nama_pembeli', 'id_hp', 'jmlh_ord'
    Untuk tipe datanya id_ord, id_hp, dan jmlh_ord itu menggunakan tipe data INT atau integer, sedangkan nama_pembeli menggunakan VARCHAR untuk tutorialnya sebagai berikut.

![kokok](https://i.ibb.co/ygw7Jbh/image.png)


!!! note ""
    Lalu, kita isi datanya menggunakan perintah INSERT INTO sebagai berikut.


![kokoko](https://i.ibb.co/yPvLfJp/image.png)


!!! note ""
    Kita akan hitung data jmlh_ord menggunakan SUM()
    Untuk menghitung jumlah baris pada nama_pembeli menggunakan COUNT()


![huhuhu](https://images2.imgbox.com/9b/79/reJRvJ9G_o.png)

!!! note ""
    Karena terdapat duplikasi data pada kolom 'id_hp' maka kita bisa hitung data barisnya menggunakan COUNT dengan DISTINCT seperti ini.


![huhuhu](https://images2.imgbox.com/1c/23/UTaSrdnv_o.png)


!!! note ""
    Kita bisa mengurutkan nilai terbesar dan terkecil dari kolom 'jmlh_order'


![huhuhu](https://images2.imgbox.com/05/2d/9VrT7WyP_o.png)

# SQL DISTINCT 
!!! Info 

    Pernyataan SELECT DISTINCT digunakan untuk mengembalikan hanya nilai yang berbeda. Di dalam sebuah tabel, kolom sering berisi banyak nilai duplikat, dan terkadang Anda hanya ingin membuat daftar perbedaan nilai yang berbeda. Pernyataan SELECT DISTINCT digunakan untuk mengembalikan hanya nilai yang berbeda.
    Sintaksnya Sebagai Berikut :
    {== SELECT DISTINCT kolom1, kolom2, ...
    FROM nama_tabel; ==}

## Berikut Penggunaan SQL DISTINCT
!!! note ""
    Kita menggunakan kata kunci DISTINCT dengan pernyataan SELECT ketika ada kebutuhan untuk menghindari nilai duplikat yang ada dalam kolom/tabel tertentu. Ketika kita menggunakan kata kunci DISTINCT, pernyataan SELECT hanya mengembalikan record unik yang tersedia dalam tabel.    
    Kata Kunci SQL DISTINCT dapat dikaitkan dengan pernyataan SELECT untuk mengambil catatan unik dari satu atau beberapa kolom/tabel.

Sintaks
Sintaks dasar kata kunci SQL DISTINCT adalah sebagai berikut -

```SQL
    SELECT DISTINCT kolom1, kolom2, ..... kolomN 
    FROM nama_tabel;
```

!!! note ""
    Di mana, column1, column2, dst. adalah kolom-kolom yang ingin kita ambil nilai unik atau berbeda; dan table_name mewakili nama tabel yang berisi data.

## Kata Kunci DISTINCT pada Kolom Tunggal
!!! note ""
    Kita dapat menggunakan kata kunci DISTINCT pada kolom tunggal untuk mengambil semua nilai unik dalam kolom tersebut, yaitu dengan menghilangkan duplikatnya. Hal ini sering digunakan untuk mendapatkan ringkasan dari nilai-nilai yang berbeda dalam kolom tertentu atau untuk menghilangkan data yang berlebihan.
    Contoh
    Asumsikan kita telah membuat sebuah tabel dengan nama PELANGGAN pada database MySQL dengan menggunakan pernyataan CREATE TABLE seperti yang ditunjukkan di bawah ini -
```sql
CREATE TABLE CUSTOMERS (
   ID INT NOT NULL,
   NAME VARCHAR (20) NOT NULL,
   AGE INT NOT NULL,
   ADDRESS VARCHAR (25),
   SALARY DECIMAL (18, 2),
   PRIMARY KEY(ID)
);
```
!!! note ""
   Kueri berikut menyisipkan nilai ke dalam tabel ini menggunakan pernyataan INSERT -
```SQL
MASUKKAN KE DALAM NILAI PELANGGAN
INSERT INTO CUSTOMERS(ID, NAME, UMUR, ALAMAT, GAJI) VALUES
(1, 'Ramesh', 32, 'Ahmedabad', 2000.00),
(2, 'Khilan', 25, 'Delhi', 1500.00),
(3, 'Kaushik', 23, 'Kota', 2000.00),
(4, 'Chaitali', 25, 'Mumbai', 6500.00),
(5, 'Hardik', 27, 'Bhopal', 8500.00),
(6, 'Komal', 22, 'Hyderabad', 4500.00),
(7, 'Muffy', 24, 'Indore', 10000.00);
```
   Tabel yang diperoleh adalah seperti yang ditunjukkan di bawah ini -
   ![GMBR](https://i.ibb.co/K6W5kS6/image.png)

!!! note ""
    Sekarang, mari kita gunakan kata kunci DISTINCT dengan kueri SELECT di atas dan kemudian lihat hasilnya -
```sql
    SELECT DISTINCT SALARY FROM CUSTOMERS ORDER BY SALARY;
```
    PILIH GAJI YANG BERBEDA DARI URUTAN PELANGGAN BERDASARKAN GAJI;
    Hasilnya 
    Ini akan menghasilkan hasil sebagai berikut di mana kita tidak memiliki entri duplikat jadi bersifat UNIK

![uwaww](https://i.ibb.co/jGR7YJw/image.png)


## Kata Kunci DISTINCT pada Beberapa Kolom
!!! note ""
    Kita juga dapat menggunakan kata kunci DISTINCT pada beberapa kolom untuk mengambil semua kombinasi nilai unik di seluruh kolom tersebut. Hal ini sering digunakan untuk mendapatkan ringkasan nilai yang berbeda di beberapa kolom, atau untuk menghilangkan data yang berlebihan.
    Contoh
    Dalam kueri berikut, kami mengambil daftar semua kombinasi unik dari usia dan gaji pelanggan menggunakan kata kunci DISTINCT -
```sql
    SELECT DISTINCT AGE, SALARY FROM CUSTOMERS ORDER BY AGE;
```
    hasilnya
    Meskipun kolom AGE memiliki nilai "25" dalam dua catatan, setiap kombinasi "25" dengan 'gaji' spesifiknya adalah unik, sehingga kedua baris disertakan dalam kumpulan hasil -


![jljkl](https://i.ibb.co/THxGcC7/image.png)

## Kata Kunci DISTINCT dengan Fungsi COUNT()
!!! note ""
    Fungsi COUNT() digunakan untuk mendapatkan jumlah record yang di-retun oleh kueri SELECT. Kita perlu mengoper sebuah ekspresi ke fungsi ini agar kueri SELECT mengembalikan jumlah record yang memenuhi ekspresi yang ditentukan.
    Jika kita mengoper kata kunci DISTINCT ke fungsi COUNT() sebagai ekspresi, fungsi ini akan mengembalikan jumlah nilai unik dalam sebuah kolom tabel. Maka Sintaksnya adalah

```sql
    SELECT COUNT(DISTINCT column_name) 
    FROM nama_tabel WHERE kondisi;
```
!!! note ""  
    Di mana, column_name adalah nama kolom yang ingin kita hitung nilai uniknya; dan table_name adalah nama tabel yang berisi data.
    Contoh
    Dalam kueri berikut, kami mengambil jumlah usia pelanggan yang berbeda -
```sql
SELECT COUNT(DISTINCT AGE) as UniqueAge  FROM CUSTOMERS;
```
!!! note ""
    Hasilnya :
![sdsds](https://i.ibb.co/JFYVqxn/image.png)