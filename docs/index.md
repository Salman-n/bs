# SQL JOIN LANJUTAN PART 2 
## Alias untuk Tabel dalam SQL :smile:

    
    Aliases (alias) digunakan untuk memberikan nama alternatif pada tabel atau 
    kolom dalam query SQL. Alias berguna untuk membuat query lebih mudah dibaca 
    dan menghindari ambiguitas ketika ada nama yang sama dalam tabel 
    yang berbeda. 
    
    Alias digunakan dalam berbagai konteks, termasuk penggunaan alias untuk tabel, 
    self-joins, dan penggabungan lebih dari dua tabel.

    Ada beberapa jenis alias dengan SQL Join yang dapat Anda gunakan di SQL:
    1. Nama alias dengan Gabungan SQL untuk tabel.
    2. Nama alias dengan Gabungan SQL untuk kolom tabel.
    
    Meskipun ada beberapa cara berbeda untuk menggunakan alias dalam kueri Anda, 
    sintaksnya serupa untuk semua metode ini. Mari kita lihat sintaks alias.

## Sintaks SQL Alias
Sintaks yang ditunjukkan di bawah ini mencakup alias kolom dan tabel:

=== "ALIAS SQL JOIN UNTUK TABEL DAN KOLOM"

    ```sql
    SELECT
    t1.column_name (AS) new_column_name,
    t2.column_name (AS) other_new_column_name,
    ...
    FROM table1 (AS) t1
    JOIN table2 (AS) t2
    ON t1.column_name = t2.column_name
    …
    ```
## Penerapan Sintaks Alias untuk JOIN SQL Untuk Kolom & Tabel 
Pertama, mari kita lihat nama alias kolom :

=== "ALIAS WITH SQL JOIN FOR COLUMN (Alias dengan SQL JOIN untuk Kolom)"

    ```sql
    t1.column_name (AS) new_column_name,
    t2.column_name (AS) other_new_column_name
    ```
   
!!! note ""

    Kata kunci AS di sini bersifat opsional, jadi bisa digunakan bisa tidak, tetapi kueri akan berperilaku sama persis.

    Alias didefinisikan secara langsung setelah nama kolom (atau kata kunci AS). Dalam kasus ini, alias kita adalah new_column_name / nama_kolom_barunya dan other_new_column_name / nama_kolom_baru_lainnya (sesuai kebutuhan jumlah kolomnya).


Jika ingin menyertakan spasi pada nama kolom baru tadi, apit dengan tanda kutip. Kita dapat memperbarui contoh ini menjadi:
=== "ALIAS WITH SQL JOIN FOR NEW COLUMN (Alias dengan SQL JOIN untuk Kolom Baru)"

    ```sql
    SELECT t1.column_name (AS) 'new column name'
    ```
Tidak menyertakan tanda petik di sini akan menyebabkan kesalahan / {==ERROR==}.

Oke, itu mencakup alias SQL untuk nama kolom baru. Mari kita lihat alias dengan SQL JOIN untuk tabel sebagai berikut.

=== "ALIAS WITH SQL JOIN FOR TABLE (Alias dengan SQL JOIN untuk Tabel)"

    ```sql
    FROM table1 (AS) t1
    JOIN table2 (AS) t2
    ```

!!! note ""
    Seperti sebelumnya, penyertaan kata kunci AS sepenuhnya opsional. Kita mendeklarasikan alias untuk tabel1 sebagai t1. 
    Demikian pula, alias untuk table2 adalah t2.
    Ketika Anda mengganti nama tabel database, Anda harus menggunakan alias tabel dalam kondisi ON, dalam daftar SELECT ketika memilih kolom (jika ada kebutuhan untuk menentukan tabel untuk kolom), dan di bagian lain dari kueri.

Sehingga kita dapat melihat bahwa kita mengikuti aturan ini dengan menyertakan t1 dan t2 dalam klausa SELECT:

=== "ALIAS WITH SQL JOIN FOR NEW TABLE  (Alias dengan SQL JOIN untuk Tabel Baru)"

    ```sql
    SELECT
      t1.column_name (AS) new_column_name,
      t2.column_name (AS) other_new_column_name,
      .....
    ```

## Contoh Penggunaan Alias SQL dengan JOIN, INNER JOIN, LEFT JOIN, RIGHT JOIN, UNION 

Studi kasusnya adalah terdapat database penjualan dengan terdiri atas 3 tabel yaitu {==orders==}, {==order_details==},{==products==}.
Kita buat database dan tabelnya dengan FK dan FKnya terlebih dahulu sebagai berikut sintaksnya !

![Buat databasenya](https://i.ibb.co/tDCwR0Q/Screenshot-2023-10-31-000715.png)
![Buat Tabel Orders](https://i.ibb.co/GsyTY2Y/Screenshot-2023-10-31-000854.png)
![Buat Tabel Products](https://i.ibb.co/z22CZMS/Screenshot-2023-10-31-000912.png)
![Buat Tabel Order_details](https://i.ibb.co/9gzLpV4/Screenshot-2023-10-31-000944.png)

Jika sudah isi datanya sebagai berikut :

![isi data tabel orders](https://i.ibb.co/48tBQ78/Screenshot-2023-10-31-002405.png)
![isi data tabel products](https://i.ibb.co/3z6tNdp/Screenshot-2023-10-31-002414.png)
![isi data tabel order_details](https://i.ibb.co/KN6cxbw/Screenshot-2023-10-31-002421.png)

Lalu Kita akan mengabungkan datanya menggunakan SQL JOIN dengan Alias AS baik INNER JOIN, LEFT JOIN, RIGHT JOIN, Dan sebagainya.

Penggunaan Alias dalam INNER JOIN
- INNER JOIN menghasilkan baris yang memiliki nilai cocok dalam kedua tabel yang digabungkan. untuk sintaksnya sebagai berikut :


=== "Sintaks INNER JOIN"

    ```sql
    Untuk 2 Tabel :
    SELECT nama_kolom(s)
    FROM tabel1,tabel2 
    WHERE tabel1.nama_kolom = tabel2.nama_kolom;
    atau
    SELECT nama_kolom(s)
    FROM tabel1 INNER JOIN tabel2 
    ON tabel1.nama_kolom = tabel2.nama_kolom;
    Untuk 3 Tabel :
    SELECT nama_kolom(s)
    FROM tabel1, tabel2, tabel3
    WHERE tabel1.nama_kolom = tabel2.nama_kolom
    AND tabel2.nama_kolom = tabel3.nama_kolom;
    atau
    SELECT nama_kolom(s)
    FROM ((tabel1 INNER JOIN tabel2 ON tabel1.nama_kolom = tabel2.nama_kolom)
    INNER JOIN tabel3 ON tabel2.nama_kolom = tabel3.nama_kolom);
    ```
  
Maka hasil gabungannya :

![isi data tabel order_details](https://i.ibb.co/X7mHm6J/Screenshot-2023-10-31-004152.png)

Penggunaan Alias dalam LEFT JOIN
- LEFT JOIN menghasilkan semua baris dari tabel kiri dan baris yang cocok dari tabel kanan. 

=== "Sintaks LEFT JOIN"

    ```sql
    SELECT nama_kolom(s)
    FROM tabel1 LEFT JOIN tabel2 
    ON tabel1.nama_kolom = tabel2.nama_kolom;
    ```

Maka hasil gabungannya :

![isi data tabel order_details](https://i.ibb.co/1dNbkYk/Screenshot-2023-10-31-004412.png)

Penggunaan Alias dalam RIGHT JOIN
- RIGHT JOIN adalah kebalikan dari LEFT JOIN dan menghasilkan semua baris dari tabel kanan dan baris yang cocok dari tabel kiri. 

=== "Sintaks RIGHT JOIN"

    ```sql
    SELECT nama_kolom(s)
    FROM tabel1 RIGHT JOIN tabel2 
    ON tabel1.nama_kolom = tabel2.nama_kolom;
    ```

Maka hasil gabungannya :

![isi data tabel order_details](https://i.ibb.co/0cgdWkb/Screenshot-2023-10-31-004648.png)


Penggunaan Alias dalam UNION 
- UNION menggabungkan semua baris dari kedua tabel dan operator yang digunakan untuk menggabungkan hasil dari dua atau lebih query. 

=== "Sintaks UNION JOIN"

    ```sql
    SELECT kolom1, kolom2, ...
    FROM tabel1
    WHERE kondisi
    UNION
    SELECT kolom1, kolom2, ...
    FROM tabel2
    WHERE kondisi;
    ```
Maka hasil gabungannya :

![isi data tabel order_details](https://i.ibb.co/bBtVkMM/Screenshot-2023-10-31-005332.png)


Penggunaan Alias dalam UNION ALL
- UNION ALL Berbeda dengan fungsi UNION yang hanya memilih nilai yang berbeda secara default. Untuk mengizinkan nilai duplikat atau nilai yang dimunculkan tidak distinct, maka kita bisa menggunakan fungsi SQL UNION ALL. 

=== "Sintaks UNION JOIN"

    ```sql
    SELECT kolom1, kolom2, ...
    FROM tabel1
    WHERE kondisi
    UNION ALL
    SELECT kolom1, kolom2, ...
    FROM tabel2
    WHERE kondisi;
    ```

Maka hasil gabungannya :

![isi data tabel order_details](https://i.ibb.co/tzQpz3P/Screenshot-2023-10-31-005920.png)


