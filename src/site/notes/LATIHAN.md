---
{"sticker":"emoji//1f624","dg-publish":true,"dg_publish":true,"permalink":"/latihan/","dgPassFrontmatter":true,"noteIcon":""}
---

[DATABASE](DATABASE)
### Soal Ujian Akhir Database

#### Kisi-Kisi:
1. **Esai**: Arsitektur Database
2. **Cases**:
   - **SQL Command 1**: Join
   - **SQL Command 2**: Except
   - **SQL Command 3**: Grant, Revoke, View
   - **SQL Command 4**: Subquery and Aggregation (IN, EXISTS)
   - **DBMS Architecture**
   - **Data Warehouse**

# Soal Cases:
## **Case 1: Join**

Diberikan tabel berikut:

**Tabel Client:**

| clientNo | fName | lName |
|----------|-------|-------|
| C001     | John  | Doe   |
| C002     | Jane  | Smith |

**Tabel Viewing:**

| clientNo | propertyNo | comment    |
|----------|------------|------------|
| C001     | P001       | Interested |
| C003     | P002       | Not Sure   |

**Tabel PropertyForRent:**

| propertyNo | pCity         | rent |
|------------|---------------|------|
| P001       | New York      | 1500 |
| P002       | San Francisco | 2000 |
| P003       | Los Angeles   | 1800 |

**Tabel Staff:**

| staffNo | fName  | lName  | branchNo |
|---------|--------|--------|----------|
| S001    | Alice  | Brown  | B001     |
| S002    | Bob    | Johnson| B002     |
| S003    | Charlie| Davis  | B003     |

**Tabel Branch:**

| branchNo | bCity         |
|----------|---------------|
| B001     | New York      |
| B002     | Los Angeles   |
| B003     | San Francisco |

**Pertanyaan:**
1. Buat query untuk menampilkan nama semua klien yang telah melihat properti beserta komentarnya.
2. Buat query untuk menampilkan cabang dan properti yang ada di kota yang sama, serta cabang yang tidak memiliki kecocokan.

**Kunci Jawaban:**
1. **Inner Join:**

```sql
SELECT c.clientNo, c.fName, c.lName, v.propertyNo, v.comment
FROM Client c
INNER JOIN Viewing v ON c.clientNo = v.clientNo;
```

**Hasil:**

| clientNo | fName | lName | propertyNo | comment    |
|----------|-------|-------|------------|------------|
| C001     | John  | Doe   | P001       | Interested |

2. **Left Outer Join:**

```sql
SELECT b.branchNo, b.bCity, p.propertyNo, p.pCity, p.rent
FROM Branch b
LEFT JOIN PropertyForRent p ON b.bCity = p.pCity;
```

**Hasil:**

| branchNo | bCity         | propertyNo | pCity         | rent |
|----------|---------------|------------|---------------|------|
| B001     | New York      | P001       | New York      | 1500 |
| B002     | Los Angeles   | P003       | Los Angeles   | 1800 |
| B003     | San Francisco | P002       | San Francisco | 2000 |

## **Case 2: Except**

**Pertanyaan:**
1. Buat query untuk menampilkan semua kota yang memiliki kantor cabang tetapi tidak memiliki properti.

**Kunci Jawaban:**

```sql
(SELECT bCity AS city FROM Branch)
EXCEPT
(SELECT pCity AS city FROM PropertyForRent);
```

**Hasil:**

| city      |
|-----------|
| San Francisco |

## **Case 3: Grant, Revoke, View**

**Pertanyaan:**
1. Buat perintah SQL untuk memberikan hak akses SELECT dan INSERT pada tabel `pegawai` kepada pengguna `user1`.
2. Buat perintah SQL untuk mencabut hak akses INSERT pada tabel `pegawai` dari pengguna `user1`.
3. Buat view untuk menampilkan informasi staff yang bekerja di cabang tertentu.

**Kunci Jawaban:**
1. **GRANT:**

```sql
GRANT SELECT, INSERT ON pegawai TO user1;
```

2. **REVOKE:**

```sql
REVOKE INSERT ON pegawai FROM user1;
```

3. **View:**

```sql
CREATE VIEW StaffInBranch AS
SELECT s.staffNo, s.fName, s.lName, b.bCity
FROM Staff s
JOIN Branch b ON s.branchNo = b.branchNo;
```

## **Case 4: Subquery and Aggregation (IN, EXISTS)**

**Pertanyaan:**
1. Buat query untuk menampilkan staff yang bekerja di cabang di kota 'New York'.
2. Buat query untuk menampilkan rata-rata gaji staff di setiap cabang.

**Kunci Jawaban:**
1. **Subquery IN:**

```sql
SELECT staffNo, fName, lName
FROM Staff
WHERE branchNo = (SELECT branchNo FROM Branch WHERE bCity = 'New York');
```

**Hasil:**

| staffNo | fName | lName  |
|---------|-------|--------|
| S001    | Alice | Brown  |

2. **Aggregation:**

```sql
SELECT branchNo, AVG(salary) AS avgSalary
FROM Staff
GROUP BY branchNo;
```

# Soal Esai:
1. **Jelaskan konsep arsitektur tiga tingkat (Three-Level Architecture) dalam database berdasarkan model ANSI-SPARC. Berikan contoh sederhana untuk masing-masing tingkat.**

## Esai: DBMS Architecture

**Pertanyaan:**
1. Jelaskan konsep dasar dari arsitektur client-server dua tingkat (two-tier) dan tiga tingkat (three-tier) dalam DBMS. Apa kelebihan dan kekurangan dari masing-masing arsitektur tersebut?

**Kunci Jawaban:**
1. **Arsitektur Client-Server Dua Tingkat:**
   - **Konsep:** Klien (tier 1) mengelola antarmuka pengguna dan menjalankan aplikasi. Server (tier 2) menyimpan basis data dan DBMS.
   - **Kelebihan:** 
     - Akses lebih luas ke basis data yang ada.
     - Peningkatan kinerja.
     - Pengurangan biaya perangkat keras dan komunikasi.
     - Peningkatan konsistensi.
   - **Kekurangan:** 
     - Ketergantungan pada jaringan.
     - Administrasi lebih kompleks.

2. **Arsitektur Client-Server Tiga Tingkat:**
   - **Konsep:** Ditujukan untuk skalabilitas perusahaan, memisahkan lapisan antarmuka pengguna, logika bisnis, dan penyimpanan data.
   - **Kelebihan:**
     - Client "tipis" memerlukan perangkat keras yang lebih murah.
     - Pemeliharaan aplikasi terpusat.
     - Lebih mudah memodifikasi atau mengganti satu lapisan tanpa mempengaruhi yang lain.
     - Implementasi load balancing lebih mudah.
     - Cocok dengan lingkungan web.
   - **Kekurangan:** 
     - Kompleksitas lebih tinggi dalam pengembangan dan pemeliharaan.

## Esai: Data Warehouse

**Pertanyaan:**
1. Jelaskan proses ETL (Extract, Transform, Load) dalam konteks data warehousing dan berikan contoh untuk setiap tahapannya.

**Kunci Jawaban:**
1. **ETL (Extract, Transform, Load):**
   - **Extract:** Mengambil data dari berbagai sumber.
     - Contoh: Mengambil data penjualan dari sistem ERP.
   - **Transform:** Menerapkan serangkaian aturan atau fungsi pada data yang diekstraksi.
     - Contoh: Mengubah format tanggal menjadi format standar, membersihkan data dari duplikat.
   - **Load:** Memuat data ke dalam data warehouse.
     - Contoh: Memasukkan data penjualan yang sudah dibersihkan ke dalam tabel penjualan di data warehouse.

