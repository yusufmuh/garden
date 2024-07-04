---
{"sticker":"emoji//1f4c5","dg-publish":true,"dg-home":true,"aliases":["SQL"],"permalink":"/knowladge/database/","tags":["gardenEntry"],"dgPassFrontmatter":true,"noteIcon":"","created":"2024-06-13T14:23:33.881+07:00","updated":"2024-07-04T13:50:37.307+07:00"}
---

```widgets
type: countdown
date: 2024-07-09 15:00:00
to: 2024-07-01 11:09:20
```
---
# 🗄SQL SERVER
---
# UTS
![WhatsApp Image 2024-04-25 at 13.40.31 (1).jpeg](/img/user/WhatsApp%20Image%202024-04-25%20at%2013.40.31%20(1).jpeg)![WhatsApp Image 2024-04-25 at 13.40.31.jpeg](/img/user/WhatsApp%20Image%202024-04-25%20at%2013.40.31.jpeg)
#UTS_Database #1_Introduction_to_Databases_and_The_Relational_Model #2_Normalization #3_ER_Modelling #4_Enhanced_ER_Modelling #5_SQL_Data_Definition_Introduction_to_Views #6_SQL_Data_Manipulation_Basic_Queries_1 #7_SQL_Data_Manipulation_Basic_Queries_2

---
---
# UAS
![WhatsApp Image 2024-07-03 at 21.01.01.jpeg](/img/user/WhatsApp%20Image%202024-07-03%20at%2021.01.01.jpeg)
#UAS_Database 
## SQL COMMAND
#8_SQL_Data_Manipulation_Multi_Table_Queries #9_Security_and_Administration #10_SQL_Data_Manipulation_Sub_Queries_and_View
## DATABASE ARCH + WAREHOUSE
#12_Database_Environment_Architectures #13_Data_Warehousing_Concepts

---
#8_SQL_Data_Manipulation_Multi_Table_Queries  #UAS_Database 
![[S 8_6 Lab SQL Data Manipulation (Multi table Queries).ppt]]

---
## **1) JOIN :**
### PENGERTIAN 
- JOIN adalah perintah dalam SQL yang digunakan untuk **menggabungkan baris dari dua atau lebih tabel berdasarkan kondisi tertentu.**
- JOIN mengizinkan kita untuk **mengambil data yang terdistribusi di beberapa tabel** dan **menggabungkannya dalam satu hasil query**.
### JENIS-JENIS 
#### **1. INNER JOIN**
- **INNER JOIN:** Mengembalikan baris yang memiliki **nilai cocok di kedua tabel**
- Menggabungkan data dari `Employees` dan `Departments` berdasarkan `department_id`.
```SQL
SELECT Employees.name, Departments.department_name
FROM Employees
INNER JOIN Departments
ON Employees.department_id = Departments.department_id;
```
![Pasted image 20240704100349.png](/img/user/Pasted%20image%2020240704100349.png)

#### **2. LEFT JOIN (LEFT OUTER JOIN):** 
- Mengembalikan **semua baris** dari ***tabel kiri dan baris yang cocok dari tabel kanan***. Jika tidak ada kecocokan, nilai dari tabel kanan akan menjadi **NULL**.
- Mengembalikan semua baris dari tabel `Employees` dan baris yang cocok dari tabel `Departments`. Jika tidak ada kecocokan, nilai dari tabel `Departments` akan menjadi NULL.
```SQL
SELECT Employees.name, Departments.department_name
FROM Employees
LEFT JOIN Departments
ON Employees.department_id = Departments.department_id;
```
![Pasted image 20240704100838.png](/img/user/Pasted%20image%2020240704100838.png)

#### **3. RIGHT JOIN (RIGHT OUTER JOIN):** 
- Mengembalikan **semua baris** dari ***tabel kanan dan baris yang cocok dari tabel kiri***. Jika tidak ada kecocokan, nilai dari tabel kiri akan menjadi **NULL**.
- Mengembalikan semua baris dari tabel `Departments` dan baris yang cocok dari tabel `Employees`. Jika tidak ada kecocokan, nilai dari tabel `Employees` akan menjadi NULL.
```SQL
SELECT Employees.name, Departments.department_name
FROM Employees
RIGHT JOIN Departments
ON Employees.department_id = Departments.department_id;
```
![Pasted image 20240704101127.png](/img/user/Pasted%20image%2020240704101127.png)

#### **4. FULL JOIN (FULL OUTER JOIN):** 
- Mengembalikan baris ketika ada kecocokan di **salah satu tabel**. ***Menggabungkan*** hasil dari **LEFT JOIN dan RIGHT JOIN**.
- Menggabungkan hasil dari LEFT JOIN dan RIGHT JOIN. Mengembalikan semua baris dari kedua tabel, dengan nilai **NULL** jika tidak ada kecocokan.
```SQL
SELECT Employees.name, Departments.department_name
FROM Employees
FULL JOIN Departments
ON Employees.department_id = Departments.department_id;
```
![Pasted image 20240704101349.png](/img/user/Pasted%20image%2020240704101349.png)

## **2) EXCEPT :**
### Pengertian EXCEPT:
- EXCEPT adalah perintah SQL yang digunakan untuk **mengembalikan semua baris** dalam hasil dari query pertama yang tidak ada dalam hasil dari query kedua.
- Berguna untuk **menemukan perbedaan** antara dua set hasil.
### Sintaks EXCEPT:
- Dasar sintaks EXCEPT adalah sebagai berikut:
```SQL
SELECT columns 
FROM table1 
EXCEPT 
SELECT columns 
FROM table2;
```
- EXCEPT **mengeliminasi duplikasi** dalam hasil akhir, mirip dengan **UNION dan INTERSECT**.

**Contoh Penggunaan:**
- Misalkan kita memiliki dua tabel `employees` dan `managers`, dan kita ingin mencari semua karyawan yang bukan manajer.
    `SELECT employee_id FROM employees EXCEPT SELECT manager_id FROM managers;`
- Mengembalikan semua baris dari query pertama yang tidak ada dalam hasil dari query kedua.
```SQL
SELECT employee_id FROM Employees 
EXCEPT 
SELECT manager_id FROM Managers;
```
![Pasted image 20240704102424.png](/img/user/Pasted%20image%2020240704102424.png)

### Perbedaan dengan NOT EXISTS dan NOT IN:
- EXCEPT vs. NOT EXISTS :
    `SELECT columns FROM table1 t1 WHERE NOT EXISTS (SELECT 1 FROM table2 t2 WHERE t1.common_column = t2.common_column);`
- EXCEPT vs. NOT IN :
    `SELECT columns FROM table1 WHERE common_column NOT IN (SELECT common_column FROM table2);`

---
#9_Security_and_Administration #UAS_Database
![[S 9_10 Lab Security and Administration.ppt]]

---
## **3) GRANT :**
### Pengertian GRANT:
- GRANT adalah perintah dalam SQL yang digunakan untuk **memberikan izin (privileges) kepada pengguna** atau **peran (role) untuk melakukan tindakan tertentu** pada objek basis data seperti tabel, pandangan (view), prosedur tersimpan (stored procedure), dan lain-lain.
- Izin yang dapat diberikan mencakup ***SELECT, INSERT, UPDATE, DELETE,*** dan lainnya.
### Sintaks GRANT:
- Dasar sintaks GRANT adalah sebagai berikut:
```SQL
GRANT privilege [, privilege...] 
ON object 
TO user [, user...];
```

**Contoh Penggunaan GRANT:**
- Memberikan izin SELECT dan INSERT pada tabel `Employees` kepada pengguna `john_doe`.
    `GRANT SELECT, INSERT ON Employees TO john_doe;`
    
- Memberikan semua izin pada tabel `Departments` kepada pengguna `admin`.
    `GRANT ALL PRIVILEGES ON Departments TO admin;`
    
### Opsi WITH GRANT OPTION:
- Menambahkan opsi `WITH GRANT OPTION` memungkinkan penerima izin untuk memberikan izin yang sama kepada pengguna lain.
    `GRANT SELECT ON Employees TO john_doe WITH GRANT OPTION;`
    

## **4) REVOKE**
### Pengertian REVOKE:
- REVOKE adalah perintah dalam SQL yang digunakan untuk **mencabut izin yang telah diberika**n kepada pengguna atau peran.
- REVOKE digunakan untuk *menghapus izin tertentu dari pengguna* untuk menjaga keamanan dan integritas basis data.
### Sintaks REVOKE:
- Dasar sintaks REVOKE adalah sebagai berikut:
```SQL
REVOKE privilege [, privilege...] 
ON object 
FROM user [, user...];
```
    
**Contoh Penggunaan REVOKE:**
- Mencabut izin SELECT pada tabel `Employees` dari pengguna `john_doe`.
    `REVOKE SELECT ON Employees FROM john_doe;`
    
- Mencabut **semua izin** pada tabel `Departments` dari pengguna `admin`.
    `REVOKE ALL PRIVILEGES ON Departments FROM admin;`
    
### Opsi CASCADE dan RESTRICT:
- **CASCADE:** ***Menghapus izin yang diberikan kepada pengguna lain*** oleh pengguna yang izinnya dicabut.
- **RESTRICT:** ***Mencegah pencabutan izin*** jika izin tersebut telah diberikan kepada pengguna lain.

**Contoh Gambar Tabel:**
 penggunaan **GRANT dan REVOKE**, contoh tabel dan izin yang diberikan serta dicabut.
![Pasted image 20240704104219.png](/img/user/Pasted%20image%2020240704104219.png)
- **GRANT SELECT dan INSERT pada Employees kepada john_doe:**
```SQL
GRANT SELECT, INSERT ON Employees 
TO john_doe;
```
- **REVOKE INSERT pada Employees dari john_doe:**
```SQL
REVOKE INSERT ON Employees 
FROM john_doe;
```

---
#10_SQL_Data_Manipulation_Sub_Queries_and_View #11_DATABASE_ENVIRONMENT #UAS_Database 
![[S 10_8+9 SQL Data Manipulation (Sub Queries) and View.ppt]]

---
## 5) VIEW
### Pengertian VIEW:
- VIEW adalah objek basis data yang **menyajikan hasil query sebagai tabel virtual**.
- VIEW digunakan untuk menyederhanakan query yang kompleks, meningkatkan keamanan data dengan membatasi akses ke data tertentu, dan menyediakan abstraksi untuk struktur basis data yang lebih kompleks.
### Pembuatan VIEW:
- Sintaks dasar untuk membuat VIEW adalah sebagai berikut:
```SQL
CREATE VIEW view_name 
AS 
SELECT column1, column2, ... 
FROM table_name 
WHERE condition;
```
    
**Contoh pembuatan VIEW:**
    `CREATE VIEW EmployeeView AS SELECT employee_id, name, department_id FROM Employees WHERE department_id = 101;`
    
### Manfaat Menggunakan VIEW:
- **Abstraksi Data:** Menyembunyikan kompleksitas query dari pengguna.
- **Keamanan Data:** Membatasi akses ke kolom dan baris tertentu dalam tabel.
- **Konsistensi:** Memastikan data yang sama diakses dengan cara yang sama oleh semua pengguna.
- **Kemudahan Penggunaan:** Menyederhanakan query yang sering digunakan.

### Modifikasi VIEW:
- VIEW dapat dimodifikasi menggunakan perintah `CREATE OR REPLACE VIEW` atau dengan menghapus dan membuat kembali VIEW.
    `CREATE OR REPLACE VIEW EmployeeView AS SELECT employee_id, name, department_id, salary FROM Employees WHERE department_id = 101;`
    
### Menghapus VIEW:
- VIEW dapat dihapus menggunakan perintah `DROP VIEW`:
    `DROP VIEW view_name;`
    
**Contoh Penggunaan VIEW:**
- Misalkan kita memiliki tabel `Employees` dan `Departments`, kita dapat membuat VIEW untuk menampilkan informasi karyawan yang hanya berasal dari departemen tertentu.

**Contoh Pembuatan dan Penggunaan VIEW:**
![Pasted image 20240704110107.png](/img/user/Pasted%20image%2020240704110107.png)
**3. Contoh Pembuatan VIEW:**
- Membuat VIEW untuk menampilkan karyawan dari departemen HR.
```SQL
CREATE VIEW HR_Employees AS
SELECT employee_id, name, salary
FROM Employees
WHERE department_id = 101;
```
**4. Menggunakan VIEW:**
- Menggunakan VIEW untuk mengambil data karyawan dari departemen HR
```SQL
SELECT * FROM HR_Employees;
```
![Pasted image 20240704110339.png](/img/user/Pasted%20image%2020240704110339.png)
Gambar tersebut menunjukkan bagaimana VIEW `HR_Employees` dibuat dari tabel `Employees`, yang hanya menampilkan karyawan dari departemen HR. Dengan menggunakan VIEW, kita dapat menyederhanakan query dan membatasi akses ke data tertentu untuk tujuan keamanan dan manajemen data yang lebih baik.

## 6) IN
### Pengertian IN:
- Perintah `IN` digunakan dalam SQL untuk memeriksa apakah suatu nilai berada dalam daftar nilai yang diberikan.
- Biasanya digunakan dalam klausa `WHERE` untuk memfilter baris berdasarkan beberapa kemungkinan nilai.

### Sintaks IN:
- Sintaks dasar perintah `IN` adalah sebagai berikut:
```SQL
SELECT column1, column2, ... 
FROM table_name 
WHERE column_name 
IN (value1, value2, ...)
```
    
**Contoh penggunaan `IN`:**
    `SELECT name FROM Employees WHERE department_id IN (101, 103);`
    
- Misalkan kita ingin memilih karyawan yang bekerja di departemen HR atau Sales.
    `SELECT name FROM Employees WHERE department_id IN (101, 103);`
    
## 7) EXISTS
### Pengertian EXISTS:
- Perintah `EXISTS` digunakan untuk **memeriksa** apakah **subquery** mengembalikan hasil. Jika subquery mengembalikan satu atau lebih baris, perintah `EXISTS` akan mengembalikan nilai TRUE.
- Biasanya digunakan dalam klausa `WHERE` untuk memfilter baris berdasarkan adanya baris dalam subquery.

### Sintaks EXISTS:
- Sintaks dasar perintah `EXISTS` adalah sebagai berikut:
```SQL
SELECT column1, column2, ... 
FROM table_name 
WHERE EXISTS (subquery)
```
    
**Contoh penggunaan `EXISTS`:**
    `SELECT name FROM Employees e WHERE EXISTS (   SELECT 1   FROM Departments d   WHERE e.department_id = d.department_id   AND d.department_name = 'HR' );`
    
**Contoh Penggunaan EXISTS:**
- Misalkan kita ingin memilih karyawan yang bekerja di departemen yang memiliki nama 'HR'.
    `SELECT name FROM Employees e WHERE EXISTS (   SELECT 1   FROM Departments d   WHERE e.department_id = d.department_id   AND d.department_name = 'HR' );`
![Pasted image 20240704111419.png](/img/user/Pasted%20image%2020240704111419.png)
1. **Query dengan IN:**
    - Pilih nama karyawan yang bekerja di departemen HR atau Sales.
        `SELECT name FROM Employees WHERE department_id IN (101, 103);`
![Pasted image 20240704111601.png](/img/user/Pasted%20image%2020240704111601.png)
2. **Query dengan EXISTS:**
	- Pilih nama karyawan yang bekerja di departemen dengan nama 'HR'.
	    `SELECT name FROM Employees e WHERE EXISTS (   SELECT 1   FROM Departments d   WHERE e.department_id = d.department_id   AND d.department_name = 'HR' );`
![Pasted image 20240704111822.png](/img/user/Pasted%20image%2020240704111822.png)
Gambar tersebut menunjukkan bagaimana perintah `IN` dan `EXISTS` digunakan untuk memfilter data dari tabel `Employees` berdasarkan kondisi yang diberikan. Dengan menggunakan `IN`, kita dapat memilih karyawan dari beberapa departemen tertentu, sedangkan `EXISTS` memungkinkan kita untuk memilih karyawan berdasarkan kondisi yang ada dalam subquery.

---
## 8) Subquery
- Subquery adalah **query di dalam query lain**. Subquery sering digunakan untuk **mengembalikan hasil yang akan digunakan** dalam query utama. Mereka dapat berada dalam klausa **SELECT, FROM, atau WHERE**.
### Jenis Subquery:
1. **Single-row Subquery**: Mengembalikan satu baris hasil.
2. **Multiple-row Subquery**: Mengembalikan lebih dari satu baris hasil.
3. **Correlated Subquery**: Bergantung pada query luar.

 **Contoh:**
Misalkan kita memiliki dua tabel: `Employees` dan `Departments`.

**Employees**

| EmployeeID | Name    | Salary | DepartmentID |
| ---------- | ------- | ------ | ------------ |
| 1          | Alice   | 50000  | 1            |
| 2          | Bob     | 60000  | 2            |
| 3          | Charlie | 55000  | 1            |
| 4          | David   | 45000  | 3            |
| 5          | Eva     | 70000  | 2            |

**Departments**

| DepartmentID | DepartmentName |
| ------------ | -------------- |
| 1            | HR             |
| 2            | IT             |
| 3            | Finance        |

Untuk menemukan nama-nama pegawai dengan gaji di atas rata-rata gaji, kita bisa menggunakan subquery:
```SQL
SELECT Name 
FROM Employees 
WHERE Salary > (SELECT AVG(Salary) FROM Employees)
```
### Soal Subquery
***Tentukan nama departemen dari pegawai yang memiliki gaji tertinggi.***
**Jawaban:** Untuk menemukan nama departemen dari pegawai yang memiliki gaji tertinggi, kita dapat menggunakan subquery sebagai berikut:
```SQL
SELECT DepartmentName 
FROM Departments 
WHERE DepartmentID = (SELECT DepartmentID 
					  FROM Employees                       
					  WHERE Salary = (SELECT MAX(Salary) 
									  FROM Employees)
					  )
```
**Penjelasan:**
- Subquery pertama (paling dalam) mencari gaji maksimum (`SELECT MAX(Salary) FROM Employees`).
- Subquery kedua menggunakan hasil dari subquery pertama untuk menemukan `DepartmentID` pegawai dengan gaji tertinggi (`SELECT DepartmentID FROM Employees WHERE Salary = (MAX(Salary))`).
- Query utama menggunakan hasil dari subquery kedua untuk menemukan nama departemen (`SELECT DepartmentName FROM Departments WHERE DepartmentID = (...)`).

***Jelaskan perbedaan antara single-row subquery dan multiple-row subquery, dan berikan contoh masing-masing.***
**Jawaban:**
- **Single-row Subquery:** 
	Single-row subquery adalah subquery yang mengembalikan **hanya satu baris hasil**. Biasanya digunakan dalam klausa **WHERE atau HAVING** dalam query utama.
**Contoh:** Menemukan pegawai dengan gaji tertinggi:
```SQL
SELECT Name, Salary 
FROM Employees 
WHERE Salary = (SELECT MAX(Salary) 
				FROM Employees)
```
Dalam contoh ini, subquery `SELECT MAX(Salary) FROM Employees` mengembalikan satu nilai gaji tertinggi.

- **Multiple-row Subquery:** 
	Multiple-row subquery adalah subquery yang dapat mengembalikan **lebih dari satu baris hasil**. Digunakan dengan klausa seperti **IN, ANY, atau ALL** dalam query utama.
**Contoh:** Menemukan pegawai yang bekerja di departemen yang memiliki lebih dari satu pegawai:
```SQL
SELECT Name 
FROM Employees 
WHERE DepartmentID IN (SELECT DepartmentID                        
					   FROM Employees                        
					   GROUP BY DepartmentID                        
					   HAVING COUNT(*) > 1
					   )
```
Dalam contoh ini, subquery `SELECT DepartmentID FROM Employees GROUP BY DepartmentID HAVING COUNT(*) > 1` mengembalikan daftar `DepartmentID` yang memiliki lebih dari satu pegawai.


---
## 9) Aggregation
- Aggregation adalah **teknik** untuk **mengumpulkan beberapa baris data menjadi satu ringkasan** nilai dengan menggunakan fungsi agregat seperti `SUM`, `AVG`, `COUNT`, `MAX`, dan `MIN`.

**Contoh:**
Menggunakan tabel `Employees` di atas, kita bisa menghitung rata-rata gaji di setiap departemen.
```SQL
SELECT DepartmentID, AVG(Salary) 
AS AverageSalary 
FROM Employees 
GROUP BY DepartmentID
```

Hasilnya akan berupa tabel dengan rata-rata gaji per departemen:
**Average Salaries per Department**

| DepartmentID | AverageSalary |
| ------------ | ------------- |
| 1            | 52500         |
| 2            | 65000         |
| 3            | 45000         |
### SOAL AGREGASI
***Hitung jumlah total gaji yang dibayarkan oleh setiap departemen.***
**Jawaban:** Untuk menghitung jumlah total gaji yang dibayarkan oleh setiap departemen, kita dapat menggunakan fungsi agregat `SUM` dan `GROUP BY`:
```SQL
SELECT DepartmentID, SUM(Salary) 
AS TotalSalary 
FROM Employees 
GROUP BY DepartmentID
```
**Penjelasan:**
- Query ini mengelompokkan data berdasarkan `DepartmentID`.
- Menggunakan fungsi `SUM(Salary)` untuk menghitung jumlah total gaji di setiap departemen.

***Jelaskan pentingnya agregasi dalam analisis data dan berikan contoh situasi di mana agregasi digunakan untuk membuat keputusan bisnis.***
**Jawaban:** 
	Agregasi dalam SQL sangat penting untuk analisis data karena memungkinkan pengumpulan data dari beberapa baris menjadi satu ringkasan nilai. Ini membantu dalam memahami pola dan tren dalam data yang besar dan kompleks. Dengan menggunakan fungsi agregat seperti `SUM`, `AVG`, `COUNT`, `MAX`, dan `MIN`, kita dapat dengan mudah menganalisis data dan membuat keputusan yang lebih baik.
**Contoh Situasi:** 
	Sebuah perusahaan retail ingin menganalisis performa penjualan mereka untuk membuat keputusan tentang inventaris dan strategi pemasaran. 
Mereka dapat menggunakan agregasi untuk:
1. **Menghitung Total Penjualan**:
```SQL
SELECT SUM(SalesAmount) 
AS TotalSales 
FROM Sales
```
Ini memberikan total penjualan yang membantu perusahaan memahami skala operasinya.
    
2. **Rata-rata Penjualan per Bulan**:
```SQL
SELECT AVG(SalesAmount) 
AS AverageMonthlySales 
FROM Sales 
WHERE SaleDate 
BETWEEN '2023-01-01' AND '2023-12-31' 
GROUP BY MONTH(SaleDate)
```
Ini membantu dalam mengidentifikasi tren musiman dan merencanakan strategi pemasaran musiman.
    
3. **Produk Terlaris**:
```SQL
SELECT ProductID, COUNT(*) AS NumberOfSales 
FROM Sales 
GROUP BY ProductID 
ORDER BY NumberOfSales 
DESC LIMIT 1
```
Ini membantu perusahaan untuk mengetahui produk mana yang paling laris dan mungkin mengalokasikan lebih banyak sumber daya untuk produk tersebut.
    
Dengan menggunakan agregasi, perusahaan dapat membuat keputusan yang lebih informasi mengenai pengelolaan inventaris, penjadwalan karyawan, dan strategi pemasaran, yang pada akhirnya meningkatkan efisiensi dan keuntungan.

---
#12_Database_Environment_Architectures #UAS_Database 
![[S 12 Database Environment & Architectures.ppt]]
![[S 12 Lab Project.pptx]]

---
# **DBMS Architecture:**
### Pengertian Arsitektur DBMS:
- Arsitektur DBMS (Database Management System) merujuk pada struktur dan organisasi komponen DBMS serta bagaimana komponen-komponen ini berinteraksi satu sama lain untuk mengelola data dalam basis data.

### Lapisan Arsitektur DBMS:
- Arsitektur DBMS umumnya terdiri dari beberapa lapisan yang dirancang untuk **memisahkan berbagai fungsi** dan **operasi** dalam sistem basis data. Lapisan ini meliputi:
    1. **Lapisan Eksternal:**
        - Menyediakan **antarmuka bagi pengguna** akhir dan aplikasi **untuk mengakses data**.
        - Melibatkan pandangan (views) dan **antarmuka pengguna**.
    2. **Lapisan Konseptual:**
        - Mengabstraksi dan **menyembunyikan detail internal** data.
        - Mengatur bagaimana data direpresentasikan secara logis dalam basis data.
    3. **Lapisan Internal:**
        - Menangani **penyimpanan fisik data di media penyimpanan**.
        - Mengelola **file dan indeks** untuk efisiensi penyimpanan dan akses data.

### Komponen Utama DBMS:
- **DBMS Engine:** **Komponen inti** yang menangani operasi penyimpanan, pengambilan, dan pengelolaan data.
- **Query Processor:** Mengurai, mengoptimalkan, dan **mengeksekusi perintah SQL**.
- **Storage Manager:** **Mengelola penyimpanan** fisik data, termasuk pengelolaan file dan ruang disk.
- **Transaction Manager:** Menangani eksekusi transaksi untuk memastikan konsistensi dan isolasi data.
- **Buffer Manager:** **Mengelola memori** yang digunakan untuk caching data yang sering diakses.
- **Recovery Manager:** **Memastikan pemulihan data** dalam kasus kegagalan sistem.

### Model Arsitektur DBMS:
- **Satu Tingkat (Single-tier):**
    - Basis data dan aplikasi berada di dalam satu sistem.
- **Dua Tingkat (Two-tier):**
    - Klien dan server berinteraksi secara langsung.
    - Klien menjalankan aplikasi, sedangkan server menjalankan DBMS.
- **Tiga Tingkat (Three-tier):**
    - Terdiri dari lapisan presentasi (client), lapisan aplikasi (middle-tier), dan lapisan data (server).
    - Middle-tier menyediakan logika aplikasi dan komunikasi antara klien dan server.

### Contoh Arsitektur DBMS:
1. **Arsitektur Satu Tingkat (Single-tier):**
    - Basis data dan aplikasi berada di dalam satu sistem komputer.
2. **Arsitektur Dua Tingkat (Two-tier):**
    - Sistem klien-server di mana klien mengirim permintaan langsung ke server basis data.
3. **Arsitektur Tiga Tingkat (Three-tier):**
    - Klien, aplikasi, dan basis data berada di lapisan yang berbeda.
    - Aplikasi di middle-tier mengelola logika bisnis dan komunikasi antara klien dan server basis data.

##### Contoh Kasus:
<p align="justify">Sebuah perusahaan e-commerce, ShopEase, berencana untuk meningkatkan sistem basis data mereka untuk mendukung peningkatan jumlah pelanggan dan transaksi harian. Saat ini, ShopEase menggunakan arsitektur DBMS dua tingkat (two-tier) di mana aplikasi klien langsung berkomunikasi dengan server basis data. Namun, dengan pertumbuhan bisnis yang pesat, mereka menghadapi masalah seperti kinerja yang lambat dan kesulitan dalam mengelola transaksi yang meningkat secara drastis. Oleh karena itu, mereka mempertimbangkan untuk beralih ke arsitektur tiga tingkat (three-tier) untuk meningkatkan efisiensi, skalabilitas, dan keamanan sistem mereka.</p>

##### Esai Mengenai Arsitektur DBMS:

<p align="justify">Arsitektur DBMS memainkan peran penting dalam menentukan efisiensi, skalabilitas, dan keamanan sistem basis data. Ada beberapa model arsitektur yang dapat dipilih oleh organisasi berdasarkan kebutuhan mereka, yaitu arsitektur satu tingkat (single-tier), dua tingkat (two-tier), dan tiga tingkat (three-tier).

Pada arsitektur satu tingkat, basis data dan aplikasi berada dalam satu sistem. Model ini sederhana dan cocok untuk aplikasi kecil atau pengembangan dan pengujian, tetapi tidak skalabel dan memiliki keterbatasan dalam hal keamanan dan manajemen.

Arsitektur dua tingkat melibatkan interaksi langsung antara klien dan server basis data. Klien menjalankan aplikasi yang mengirim permintaan langsung ke server. Meskipun model ini lebih efisien dibandingkan dengan arsitektur satu tingkat, ia memiliki keterbatasan dalam menangani jumlah pengguna yang besar dan kompleksitas transaksi. Karena aplikasi klien harus mengelola logika bisnis dan komunikasi basis data, ini dapat menyebabkan kinerja yang lambat ketika jumlah permintaan meningkat.

Arsitektur tiga tingkat memisahkan antarmuka pengguna, logika aplikasi, dan penyimpanan data ke dalam tiga lapisan terpisah. Lapisan presentasi (client tier) berinteraksi dengan pengguna, lapisan aplikasi (middle-tier) mengelola logika bisnis dan komunikasi, dan lapisan data (server tier) menangani penyimpanan dan pengelolaan data. Model ini menawarkan banyak keuntungan, termasuk skalabilitas yang lebih baik, pemeliharaan yang lebih mudah, dan peningkatan keamanan. Dengan memisahkan logika aplikasi dari klien dan server basis data, arsitektur tiga tingkat dapat menangani beban yang lebih besar dan mendistribusikan tugas secara lebih efisien.

Bagi ShopEase, beralih ke arsitektur tiga tingkat dapat menjadi solusi untuk mengatasi masalah kinerja dan skalabilitas. Dengan menggunakan middle-tier untuk mengelola logika bisnis dan transaksi, mereka dapat mengurangi beban pada klien dan server basis data, serta meningkatkan responsivitas dan efisiensi sistem. Selain itu, arsitektur ini memungkinkan penambahan lapisan keamanan tambahan untuk melindungi data pelanggan yang sensitif.

Secara keseluruhan, pemilihan arsitektur DBMS yang tepat sangat penting untuk memastikan bahwa sistem basis data dapat mendukung kebutuhan bisnis yang berkembang. Arsitektur tiga tingkat menawarkan fleksibilitas dan kemampuan untuk mengelola beban kerja yang besar, menjadikannya pilihan yang ideal untuk perusahaan seperti ShopEase yang sedang berkembang pesat.</p>

- **Perbedaan utama antara arsitektur DBMS satu tingkat, dua tingkat, dan tiga tingkat:**
    - **Satu Tingkat (Single-tier):** Basis data dan aplikasi berada dalam satu sistem. Sederhana dan cocok untuk aplikasi kecil atau pengembangan, tetapi tidak skalabel dan kurang aman.
    - **Dua Tingkat (Two-tier):** Klien langsung berkomunikasi dengan server basis data. Klien menjalankan aplikasi dan mengirim permintaan ke server. Lebih efisien daripada satu tingkat tetapi memiliki keterbatasan dalam menangani banyak pengguna dan transaksi kompleks.
    - **Tiga Tingkat (Three-tier):** Memisahkan antarmuka pengguna, logika aplikasi, dan penyimpanan data ke dalam tiga lapisan terpisah. Lebih skalabel, mudah dipelihara, dan menawarkan keamanan yang lebih baik karena logika aplikasi dikelola di middle-tier.
    - 
- **Arsitektur tiga tingkat dianggap lebih skalabel dibandingkan arsitektur dua tingkat karena:**
    - **Pemrosesan Terdistribusi:** Middle-tier dapat mendistribusikan beban kerja pemrosesan logika bisnis, mengurangi beban pada klien dan server basis data.
    - **Keseimbangan Beban:** Middle-tier memungkinkan penyeimbangan beban yang lebih baik, sehingga lebih mudah menambah server aplikasi sesuai kebutuhan untuk menangani peningkatan jumlah pengguna dan permintaan.
    
- **Dalam konteks keamanan, arsitektur tiga tingkat dapat memberikan perlindungan yang lebih baik dibandingkan arsitektur dua tingkat karena:**
    - **Isolasi Data:** Middle-tier berfungsi sebagai penghalang antara klien dan server basis data, sehingga data sensitif tidak langsung terekspos ke klien.
    - **Keamanan Tambahan:** Middle-tier dapat menerapkan lapisan keamanan tambahan seperti autentikasi, otorisasi, dan enkripsi data sebelum mengirimkan data ke dan dari server basis data.
    
- **Contoh kasus di mana arsitektur satu tingkat masih dapat digunakan dengan efektif:**
    - Pengembangan dan pengujian aplikasi kecil di mana kompleksitas dan jumlah pengguna rendah.
    - Aplikasi desktop tunggal yang tidak memerlukan akses jaringan atau skalabilitas yang tinggi.
    
- **Keuntungan menggunakan middle-tier dalam arsitektur tiga tingkat:**
    - **Isolasi Logika Bisnis:** Memisahkan logika bisnis dari klien dan server basis data, meningkatkan modularitas dan pemeliharaan.
    - **Pengelolaan Transaksi:** Middle-tier dapat mengelola transaksi secara efisien, memastikan konsistensi data dan integritas transaksi.
    - **Peningkatan Keamanan:** Menyediakan lapisan keamanan tambahan untuk melindungi data sensitif dan mengelola autentikasi dan otorisasi pengguna.
    
---
#13_Data_Warehousing_Concepts #UAS_Database 
![[S 13 Data Warehousing Concept.ppt]]

---
# DATA WAREHOUSE
### Pengertian Data Warehouse:
- Data Warehouse adalah sistem basis data yang dirancang untuk **analisis dan pelaporan data**, seringkali dari berbagai sumber data yang berbeda. Tujuan utama dari data warehouse adalah menyediakan basis data terpadu yang memungkinkan analisis data historis untuk pengambilan keputusan bisnis.

### Karakteristik Data Warehouse:
1. **Subject-Oriented:** Data diorganisasi berdasarkan **subjek utama** bisnis (misalnya, penjualan, pelanggan).
2. **Integrated:** Data dari berbagai sumber **diintegrasikan** dan disimpan secara konsisten.
3. **Time-Variant:** Data disimpan untuk **jangka waktu yang panjan**g dan mencerminkan perubahan dari waktu ke waktu.
4. **Non-Volatile:** Data **tidak dihapus atau diubah setelah dimasukkan** ke dalam data warehouse. Data hanya ditambahkan.

### Arsitektur Data Warehouse:
- Arsitektur data warehouse terdiri dari beberapa komponen utama:
    1. **Source Systems:** Sistem operasional **tempat data berasal,** seperti basis data transaksi, file log, dan aplikasi lainnya.
    2. **ETL (Extract, Transform, Load):** Proses yang **mengekstraksi data** dari sistem sumber, mengubahnya ke format yang konsisten, dan memuatnya ke dalam data warehouse.
    3. **Data Warehouse Database:** Basis data pusat yang **menyimpan data** yang telah diolah untuk analisis.
    4. **Metadata:** **Informasi tentang data yang disimpan** di data warehouse, seperti definisi skema dan aturan transformasi.
    5. **Data Marts:** **Subset dari data warehouse** yang dirancang untuk memenuhi kebutuhan analisis tertentu.
    6. **OLAP (Online Analytical Processing):** **Alat untuk menganalisis data yang disimpan** di data warehouse, memungkinkan penggunanya untuk melakukan query yang kompleks dan analisis multidimensional.

### Proses ETL:
- **Extract:** Mengambil data dari berbagai sumber.
- **Transform:** Mengubah data ke format yang konsisten, termasuk pembersihan data, penggabungan data, dan agregasi data.
- **Load:** Memuat data yang telah diubah ke dalam data warehouse.

###### **Contoh Gambar Tabel:**
![Pasted image 20240704114428.png](/img/user/Pasted%20image%2020240704114428.png)
![Pasted image 20240704114459.png](/img/user/Pasted%20image%2020240704114459.png)
###### **Contoh Proses ETL:**
1. **Extract:**
    - Mengambil data dari tabel penjualan, produk, dan pelanggan dari sistem sumber.
```SQL
SELECT * FROM Sales;
SELECT * FROM Products;
SELECT * FROM Customers;
```
2. **Transform:**
	- Menggabungkan data dari tabel penjualan dengan informasi produk dan pelanggan.
```SQL
SELECT s.SalesID, p.ProductName, c.CustomerName, s.SalesDate, s.Quantity, s.TotalAmount
FROM Sales s
JOIN Products p ON s.ProductID = p.ProductID
JOIN Customers c ON s.CustomerID = c.CustomerID;
```
3. **Load:**
	- Memuat data yang telah diubah ke dalam tabel data warehouse.
```SQL
INSERT INTO DataWarehouse (SalesID, ProductName, CustomerName, SalesDate, Quantity, TotalAmount)
SELECT s.SalesID, p.ProductName, c.CustomerName, s.SalesDate, s.Quantity, s.TotalAmount
FROM Sales s
JOIN Products p ON s.ProductID = p.ProductID
JOIN Customers c ON s.CustomerID = c.CustomerID;
```
Gambar ini menunjukkan bagaimana data dari berbagai tabel sumber (Penjualan, Produk, Pelanggan) diekstrak, diubah, dan dimuat ke dalam tabel data warehouse untuk analisis lebih lanjut. Data warehouse memungkinkan perusahaan untuk menganalisis data historis dari berbagai perspektif untuk mendukung pengambilan keputusan bisnis yang lebih baik.

##### Contoh Kasus:
<p align="justify">Perusahaan ritel multinasional, ShopMax, mengalami kesulitan dalam mengelola dan menganalisis data dari berbagai cabang di seluruh dunia. Data penjualan, inventaris, dan pelanggan tersebar di berbagai sistem basis data yang berbeda, membuat analisis terpadu menjadi sangat sulit. ShopMax memutuskan untuk membangun data warehouse guna mengintegrasikan data dari semua cabang dan sistem operasional, memungkinkan analisis yang lebih efektif dan pengambilan keputusan yang lebih baik.</p>
##### Esai Mengenai Data Warehouse:

<center>Pentingnya Data Warehouse dalam Analisis Bisnis</center>
<p align="justify">
Dalam era digital ini, data menjadi aset yang sangat berharga bagi perusahaan. Namun, data yang tersebar di berbagai sistem dan lokasi dapat menjadi tantangan besar dalam analisis dan pengambilan keputusan. Di sinilah peran data warehouse menjadi sangat penting. Data warehouse adalah sistem basis data yang dirancang khusus untuk analisis dan pelaporan, yang mengintegrasikan data dari berbagai sumber untuk memberikan pandangan holistik tentang kinerja bisnis.

Data warehouse memiliki beberapa karakteristik utama: subject-oriented, integrated, time-variant, dan non-volatile. Keempat karakteristik ini memungkinkan data warehouse untuk menyajikan data yang terorganisasi berdasarkan subjek utama bisnis, terintegrasi secara konsisten dari berbagai sumber, mengandung data historis yang mencerminkan perubahan dari waktu ke waktu, dan bersifat tetap setelah dimuat.

Proses ETL (Extract, Transform, Load) adalah jantung dari implementasi data warehouse. Data dari berbagai sumber diekstrak, diubah ke format yang konsisten dan bersih, lalu dimuat ke dalam data warehouse. Proses ini memastikan bahwa data yang masuk ke dalam data warehouse berkualitas tinggi dan siap untuk dianalisis.

ShopMax, misalnya, menghadapi tantangan dalam mengelola data dari cabang-cabangnya di seluruh dunia. Dengan membangun data warehouse, ShopMax dapat mengintegrasikan data penjualan, inventaris, dan pelanggan dari berbagai sistem operasional. Proses ETL mengumpulkan data dari setiap cabang, membersihkannya, dan menyimpannya dalam data warehouse yang terpadu. Hasilnya, manajemen ShopMax dapat melakukan analisis mendalam mengenai kinerja penjualan global, mengidentifikasi tren pasar, dan membuat keputusan strategis yang lebih baik.

Selain itu, data warehouse juga mendukung analisis multi-dimensional melalui OLAP (Online Analytical Processing). Dengan OLAP, ShopMax dapat menganalisis data dari berbagai perspektif, seperti penjualan per wilayah, per produk, atau per periode waktu tertentu. Ini memberikan wawasan yang lebih mendalam dan memungkinkan identifikasi peluang pertumbuhan serta area yang memerlukan perhatian lebih.

Secara keseluruhan, data warehouse adalah alat yang sangat kuat dalam mengelola dan menganalisis data bisnis. Dengan menyediakan data yang terintegrasi dan berkualitas tinggi, data warehouse memungkinkan perusahaan seperti ShopMax untuk mengambil keputusan yang lebih cerdas dan berbasis data, sehingga meningkatkan daya saing dan kinerja bisnis secara keseluruhan.</p>

##### **Soal Mengenai DBMS Architecture dan Jawabannya:**
1. **Apa perbedaan utama antara arsitektur DBMS satu tingkat, dua tingkat, dan tiga tingkat?**
    - **Jawaban:**
        - **Satu Tingkat (Single-tier):** Basis data dan aplikasi berada dalam satu sistem. Sederhana dan cocok untuk aplikasi kecil atau pengembangan, tetapi tidak skalabel dan kurang aman.
        - **Dua Tingkat (Two-tier):** Klien langsung berkomunikasi dengan server basis data. Klien menjalankan aplikasi dan mengirim permintaan ke server. Lebih efisien daripada satu tingkat tetapi memiliki keterbatasan dalam menangani banyak pengguna dan transaksi kompleks.
        - **Tiga Tingkat (Three-tier):** Memisahkan antarmuka pengguna, logika aplikasi, dan penyimpanan data ke dalam tiga lapisan terpisah. Lebih skalabel, mudah dipelihara, dan menawarkan keamanan yang lebih baik karena logika aplikasi dikelola di middle-tier.
        
2. **Mengapa arsitektur tiga tingkat dianggap lebih skalabel dibandingkan arsitektur dua tingkat? Berikan dua alasan.**
    - **Jawaban:**
        - **Pemrosesan Terdistribusi:** Middle-tier dapat mendistribusikan beban kerja pemrosesan logika bisnis, mengurangi beban pada klien dan server basis data.
        - **Keseimbangan Beban:** Middle-tier memungkinkan penyeimbangan beban yang lebih baik, sehingga lebih mudah menambah server aplikasi sesuai kebutuhan untuk menangani peningkatan jumlah pengguna dan permintaan.
        
3. **Dalam konteks keamanan, bagaimana arsitektur tiga tingkat dapat memberikan perlindungan yang lebih baik dibandingkan arsitektur dua tingkat?**
    - **Jawaban:**
        - **Isolasi Data:** Middle-tier berfungsi sebagai penghalang antara klien dan server basis data, sehingga data sensitif tidak langsung terekspos ke klien.
        - **Keamanan Tambahan:** Middle-tier dapat menerapkan lapisan keamanan tambahan seperti autentikasi, otorisasi, dan enkripsi data sebelum mengirimkan data ke dan dari server basis data.
        
4. **Berikan contoh kasus di mana arsitektur satu tingkat masih dapat digunakan dengan efektif.**
    - **Jawaban:**
        - Pengembangan dan pengujian aplikasi kecil di mana kompleksitas dan jumlah pengguna rendah.
        - Aplikasi desktop tunggal yang tidak memerlukan akses jaringan atau skalabilitas yang tinggi.
        
5. **Apa keuntungan menggunakan middle-tier dalam arsitektur tiga tingkat? Sebutkan tiga keuntungan utama.**
    - **Jawaban:**
        - **Isolasi Logika Bisnis:** Memisahkan logika bisnis dari klien dan server basis data, meningkatkan modularitas dan pemeliharaan.
        - **Pengelolaan Transaksi:** Middle-tier dapat mengelola transaksi secara efisien, memastikan konsistensi data dan integritas transaksi.
        - **Peningkatan Keamanan:** Menyediakan lapisan keamanan tambahan untuk melindungi data sensitif dan mengelola autentikasi dan otorisasi pengguna.
        
---
---
#UAS_Database 

