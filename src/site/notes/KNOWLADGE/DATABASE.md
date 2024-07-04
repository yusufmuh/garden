---
{"sticker":"emoji//1f4c5","dg-publish":true,"dg-home":false,"aliases":["SQL"],"permalink":"/knowladge/database/","dgPassFrontmatter":true,"noteIcon":"","created":"2024-06-13T14:23:33.881+07:00","updated":"2024-07-04T10:54:34.207+07:00"}
---

```widgets
type: countdown
date: 2024-07-09 15:00:00
to: 2024-07-01 11:09:20
```
---


# 🗄SQL SERVER
#1_Introduction_to_Databases_and_The_Relational_Model 
#2_Normalization
#3_ER_Modelling 
#4_Enhanced_ER_Modelling 
#5_SQL_Data_Definition_Introduction_to_Views 
#6_SQL_Data_Manipulation_Basic_Queries_1 
#7_SQL_Data_Manipulation_Basic_Queries_2

---
#UAS 

# SQL COMMAND
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

    `REVOKE privilege [, privilege...] ON object FROM user [, user...];`
    
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

    
- Contoh pembuatan VIEW:
    
    sql
    
    Salin kode
    
    `CREATE VIEW EmployeeView AS SELECT employee_id, name, department_id FROM Employees WHERE department_id = 101;`
    

**3. Manfaat Menggunakan VIEW:**

- **Abstraksi Data:** Menyembunyikan kompleksitas query dari pengguna.
- **Keamanan Data:** Membatasi akses ke kolom dan baris tertentu dalam tabel.
- **Konsistensi:** Memastikan data yang sama diakses dengan cara yang sama oleh semua pengguna.
- **Kemudahan Penggunaan:** Menyederhanakan query yang sering digunakan.

**4. Modifikasi VIEW:**

- VIEW dapat dimodifikasi menggunakan perintah `CREATE OR REPLACE VIEW` atau dengan menghapus dan membuat kembali VIEW.
    
    sql
    
    Salin kode
    
    `CREATE OR REPLACE VIEW EmployeeView AS SELECT employee_id, name, department_id, salary FROM Employees WHERE department_id = 101;`
    

**5. Menghapus VIEW:**

- VIEW dapat dihapus menggunakan perintah `DROP VIEW`:
    
    sql
    
    Salin kode
    
    `DROP VIEW view_name;`
    

**6. Contoh Penggunaan VIEW:**

- Misalkan kita memiliki tabel `Employees` dan `Departments`, kita dapat membuat VIEW untuk menampilkan informasi karyawan yang hanya berasal dari departemen tertentu.

**Contoh Pembuatan dan Penggunaan VIEW:**



## SQL Server Management


#8_SQL_Data_Manipulation_Multi_Table_Queries 
#9_Security_and_Administration
#10_SQL_Data_Manipulation_Sub_Queries_and_View 
#11_DATABASE_ENVIRONMENT 
#12_Database_Environment_Architectures 
#13_Data_Warehousing_Concepts

## EXECPT
## GRANT
## REVOKE
## VIEW
## IN
## EXISTS
### SUB QUERY
### AGREGATION
Represents a "has-a"
## DBMS Architectures
## DATA WAREHOUSE
