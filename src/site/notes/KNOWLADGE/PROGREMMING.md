---
{"sticker":"lucide//code-2","dg-publish":true,"aliases":["JAVA"],"permalink":"/knowladge/progremming/","dgPassFrontmatter":true,"noteIcon":"","created":"2024-06-13T14:39:34.708+07:00","updated":"2024-07-03T05:01:43.974+07:00"}
---

```widgets
type: countdown
date: 2024-07-03 13:00:00
to: 2024-07-01 11:10:50
```
---
# Java DASAR
![[Java Dasar.pptx]]

# Java OOP
![[Java Object Oriented Programming.pptx]]

# ☕ JAVA
#UAS 

---
#1_Introduction_to_Algorithm 
Dari contoh pseudocode perhitungan rata-rata nilai berikut, buatlah **flowchart dan Diagram NS**
**`BEGIN`**
	`Set total to zero`
	`Set grade_counter to one`
	`While grade_counter is less than or equal to ten`
	`Input the next grade`
	`Add the grade into the total`
	`Set the class_average to the total divided by ten`
	`Print the class_average`
**`END`**

Dengan menggunakan **Pseudo-code dan flowchart**, buatlah:
	- algoritma untuk **menghitung luas segitiga**!
	- sebuah algoritma untuk **mengubah detik menjadi satuan jam dan menit!**
	- sebuah algoritma untuk menerima tiga angka dan menemukan angka maks, min, dan rata-rata!
	- algoritma untuk menghitung luas lingkaran!
	- algoritma untuk menghitung keliling persegi panjang!
	
---
#2_Introduction_to_Java_Programming 
1. Jelaskan tentang **library** di java!
		Library dalam Java adalah **kumpulan kelas, metode, dan sumber daya lain** yang sudah ditulis sebelumnya dan dapat digunakan untuk melakukan tugas-tugas pemrograman umum. Library menyediakan cara untuk menggunakan kembali kode dan mempercepat proses pengembangan dengan menyediakan fungsionalitas standar yang dapat dengan mudah diintegrasikan ke dalam aplikasi. **Library Java biasanya dikemas dalam file JAR (Java ARchive).**
	**Contoh Library Java yang Umum:**
	1. **Java Standard Library:** Bagian dari JDK, termasuk library untuk struktur data, jaringan, file I/O, pengembangan GUI, dll.
	2. **Apache Commons:** Menyediakan komponen Java yang dapat digunakan kembali, seperti koleksi, utilitas file, dan banyak lagi.
	3. **Google Guava:** Menawarkan utilitas untuk koleksi, caching, dukungan primitif, dan banyak lagi.
	4. **JUnit:** Digunakan untuk pengujian unit di Java.

2. Tentukan aturan yang dapat digunakan untuk **create identifier** (Aturan untuk Membuat Identifier dalam Java)
	**Identifier** adalah nama yang diberikan untuk elemen-elemen dalam program Java seperti variabel, kelas, dan metode. Aturan untuk membuat identifier adalah:
	1. Identifier dapat berisi huruf (a-z, A-Z), digit (0-9), underscore (_), dan tanda dolar ($).
	2. Identifier harus dimulai dengan huruf, underscore (_), atau tanda dolar ($).
	3. Identifier tidak boleh dimulai dengan digit.
	4. Identifier tidak boleh menggunakan kata kunci Java (misalnya, `int`, `class`, `static`).
	5. Identifier bersifat case-sensitive (misalnya, `MyVariable` dan `myVariable` adalah berbeda).
	**Contoh:**
	- Valid: `myVariable`, `_temp`, `$value`, `mainMethod`
	- Tidak Valid: `1stVariable`, `class`, `staticVar`

1. Apa fungsi **function of keywords** di java:
- **static:** 
		**:** Menunjukkan bahwa anggota (field atau metode) milik kelas, bukan instance dari kelas. Anggota static dapat diakses tanpa membuat objek dari kelas.
```java
public class MyClass {
    static int counter = 0; // Static field

    static void incrementCounter() { // Static method
        counter++;
    }
}
```
- **final:**
		**:** Digunakan untuk mendeklarasikan konstanta, mencegah overriding metode, dan pewarisan kelas. Ketika variabel dideklarasikan sebagai `final`, nilainya tidak dapat diubah.
```java
public class MyClass {
    final int MAX_VALUE = 100; // Final variable

    final void display() { // Final method
        System.out.println("Metode ini tidak dapat di-overridden");
    }
}

final class MyFinalClass { // Final class
    // Kelas ini tidak dapat diwariskan
}
```
- **class:** 
		**:** Digunakan untuk ***mendeklarasikan kelas***, yang merupakan cetak biru untuk objek. Kelas mendefinisikan field dan metode yang dapat digunakan oleh objek yang dibuat dari kelas.
```java
public class MyClass {
    int myField;

    void myMethod() {
        System.out.println("Hello, World!");
    }
}
```
- **package:** 
		**:** Digunakan untuk ***mengelompokkan kelas*** dan antarmuka yang terkait ke dalam namespace, menyediakan modularitas dan organisasi pada kode. Package juga membantu menghindari konflik nama.
```java
package com.example.myapp;

public class MyClass {
    // Definisi kelas
}
```

1. Jelaskan penggunaan **“String[] args ”** di ***public static void main***!
	Penggunaan `String[] args` dalam `public static void main`
		`String[] args` adalah **array objek** `String` yang menyimpan argumen baris perintah yang diteruskan ke program saat dijalankan. Argumen ini memungkinkan program dijalankan dengan input yang berbeda tanpa mengubah kode sumber.
```java
public class MainClass {
    public static void main(String[] args) {
        if (args.length > 0) {
            System.out.println("Argumen pertama: " + args[0]);
        } else {
            System.out.println("Tidak ada argumen yang diteruskan.");
        }
    }
}
```

2. Apa itu **JVM, JDK, source program, compiler**?
	**1. JVM (Java Virtual Machine)**
	- **Deskripsi:** Mesin virtual yang **mengeksekusi bytecode Jav**a. JVM memungkinkan program Java menjadi platform-independen dengan menyediakan lingkungan eksekusi yang konsisten pada perangkat atau sistem operasi apa pun.
	- **Fungsi:** Menjalankan program Java dan menyediakan fitur seperti ***garbage collection, manajemen memori, dan keamanan**.*

	**2. JDK (Java Development Kit)**
	- **Deskripsi:** ***Kit pengembangan perangkat lunak*** yang diperlukan untuk mengembangkan aplikasi Java. JDK mencakup JRE (Java Runtime Environment), interpreter/loader (Java), compiler (javac), archiver (jar), generator dokumentasi (javadoc), dan alat lain yang diperlukan untuk pengembangan Java.
	- **Fungsi:** Menyediakan alat untuk ***mengkompilasi, debug, dan menjalankan aplikasi Jav***a.

	**3. Program Sumber**
	- **Deskripsi:** ***Kode asli*** yang ditulis oleh programmer dalam bahasa pemrograman tingkat tinggi seperti Java. Kode ini dapat dibaca oleh manusia dan perlu dikompilasi menjadi bytecode atau kode mesin untuk dieksekusi.
	- **Contoh:** File `.java` yang berisi kode Java.

	**4. Compiler**
	- **Deskripsi:** Program yang ***menerjemahkan kode sumber*** yang ditulis dalam ***bahasa pemrograman tingkat tinggi*** menjadi ***bytecode*** atau kode mesin. Dalam Java, compiler (javac) mengonversi file `.java` menjadi file `.class` yang berisi bytecode Java.
	- **Fungsi:** Memeriksa sintaksis kode sumber dan ***mengonversinya ke format yang dapat dieksekusi oleh JVM***.

---
---
#4_BASIC_CLASS 
1. Does any ***method** in the String class* **change the contents of the string**?
		Tidak, **tidak ada metode dalam kelas `String` yang mengubah isi string** karena objek `String` bersifat immutable (tidak dapat diubah). Setiap metode yang tampaknya mengubah string sebenarnya mengembalikan string baru dengan hasil perubahan.
2. Create a program to determine whether a character is **alphanumeric?**
```java
public class AlphanumericCheck {
    public static void main(String[] args) {
        char ch = 'a'; // Ganti dengan karakter yang ingin dicek
        boolean isAlphanumeric = Character.isLetterOrDigit(ch);
        
        if (isAlphanumeric) {
            System.out.println(ch + " adalah karakter alfanumerik.");
        } else {
            System.out.println(ch + " bukan karakter alfanumerik.");
        }
    }
}
```
3. Create a program to determine whether a character is in **lowercase or uppercase**?
```java
public class CaseCheck {
    public static void main(String[] args) {
        char ch = 'A'; // Ganti dengan karakter yang ingin dicek
        
        if (Character.isLowerCase(ch)) {
            System.out.println(ch + " adalah huruf kecil.");
        } else if (Character.isUpperCase(ch)) {
            System.out.println(ch + " adalah huruf besar.");
        } else {
            System.out.println(ch + " bukan huruf kecil maupun besar.");
        }
    }
}
```
4. Describe how to *convert* **hexadecimal to decimal**?
	Untuk mengkonversi angka hexadecimal ke desimal, Anda dapat menggunakan langkah-langkah berikut:
	1. Tuliskan angka hexadecimal.
	2. Mulai dari digit paling kanan, kalikan setiap digit dengan 16 pangkat posisi digit (dimulai dari 0).
	3. Jumlahkan semua hasil kali tersebut untuk mendapatkan nilai desimal.
	Contoh: Hexadecimal "1A3"
		- 3 * (16^0) = 3
		- A (yang setara dengan 10 dalam desimal) * (16^1) = 160
		- 1 * (16^2) = 256
		- Jumlahkan hasilnya: 3 + 160 + 256 = 419 (Desimal)
		
5. Evaluate the following method calls:
	- Math.**pow**(2,2)
		- Hasil: 4.0
	- Math.**max**(2, Math.**min**(3,4))
		- Hasil: 3
	- Math.**round**(2.5F)
		- Hasil: 3
	- Math.**ceil**(-9.49)
		- Hasil: -9.0
	- Math.**floor**(7.5)
		- Hasil: 7.0
		
1. Describe and give example for each **method of String**
	**- contains**
		- : Memeriksa apakah suatu string mengandung urutan karakter tertentu.
		`- String str = "Hello, world!"; 
		`- boolean result = str.contains("world");` // result is true
	**- concat**
		- **:** Menggabungkan string yang ditentukan ke akhir string saat ini.
		`- String str1 = "Hello, ";` 
		`- String str2 = "world!";` 
		`- String result = str1.concat(str2);` // result is "Hello, world!"
	**- compareTo**
		- **:** Membandingkan dua string secara leksikografis.
		`- String str1 = "apple";`
		`- String str2 = "banana";`
		`- int result = str1.compareTo(str2);` // result is negative because "apple" is less than "banana"
	**- format**
		- **:** Mengembalikan string yang diformat menggunakan format string dan argumen yang ditentukan.
		`- String name = "John";`
		`- int age = 25;`
		`- String formattedString = String.format("Name: %s, Age: %d", name, age);` // result is "Name: John, Age: 25"
	**- charAt**
		- **:** Mengembalikan karakter pada indeks yang ditentukan.
		`- String str = "Hello";`
		`- char result = str.charAt(1);` // result is 'e'
	**- replace**
		- **:** Mengganti setiap substring dari string ini yang cocok dengan urutan target literal dengan urutan penggantian literal yang ditentukan.
		`- String str = "Hello, world!";`
		`- String result = str.replace("world", "Java");` // result is "Hello, Java!"
	**- substing**
		- **:** Mengembalikan string baru yang merupakan substring dari string ini.
		`- String str = "Hello, world!";
		`- String result = str.substring(7, 12);` // result is "world"
	**- trim**
		- **:** Mengembalikan string yang nilainya adalah string ini, dengan menghapus spasi di awal dan akhir.
		`- String str = "   Hello, world!   ";`
		`- String result = str.trim();` // result is "Hello, world!"
	**- toCharArray**
		- **:** Mengonversi string ini ke array karakter baru.
		`- String str = "Hello";`
		`- char[] result = str.toCharArray();` // result is ['H', 'e', 'l', 'l', 'o']
	**- split**
		- **:** Membagi string ini di sekitar kecocokan ekspresi reguler yang diberikan.
		`- String str = "apple,banana,orange";`
		`- String[] result = str.split(",");` // result is ["apple", "banana", "orange"]
	**- toLowerCase**
		- **:** Mengonversi semua karakter dalam string ini ke huruf kecil menggunakan aturan lokal default.
		`- String str = "Hello, World!";`
		`- String result = str.toLowerCase();` // result is "hello, world!"
	**- toUpperCase**
		- **:** Mengonversi semua karakter dalam string ini ke huruf besar menggunakan aturan lokal default.
		`- String str = "Hello, World!";`
		`- String result = str.toUpperCase();` // result is "HELLO, WORLD!"

---
#5_Arithmetic_Operation
1. Can **different types of numeric values** be ***used together*** in computation?
	  Ya, **tipe nilai numerik yang berbeda** dapat ***digunakan bersama*** dalam perhitungan. Dalam Java, ketika operasi aritmatika melibatkan tipe data yang berbeda (misalnya, `int` dan `double`), Java akan melakukan konversi tipe (type casting) secara otomatis untuk memastikan operasi tersebut dilakukan dengan benar.
2. Assume that ***int*** **a = 1** and ***double*** **d = 1.0** and that each expression is independent. What are the results of the following expressions?
	**a = 46 % 9 + 4 * 4 – 2**
	- `46 % 9` adalah 1 (sisa pembagian 46 dengan 9)
	- `4 * 4` adalah 16
	- Jadi, ekspresi menjadi `1 + 16 - 2` yang sama dengan `15`
	- Hasil: `a = 15`
	**a = 45 + 43 % 5 * (23 * 3 % 2)**
	- `43 % 5` adalah 3 (sisa pembagian 43 dengan 5)
	- `23 * 3` adalah 69
	- `69 % 2` adalah 1 (sisa pembagian 69 dengan 2)
	- Jadi, ekspresi menjadi `45 + 3 * 1` yang sama dengan `45 + 3` yaitu `48`
	- Hasil: `a = 48`
	**a %= 3 / a + 3**  (dengan `a` sekarang adalah 48):
	- `3 / a` adalah `3 / 48` yang sama dengan 0 (pembagian bilangan bulat)
	- `0 + 3` adalah 3
	- `a %= 3` sama dengan `a = a % 3` yaitu `48 % 3` adalah 0
	- Hasil: `a = 0`
	**d += 1.5 * 3 + (++a)**  (dengan `a` sekarang adalah 0 dan `d` adalah 1.0):
	- `++a` adalah `1` (**pre-increment** `a` dari 0 **menjadi 1**)
	- `1.5 * 3` adalah 4.5
	- Jadi, ekspresi menjadi `d += 4.5 + 1` yang sama dengan `d += 5.5` yaitu `1.0 + 5.5` sama dengan 6.5
	- Hasil: `d = 6.5`

3. Are the following statements correct? If so, show the output.
	**System.out.println(“25 / 4 is “ + 25 / 4);** 
		 `25 / 4` adalah 6 (pembagian bilangan bulat)
	     Output: `25 / 4 is 6`
	**System.out.println(“25 / 4.0 is “ + 25 / 4.0);**
			`25 / 4.0` adalah 6.25 (pembagian melibatkan bilangan `double`)
			Output: `25 / 4.0 is 6.25`
	**System.out.println(“3 * 2 / 4 is “ + 3 * 2 / 4);**
			`3 * 2` adalah 6
			`6 / 4` adalah 1 (pembagian bilangan bulat)
			Output: `3 * 2 / 4 is 1`
	**System.out.println(“3.0 * 2 / 4 is “ + 3.0 * 2 / 4);**
			`3.0 * 2` adalah 6.0
			`6.0 / 4` adalah 1.5 (pembagian melibatkan bilangan `double`)
			Output: `3.0 * 2 / 4 is 1.5`
 **Ringkasan Hasil Evaluasi:**
	1. **`a = 46 % 9 + 4 * 4 - 2`** -> `a = 15`
	2. **`a = 45 + 43 % 5 * (23 * 3 % 2)`** -> `a = 48`
	3. **`a %= 3 / a + 3`** -> `a = 0`
	4. **`d += 1.5 * 3 + (++a)`** -> `d = 6.5`
**Output Pernyataan:**
	1. `System.out.println("25 / 4 is " + 25 / 4);` -> `25 / 4 is 6`
	2. `System.out.println("25 / 4.0 is " + 25 / 4.0);` -> `25 / 4.0 is 6.25`
	3. `System.out.println("3 * 2 / 4 is " + 3 * 2 / 4);` -> `3 * 2 / 4 is 1`
	4. `System.out.println("3.0 * 2 / 4 is " + 3.0 * 2 / 4);` -> `3.0 * 2 / 4 is 1.5`
	
4. Identify and fix the errors in the following code:
![Pasted image 20240702194329.png](/img/user/Pasted%20image%2020240702194329.png)
	1. Variabel `i` dideklarasikan tetapi tidak diinisialisasi, yang akan menyebabkan kesalahan kompilasi.
	2. Variabel `k` diinisialisasi dengan nilai double, tetapi dideklarasikan sebagai integer.
	3. Mencoba melakukan aritmatika dengan variabel `i` yang belum diinisialisasi saat menginisialisasi `j`.
Berikut adalah versi kode yang telah diperbaiki:
```java
public class Test {
    public static void main(String[] args) {
        int i = 0;  // Inisialisasi i
        double k = 100.0;  // Ubah k menjadi double
        int j = i + 1;  // j = i + 1 valid sekarang karena i telah diinisialisasi

        System.out.println("j is " + j + " and k is " + k);
    }
}
```
Ringkasan perbaikan:
	1. Menginisialisasi `i` dengan 0.
	2. Mengubah tipe `k` dari `int` ke `double` agar sesuai dengan nilai yang diberikan `100.0`.
	3. Sekarang `i` telah diinisialisasi, penugasan ke `j` menjadi valid.

5. Can the following conversions involving casting be allowed? If so, find the converted result.
![Pasted image 20240702195834.png](/img/user/Pasted%20image%2020240702195834.png)
```java
char c = 'A';
int i = (int) c;
```
- `c` diberi nilai karakter 'A'.
- Casting `c` ke `int` menghasilkan nilai ASCII dari 'A', yaitu 65.
- Hasil: `i` akan menjadi 65.
```java
float f = 1000.34F;
int i = (int) f;
```
- `f` diberi nilai float 1000.34.
- Casting `f` ke `int` menghasilkan pemotongan bagian desimal, sehingga `i` akan menjadi 1000.
- Hasil: `i` akan menjadi 1000.
```java
double d = 1000.34;
int i = (int) d;
```
- `d` diberi nilai double 1000.34.
- Casting `d` ke `int` menghasilkan pemotongan bagian desimal, sehingga `i` akan menjadi 1000.
- Hasil: `i` akan menjadi 1000.
```java
int i = 97;
char c = (char) i;
```
- `i` diberi nilai integer 97.
- Casting `i` ke `char` menghasilkan karakter yang sesuai dengan nilai ASCII 97, yaitu 'a'.
- Hasil: `c` akan menjadi 'a'.
**Ringkasan hasil:**
1. `int i = (int) 'A';` menghasilkan `i = 65`.
2. `int i = (int) 1000.34F;` menghasilkan `i = 1000`.
3. `int i = (int) 1000.34;` menghasilkan `i = 1000`.
4. `char c = (char) 97;` menghasilkan `c = 'a'`.

---
#3_Data_Type_and_Input/Output
#6_Logic_and_Relational_Operation
1. Assuming that x is 1, show the result of the following Boolean expressions.
	 **(true) && (3 > 4)** 
	- `(3 > 4)` adalah `false`.
	- `true && false` adalah `false`.
	Hasil: `false`

	**!(x > 0) && (x > 0)**
	- x=1x = 1x=1
	- `(x > 0)` adalah `true`.
	- `!(x > 0)` adalah `false`.
	- `false && true` adalah `false`.
	Hasil: `false`

	**(x != 1) == !(x == 1)**
	- x=1x = 1x=1
	- `(x != 1)` adalah `false`.
	- `!(x == 1)` adalah `!(true)` yaitu `false`.
	- `false == false` adalah `true`.
	Hasil: `true`

	**x >= 0) || (x < 0)**
	- x=1x = 1x=1
	- `(x >= 0)` adalah `true`.
	- `(x < 0)` adalah `false`.
	- `true || false` adalah `true`.
	Hasil: `true`

	**Urutan Precedensi Operator Boolean:**
	- `!` (NOT)
	- `&&` (AND)
	- `||` (OR)

2. List the precedence order of the Boolean operators. Evaluate the following expressions:
	**2 * 2 – 3 > 2 && 4 – 2 > 5**
	Evaluasi aritmatika terlebih dahulu:
    - `2 * 2` adalah `4`.
    - `4 - 3` adalah `1`.
    - `4 - 2` adalah `2`.
	Evaluasi ekspresi Boolean:
    - `1 > 2` adalah `false`.
    - `2 > 5` adalah `false`.
    - `false && false` adalah `false`.
	Hasil: `false`

	**2 * 2 – 3 > 2 || 4 – 2 > 5**
	- Evaluasi aritmatika: `2 * 2 - 3` -> `4 - 3` -> `1`
    - Evaluasi aritmatika: `4 - 2` -> `2`
    - Evaluasi ekspresi Boolean: `1 > 2` -> `false`
    - Evaluasi ekspresi Boolean: `2 > 5` -> `false`
    - Evaluasi keseluruhan: `false || false` -> `false`
	Hasil: `false`

**Rekapitulasi Hasil Evaluasi:**
1. `(true) && (3 > 4)` -> `false`
2. `!(x > 0) && (x > 0)` -> `false`
3. `(x != 1) == !(x == 1)` -> `true`
4. `(x >= 0) || (x < 0)` -> `true`
5. `2 * 2 - 3 > 2 && 4 - 2 > 5` -> `false`
6. `2 * 2 - 3 > 2 || 4 - 2 > 5` -> `false`
Dengan demikian, kita telah mengevaluasi semua ekspresi yang diberikan dan memastikan bahwa hasilnya konsisten dengan urutan prioritas operator dan logika evaluasi yang benar.

---
#7_Selection_Statement
1. Suppose x = 3 and y = 2; show the output, if any, of the following code. What is the output if x = 3 and y = 4? What is the output of x = 2 and y = 2?
![Pasted image 20240702153257.png](/img/user/Pasted%20image%2020240702153257.png)
```java
if (x > 2) {
    if (y > 2) {
        z = x + y;
        System.out.println("z is " + z);
    }
} else {
    System.out.println("x is " + x);
}
```
**Kasus 1: x=3x = 3x=3 dan y=2y = 2y=2**
- `x > 2` benar.
- `y > 2` salah.
- Karena `y > 2` salah, bagian dalam dari kondisi `if (y > 2)` tidak dieksekusi.
- Tidak ada pernyataan yang dicetak.
**Output:**
Tidak ada output.

**Kasus 2: x=3x = 3x=3 dan y=4y = 4y=4**
- `x > 2` benar.
- `y > 2` benar.
- `z = x + y` dieksekusi dengan z=3+4=7z = 3 + 4 = 7z=3+4=7.
- `System.out.println("z is " + z);` dieksekusi dan mencetak `z is 7`.
**Output:**
z is 7

**Kasus 3: x=2x = 2x=2 dan y=2y = 2y=2**
- `x > 2` salah.
- `else` bagian dari kondisi `if (x > 2)` dieksekusi.
- `System.out.println("x is " + x);` dieksekusi dan mencetak `x is 2`.
**Output:**
x is 2
### Kesimpulan Output:
1. x=3x = 3x=3 dan y=2y = 2y=2 -> Tidak ada output.
2. x=3x = 3x=3 dan y=4y = 4y=4 -> `z is 7`
3. x=2x = 2x=2 dan y=2y = 2y=2 -> `x is 2`

2. What is y after the following switch statement is executed?
![Pasted image 20240702153659.png](/img/user/Pasted%20image%2020240702153659.png)
```java
x = 3;
y = 3;
switch (x + 3) {
    case 6: 
        y = 1;
    default: 
        y += 1;
}
```
- **Nilai Awal:**
    - `x = 3`
    - `y = 3`
- **Pernyataan `switch`:**
    - Ekspresi dalam `switch` adalah `x + 3`, yang berarti `3 + 3 = 6`.
- **Pencocokan `case`:**
    - `case 6:` cocok karena ekspresi `switch` adalah 6.
    - `y = 1;` dieksekusi, jadi `y` sekarang adalah 1.
- **Pernyataan `default`:**
    - Karena tidak ada `break` setelah `case 6:`, eksekusi akan terus ke pernyataan `default`.
    - `y += 1;` dieksekusi, yang berarti `y = y + 1 = 1 + 1 = 2`.
 **Nilai Akhir:**
- Setelah eksekusi `switch` selesai, nilai `y` adalah 2.
**Kesimpulan:**
Nilai `y` setelah pernyataan `switch` dieksekusi adalah 2.

3. Use a switch statement to rewrite the following if statement
![Pasted image 20240702154004.png](/img/user/Pasted%20image%2020240702154004.png)
- Pernyataan `if-else if`:
```java
if (a == 1) {
    x += 5;
} else if (a == 2) {
    x += 10;
} else if (a == 3) {
    x += 16;
} else if (a == 4) {
    x += 34;
}
```
- Pernyataan `switch`:
```java
switch (a) {
    case 1:
        x += 5;
        break;
    case 2:
        x += 10;
        break;
    case 3:
        x += 16;
        break;
    case 4:
        x += 34;
        break;
    // Tambahkan default case jika diperlukan
    default:
        break;
}
```
**Penjelasan:**
- **`switch (a)`**: Menentukan variabel `a` yang akan diperiksa.
- **`case`**: Setiap `case` cocok dengan nilai `a` yang berbeda, mirip dengan kondisi `if`.
- **`break`**: Digunakan untuk menghentikan eksekusi lebih lanjut dalam `switch` setelah kasus yang cocok dieksekusi. Tanpa `break`, eksekusi akan berlanjut ke pernyataan berikutnya (fall-through), yang biasanya tidak diinginkan dalam kasus ini.
- **`default`**: Opsional, digunakan jika tidak ada `case` yang cocok. Dapat dihilangkan jika tidak diperlukan.
Dengan mengonversi pernyataan `if-else if` menjadi `switch`, kita mendapatkan struktur yang lebih bersih dan lebih mudah dibaca ketika kita memiliki banyak kondisi berdasarkan nilai yang sama.

4. Use a ternary operator to rewrite the following if statement
![Pasted image 20240702154241.png](/img/user/Pasted%20image%2020240702154241.png)
- Pernyataan `if-else`:
```java
if (x > 65) {
    System.out.println("Passed");
} else {
    System.out.println("Failed");
}
```
- Pernyataan dengan Operator Ternary:
```java
System.out.println(x > 65 ? "Passed" : "Failed");
```
 **Penjelasan:**
- **`x > 65`**: Kondisi yang diperiksa.
- **`? "Passed"`**: Jika kondisi benar (`true`), cetak "Passed".
- **`: "Failed"`**: Jika kondisi salah (`false`), cetak "Failed".
Operator ternary adalah ***cara singkat untuk menulis pernyataan kondisional sederhana*** dan sangat berguna untuk ekspresi yang singkat seperti ini.

5. Create a program to calculate the final grade of Bina Nusantara Student by following this rule:
	Assignment (20%), Mid-Exam (30%), Final-Exam (50%)
	85 – 100 = A
	75 – 84   = B
	65 – 74   = C
	55 – 64   = D
	<55          = E![Pasted image 20240702154449.png](/img/user/Pasted%20image%2020240702154449.png)
```java
import java.util.Scanner;

public class GradeCalculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Input nilai dari pengguna
        System.out.print("Assignment point[0..100]: ");
        double assignment = scanner.nextDouble();

        System.out.print("Mid-Exam point[0..100]: ");
        double midExam = scanner.nextDouble();

        System.out.print("Final-Exam point[0..100]: ");
        double finalExam = scanner.nextDouble();

        // Hitung nilai akhir
        double finalScore = (assignment * 0.2) + (midExam * 0.3) + (finalExam * 0.5);

        // Tentukan grade
        char grade;
        if (finalScore >= 85) {
            grade = 'A';
        } else if (finalScore >= 75) {
            grade = 'B';
        } else if (finalScore >= 65) {
            grade = 'C';
        } else if (finalScore >= 55) {
            grade = 'D';
        } else {
            grade = 'E';
        }

        // Tampilkan hasil
        System.out.printf("Your Score: %.1f\n", finalScore);
        System.out.println("Your Grade: " + grade);
    }
}
```
- **Input Nilai dari Pengguna**:
    - Menggunakan `Scanner` untuk menerima input nilai tugas, ujian tengah semester, dan ujian akhir dari pengguna.
    - `System.out.print` digunakan untuk menampilkan prompt bagi pengguna.
- **Hitung Nilai Akhir**:
    - Menggunakan formula yang diberikan untuk menghitung nilai akhir berdasarkan persentase kontribusi masing-masing komponen:
        - Nilai Tugas (20%)
        - Nilai Ujian Tengah Semester (30%)
        - Nilai Ujian Akhir (50%)
- **Tentukan Grade**:
    - Menggunakan `if-else if` untuk menentukan grade berdasarkan nilai akhir.
    - Rentang nilai untuk setiap grade:
        - `A` jika nilai akhir >= 85
        - `B` jika nilai akhir antara 75 dan 84
        - `C` jika nilai akhir antara 65 dan 74
        - `D` jika nilai akhir antara 55 dan 64
        - `E` jika nilai akhir < 55
- **Tampilkan Hasil**:
    - Menggunakan `System.out.printf` untuk menampilkan nilai akhir dengan satu angka di belakang desimal.
    - Menggunakan `System.out.println` untuk menampilkan grade.
Dengan program ini, Anda dapat menghitung nilai akhir dan menentukan grade mahasiswa berdasarkan nilai tugas, ujian tengah semester, dan ujian akhir.

---
#8_Iteration_Statement 
1. What are the differences between a **while loop** and a **do-while loop**? Convert the following while loop into a do-while loop.
![Pasted image 20240702150949.png](/img/user/Pasted%20image%2020240702150949.png)

```java
int i = 1;
while (i < 10) {
    if (i % 2 == 0) {
        System.out.println(i);
    }
    i++;
}
```

```java
int i = 1;
while (i < 10) {
    if (i % 2 == 0) {
        System.out.println(i++);
    } else {
        i++;
    }
}
```

```java
int i = 1;
while (i < 10) {
    if ((i++) % 2 == 0) {
        System.out.println(i);
    }
}
```
**-Perbedaan Hasil:**
- **Potongan Kode 1:** Mencetak bilangan genap dari 1 sampai 9.
- **Potongan Kode 2:** Mencetak bilangan genap dari 1 sampai 9, namun nilai `i` dicetak sebelum diincrement (sehingga menghasilkan bilangan ganjil setelah increment).
- **Potongan Kode 3:** Mencetak nilai `i` setelah diincrement jika nilai awal `i` adalah genap, sehingga mencetak bilangan ganjil dari 2 sampai 10.

2. Do the following two loops result in the **same value in sum**?
![Pasted image 20240702150934.png](/img/user/Pasted%20image%2020240702150934.png)
Ya, kedua loop menghasilkan nilai yang sama untuk variabel `sum`.
```java
int sum = 0;
for (int i = 0; i < 10; ++i) {
    sum += i;
}
```
**Loop Pertama (`++i`)**:
- Variabel `i` diincrement sebelum evaluasi ekspresi dalam loop body.
- Namun, dalam konteks loop for, urutan inkrementasi (`++i` atau `i++`) pada bagian "update" dari for loop tidak mempengaruhi hasil akhir karena loop body dieksekusi setelah pengecekan kondisi dan inkrementasi terjadi setelah eksekusi body loop.
```java
int sum = 0;
for (int i = 0; i < 10; i++) {
    sum += i;
}
```
**Loop Kedua (`i++`)**:
- Variabel `i` diincrement setelah evaluasi ekspresi dalam loop body.
- Sama seperti loop pertama, dalam konteks loop for, urutan inkrementasi pada bagian "update" dari for loop tidak mempengaruhi hasil akhir.
Dalam kedua loop, nilai `i` akan bervariasi dari 0 hingga 9, dan setiap nilai `i` akan ditambahkan ke variabel `sum`. Oleh karena itu, hasil akhir dari `sum` akan sama dalam kedua loop tersebut.
Untuk lebih jelasnya, mari kita hitung nilai `sum` setelah loop selesai:
- `sum = 0 + 1 + 2 + 3 + 4 + 5 + 6 + 7 + 8 + 9 = 45`
### Kesimpulan:
Kedua loop menghasilkan nilai `sum` yang sama, yaitu **45.**

3. What does the following statement do?
	for( ;  ; ){
	  do something;
	}
Pernyataan `for ( ; ; ) { do something; }` dalam Java adalah loop for tanpa kondisi awal, kondisi perulangan, atau pernyataan increment/decrement. Ini menciptakan loop tak terbatas yang akan terus berjalan tanpa henti, kecuali jika diinterupsi oleh pernyataan `break`, `return`, `throw`, atau peristiwa eksterna (misalnya, penghentian program oleh pengguna).
Berikut adalah penjelasan rinci:
1. **Kondisi Awal (Initialization)**: Bagian ini biasanya digunakan untuk menginisialisasi variabel sebelum loop dimulai. Dalam kasus ini, tidak ada kondisi awal, sehingga tidak ada inisialisasi yang dilakukan.
2. **Kondisi Perulangan (Condition)**: Bagian ini biasanya berisi kondisi yang harus benar agar loop terus berjalan. Karena tidak ada kondisi yang diberikan, loop akan dianggap selalu benar (`true`), sehingga loop akan berjalan tanpa henti.
3. **Increment/Decrement (Iteration Expression)**: Bagian ini biasanya digunakan untuk mengubah nilai variabel setelah setiap iterasi loop. Dalam kasus ini, tidak ada pernyataan increment atau decrement.
4. **Loop Body (do something)**: Bagian ini berisi kode yang akan dieksekusi pada setiap iterasi loop.
Berikut adalah contoh sederhana dari loop tak terbatas:
```java
public class InfiniteLoop {
    public static void main(String[] args) {
        for ( ; ; ) {
            System.out.println("This will print forever");
        }
    }
}
```
**Catatan:** Loop seperti ini harus digunakan dengan hati-hati karena dapat menyebabkan program tidak pernah berhenti, menghabiskan sumber daya sistem, dan membuat program tidak responsif. Biasanya, loop tak terbatas ini diinterupsi dengan pernyataan `break` ketika suatu kondisi tertentu tercapai.

Contoh loop tak terbatas yang dihentikan dengan `break`:
```java
public class BreakInfiniteLoop {
    public static void main(String[] args) {
        int counter = 0;
        for ( ; ; ) {
            System.out.println("Counter: " + counter);
            counter++;
            if (counter >= 10) {
                break;  // Loop berhenti ketika counter mencapai 10
            }
        }
    }
}
```
Dalam contoh ini, loop akan berhenti setelah mencetak nilai `counter` dari 0 hingga 9, dan kemudian keluar dari loop ketika `counter` mencapai 10.

4. Can you always convert a while loop into a for loop? Convert the following while loop into a for loop.
![Pasted image 20240702150904.png](/img/user/Pasted%20image%2020240702150904.png)
Ya, kita hampir selalu bisa mengonversi loop `while` menjadi loop `for`. Berikut adalah contoh kode dari loop `while` yang Anda berikan, dan konversinya menjadi loop `for`:
### Loop `while`:
```java
int i = 1;
int sum = 0;
while (sum < 10000) {
    sum = sum + i;
    i++;
}
```
### Loop `for`:
```java
int sum = 0;
for (int i = 1; sum < 10000; i++) {
    sum = sum + i;
}
```
- **Inisialisasi (Initialization)**:
    - Pada loop `while`, inisialisasi dilakukan sebelum loop dengan `int i = 1;` dan `int sum = 0;`.
    - Pada loop `for`, inisialisasi `int i = 1;` dilakukan di bagian pertama dari pernyataan `for`.
- **Kondisi (Condition)**:
    - Pada loop `while`, kondisi `sum < 10000` ditulis sebagai bagian dari pernyataan `while`.
    - Pada loop `for`, kondisi `sum < 10000` ditulis sebagai bagian kedua dari pernyataan `for`.
- **Inkrementasi (Iteration Expression)**:
    - Pada loop `while`, inkrementasi `i++` dilakukan di dalam loop body.
    - Pada loop `for`, inkrementasi `i++` dilakukan di bagian ketiga dari pernyataan `for`.
### Loop `for` yang dihasilkan:
Loop `for` yang dihasilkan memiliki fungsi yang sama dengan loop `while` asli. Loop ini akan berjalan selama `sum` kurang dari 10.000, menambahkan nilai `i` ke `sum` dan menginkrement `i` pada setiap iterasi.

5. After the continue statement is executed in the following loop, which statement is executed? Show the output.
![Pasted image 20240702150708.png](/img/user/Pasted%20image%2020240702150708.png)
Setelah pernyataan `continue` dieksekusi dalam loop berikut, pernyataan berikutnya yang dieksekusi adalah increment pada loop terdalam (yaitu `j++`). Ini karena `continue` menyebabkan loop saat ini melewati sisa dari iterasi saat ini dan melanjutkan dengan iterasi berikutnya dari loop tersebut.
Berikut adalah kode yang diberikan:
```java
for (int i = 1; i < 4; i++) {
    for (int j = 1; j < 4; j++) {
        if (i * j > 2) {
            continue;
        }
        System.out.println(i * j);
    }
    System.out.println(i);
}
```
- **Iterasi Pertama (i = 1):**
    - `j = 1`: `i * j = 1`, cetak `1`
    - `j = 2`: `i * j = 2`, cetak `2`
    - `j = 3`: `i * j = 3`, `continue`, tidak ada pencetakan
    - Cetak `i` (1)
- **Iterasi Kedua (i = 2):**
    - `j = 1`: `i * j = 2`, cetak `2`
    - `j = 2`: `i * j = 4`, `continue`, tidak ada pencetakan
    - `j = 3`: `i * j = 6`, `continue`, tidak ada pencetakan
    - Cetak `i` (2)
- **Iterasi Ketiga (i = 3):**
    - `j = 1`: `i * j = 3`, `continue`, tidak ada pencetakan
    - `j = 2`: `i * j = 6`, `continue`, tidak ada pencetakan
    - `j = 3`: `i * j = 9`, `continue`, tidak ada pencetakan
    - Cetak `i` (3)
 **Output yang dihasilkan:**
```java
1
2
1
2
3
```
**Penjelasan Output:**
- Pada iterasi pertama (`i = 1`), `1` dan `2` dicetak dari loop dalam sebelum `i * j > 2` menjadi benar dan `continue` dieksekusi. Kemudian `1` dicetak dari loop luar.
- Pada iterasi kedua (`i = 2`), hanya `2` dicetak dari loop dalam sebelum `i * j > 2` menjadi benar. Kemudian `2` dicetak dari loop luar.
- Pada iterasi ketiga (`i = 3`), tidak ada yang dicetak dari loop dalam karena `i * j > 2` selalu benar. Kemudian `3` dicetak dari loop luar.

6. Create a program to do the average of multiple inputted numbers. Examples program given below!
![Pasted image 20240702150649.png](/img/user/Pasted%20image%2020240702150649.png)
```java
import java.util.Scanner;
public class AverageCalculator {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Meminta jumlah angka yang akan dimasukkan
        System.out.print("How many numbers will be input: ");
        int count = scanner.nextInt();

        int[] numbers = new int[count];
        int total = 0;

        // Meminta input angka dan menghitung total
        for (int i = 0; i < count; i++) {
            System.out.print("Number " + (i + 1) + ": ");
            numbers[i] = scanner.nextInt();
            total += numbers[i];
        }

        // Menghitung rata-rata
        double average = (double) total / count;

        // Menampilkan hasil
        System.out.println("Total: " + total);
        System.out.println("Average: " + average);
    }
}
```
- **Inisialisasi Scanner**:
    - `Scanner scanner = new Scanner(System.in);` digunakan untuk menerima input dari pengguna.
- **Meminta Jumlah Angka yang Akan Dimasukkan**:
    - `System.out.print("How many numbers will be input: ");` menampilkan pesan untuk meminta pengguna memasukkan jumlah angka.
    - `int count = scanner.nextInt();` menyimpan jumlah angka yang akan dimasukkan ke dalam variabel `count`.
- **Inisialisasi Array dan Variabel Total**:
    - `int[] numbers = new int[count];` membuat array untuk menyimpan angka-angka yang dimasukkan oleh pengguna.
    - `int total = 0;` menginisialisasi variabel `total` untuk menyimpan jumlah total dari angka-angka yang dimasukkan.
- **Loop untuk Meminta Input Angka dan Menghitung Total**:
    - `for (int i = 0; i < count; i++) { ... }` loop ini berjalan sebanyak `count` kali untuk menerima input angka dari pengguna.
    - `System.out.print("Number " + (i + 1) + ": ");` menampilkan pesan untuk meminta pengguna memasukkan angka ke-`i+1`.
    - `numbers[i] = scanner.nextInt();` menyimpan angka yang dimasukkan ke dalam array `numbers`.
    - `total += numbers[i];` menambahkan angka yang dimasukkan ke dalam variabel `total`.
- **Menghitung Rata-rata**:
    - `double average = (double) total / count;` menghitung rata-rata dengan membagi `total` dengan `count`.
- **Menampilkan Hasil**:
    - `System.out.println("Total: " + total);` menampilkan total dari angka-angka yang dimasukkan.
    - `System.out.println("Average: " + average);` menampilkan rata-rata dari angka-angka yang dimasukkan.
Dengan program ini, Anda dapat memasukkan beberapa angka, menghitung total dan rata-rata dari angka-angka tersebut, serta menampilkan hasilnya di konsol.
---
#9_Jump_Operation_and_Exception_Handling
1. Create a program to do the authentication access using break keyword
![Pasted image 20240702150010.png](/img/user/Pasted%20image%2020240702150010.png)
```java
import java.util.Scanner;

public class Authentication {

    public static void main(String[] args) {
        String[][] users = {
            {"budi", "hello123"},
            {"william", "helloworld"}
        };

        Scanner scanner = new Scanner(System.in);

        while (true) {
            System.out.print("Username: ");
            String username = scanner.nextLine();
            boolean userFound = false;

            for (String[] user : users) {
                if (user[0].equals(username)) {
                    userFound = true;
                    for (int attempts = 0; attempts < 3; attempts++) {
                        System.out.print("Pass: ");
                        String password = scanner.nextLine();
                        if (user[1].equals(password)) {
                            System.out.println("Access is granted");
                            break;
                        } else {
                            System.out.println("Password is wrong!");
                        }
                    }
                    break;
                }
            }

            if (!userFound) {
                System.out.println("Username is not found!");
            }

            System.out.print("Do you want to try again? (yes/no): ");
            String retry = scanner.nextLine();
            if (!retry.equalsIgnoreCase("yes")) {
                break;
            }
        }
    }
}
```
- **Data Pengguna**:
    - Data pengguna disimpan dalam array 2 dimensi `users` dengan format `{"username", "password"}`.
- **Scanner**:
    - Digunakan untuk menerima input dari pengguna.
- **Loop Utama**:
    - `while (true)` digunakan untuk mengulangi proses autentikasi hingga pengguna memutuskan untuk berhenti.
- **Pengecekan Username**:
    - Loop `for (String[] user : users)` digunakan untuk memeriksa apakah username yang dimasukkan ada dalam data pengguna.
    - Jika username ditemukan, `userFound` diset ke `true` dan masuk ke loop untuk memeriksa password.
- **Pengecekan Password**:
    - Loop `for (int attempts = 0; attempts < 3; attempts++)` digunakan untuk memberikan maksimal 3 kali percobaan memasukkan password yang benar.
    - Jika password benar, menampilkan pesan "Access is granted" dan menggunakan `break` untuk keluar dari loop password.
    - Jika password salah, menampilkan pesan "Password is wrong!".
- **Pengguna Tidak Ditemukan**:
    - Jika `userFound` tetap `false` setelah pengecekan semua username, menampilkan pesan "Username is not found!".
- **Retry**:
    - Setelah satu sesi autentikasi (baik berhasil atau gagal), pengguna ditanya apakah ingin mencoba lagi. Jika pengguna menjawab "no", loop utama dihentikan dengan `break`.
Dengan program ini, proses autentikasi menggunakan username dan password dapat dilakukan, memberikan maksimal 3 kali percobaan untuk memasukkan password yang benar sebelum meminta username kembali, dan memungkinkan pengguna untuk mencoba lagi atau berhenti setelah setiap sesi autentikasi.
---
#10_Static_and_Dynamic_Array 
1. Create a program that allows to receive multiples entry data, shows the data from the list, and delete from the list as following
![Pasted image 20240702145508.png](/img/user/Pasted%20image%2020240702145508.png)
```java
import java.util.ArrayList;
import java.util.Scanner;

public class DataManager {

    static class Data {
        String name;
        String pass;
        String phone;

        Data(String name, String pass, String phone) {
            this.name = name;
            this.pass = pass;
            this.phone = phone;
        }
    }

    private static final ArrayList<Data> dataList = new ArrayList<>();
    private static final Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) {
        while (true) {
            System.out.println("1. Input Data");
            System.out.println("2. Show Data");
            System.out.println("3. Delete Data");
            System.out.println("4. Exit");
            System.out.print("Your choice: ");
            int choice = scanner.nextInt();
            scanner.nextLine();  // Consume newline

            switch (choice) {
                case 1:
                    inputData();
                    break;
                case 2:
                    showData();
                    break;
                case 3:
                    deleteData();
                    break;
                case 4:
                    System.exit(0);
                default:
                    System.out.println("Invalid choice. Please try again.");
            }
        }
    }

    private static void inputData() {
        System.out.print("Name: ");
        String name = scanner.nextLine();
        System.out.print("Pass: ");
        String pass = scanner.nextLine();
        System.out.print("Phone: ");
        String phone = scanner.nextLine();
        dataList.add(new Data(name, pass, phone));
        System.out.println("New data is added");
    }

    private static void showData() {
        if (dataList.isEmpty()) {
            System.out.println("|No data exists!|");
        } else {
            System.out.println("|No| Name   | Pass   | Phone        |");
            System.out.println("|---------------------------------|");
            for (int i = 0; i < dataList.size(); i++) {
                Data data = dataList.get(i);
                System.out.printf("|%d | %-7s| %-7s| %-12s|\n", i + 1, data.name, data.pass, data.phone);
            }
        }
    }

    private static void deleteData() {
        if (dataList.isEmpty()) {
            System.out.println("|No data exists!|");
            return;
        }
        showData();
        System.out.print("Input data number to be deleted: ");
        int index = scanner.nextInt();
        scanner.nextLine();  // Consume newline
        if (index < 1 || index > dataList.size()) {
            System.out.println("Invalid data number.");
        } else {
            dataList.remove(index - 1);
            System.out.println("Data is removed");
        }
    }
}
```
- **Kelas `Data`**:
    - Kelas ini digunakan untuk menyimpan data setiap entri (name, pass, phone).
- **Metode `main`**:
    - Menyediakan menu utama yang memungkinkan pengguna memilih untuk menambahkan data, menampilkan data, menghapus data, atau keluar dari program.
- **Metode `inputData`**:
    - Meminta pengguna untuk memasukkan nama, kata sandi, dan nomor telepon, lalu menambahkan data tersebut ke `dataList`.
- **Metode `showData`**:
    - Menampilkan daftar data yang ada dalam format tabel. Jika tidak ada data, akan menampilkan pesan "No data exists!".
- **Metode `deleteData`**:
    - Menampilkan data yang ada dan meminta pengguna untuk memasukkan nomor data yang ingin dihapus. Menghapus data berdasarkan nomor yang dimasukkan pengguna.
Dengan program ini, Anda dapat memasukkan beberapa entri data, menampilkan data yang ada, dan menghapus data dari daftar sesuai dengan pilihan pengguna.
---
#11_Methods
1. What are the **benefits** of using a method? ***keuntungan menggunakan***
	- **Kode yang Dapat Digunakan Kembali (Reusability)**: Metode memungkinkan Anda untuk menggunakan kembali kode, mengurangi redundansi dan meningkatkan pemeliharaan.
	- **Modularitas**: Metode membantu memecah masalah kompleks menjadi tugas-tugas yang lebih kecil dan dapat dikelola.
	- **Abstraksi**: Metode menyediakan cara untuk mengabstraksi detail implementasi dan fokus pada tujuan metode tersebut.
	- **Keterbacaan dan Pemeliharaan**: Metode membuat kode lebih mudah dibaca dan dipelihara dengan mengorganisir fungsionalitas ke dalam unit-unit yang berbeda.
	- **Kemudahan Pengujian**: Metode yang lebih kecil dan terisolasi lebih mudah untuk diuji dan dibetulkan.
How do you **define a method?** ***Mendefinisikan***
```java
public int tambah(int a, int b) {
    return a + b;
}
```
 Dalam contoh ini:
	- `public` adalah modifier akses.
	- `int` adalah tipe pengembalian.
	- `tambah` adalah nama metode.
	- `(int a, int b)` adalah parameter.
How do you **invoke a method? ***Memanggil***
	Ini memanggil metode `tambah` dengan argumen `5` dan `3`.
```java
int hasil = tambah(5, 3);
```

2. What would be wrong with not writing a **return statement in a value-returning method**?  **Pernyataan Return dalam Metode yang Mengembalikan Nilai**
    Jika metode yang mengembalikan nilai tidak memiliki pernyataan return, itu akan menyebabkan kesalahan pada waktu kompilasi karena metode tersebut harus mengembalikan nilai dari tipe yang ditentukan. Contohnya:
```java
public int tambah(int a, int b) {
    // Tidak ada pernyataan return akan menyebabkan kesalahan kompilasi
}
```
Can you have a **return statement in a void method?** ***Pernyataan Return dalam Metode Void***
```java
public void cetakPesan(String pesan) {
    if (pesan == null) {
        return; // Keluar lebih awal jika pesan null
    }
    System.out.println(pesan);
}
```
Does the **return statement in void method** cause **syntax errors**? 
    Pernyataan return dalam metode void **tidak menyebabkan kesalahan sintaks selama tidak digunakan untuk mengembalikan nilai.**

3. Define the terms parameters, argument, and method signature
    - **Parameter**: Variabel yang didefinisikan dalam tanda tangan metode(**method signature**) yang menerima nilai yang dilewatkan ke metode saat dipanggil. Misalnya, `int a` dan `int b` dalam `public int tambah(int a, int b)`.
	- **Argumen (Arguments)**: Nilai aktual yang dilewatkan ke metode saat dipanggil. Misalnya, `5` dan `3` dalam `tambah(5, 3)`.
	- **Tanda Tangan Metode (Method Signature)**: Kombinasi dari nama metode(**method name**) dan daftar parameter(**parameter list**). Ini mengidentifikasi metode secara unik. Misalnya, tanda tangan metode(**method signature**) dari `public int tambah(int a, int b)` adalah `tambah(int, int)`.

4. Identify and correct the errors in the following program:
```java
public class Test {
    public static void method1(int n, int m) {
        n += m;
        method2(n);  // Mengganti argument 3.4 dengan n
    }

    public static int method2(int n) {
        if (n > 0) return 1;
        else if (n == 0) return 0;
        else if (n < 0) return -1;
        // Perlu menambahkan return default agar tidak terjadi error kompilasi
        return 0;
    }
}
```
- **Tipe Data Parameter Kedua dalam `method1`**:
    - Pada kode awal, parameter kedua `m` tidak memiliki tipe data. Telah ditambahkan tipe data `int` untuk parameter `m`.
- **Pemanggilan `method2` dalam `method1`**:
    - Pada kode awal, `method2` dipanggil dengan argumen `3.4` yang merupakan `double`, sementara `method2` mengharapkan argumen bertipe `int`. Telah diubah menjadi `method2(n)`.
- **Return Default dalam `method2`**:
    - Pada kode awal, `method2` sudah mencakup semua kemungkinan kasus, namun menambahkan return default `return 0;` di akhir metode adalah praktik yang baik untuk memastikan semua jalur mengembalikan nilai.

5. What is wrong in the following program?
```java
public class Test {
    public static void method(int x) {
        // Implementasi method1
    }

    public static int method(int y) {
        return y;
    }
}
```
Namun, terdapat masalah pada kode ini yaitu terdapat dua metode dengan nama yang sama tetapi dengan tipe parameter yang berbeda. Meskipun ini diperbolehkan dalam Java (overloading), untuk kejelasan saya akan memberikan nama yang berbeda untuk kedua metode tersebut:
```java
public class Test {
    public static void method1(int x) {
        // Implementasi method1
    }

    public static int method2(int y) {
        return y;
    }
}
```
- **Metode `method1`**:
    - Ini adalah metode `void` yang menerima satu parameter `int x`. Isi dari metode ini belum diimplementasikan.
- **Metode `method2`**:
    - Ini adalah metode yang mengembalikan nilai `int` dan menerima satu parameter `int y`. Metode ini hanya mengembalikan nilai dari parameter `y`.
Dengan memberikan nama yang berbeda (`method1` dan `method2`), kita menghindari potensi kebingungan dan memastikan bahwa metode tersebut jelas berbeda dalam hal penggunaannya.

6. Identify and correct the errors in the following program:
```java
public class Test {
    public static void main(String[] args) {
        nPrintln("Welcome to Java!", 5);
    }

    public static void nPrintln(String message, int n) {
        //int n = 1; ini salah
        for (int i = 0; i < n; i++) {
            System.out.println(message);
        }
    }
}
```
- **Metode `main`**:
    - Metode ini adalah titik masuk utama untuk program Java. Metode ini memanggil metode `nPrintln` dengan pesan "Welcome to Java!" dan jumlah pengulangan 5.
- **Metode `nPrintln`**:
    - Metode ini menerima dua parameter: `String message` dan `int n`.
    - Pengulangan menggunakan loop `for` dari 0 hingga `n`, mencetak pesan `message` sebanyak `n` kali.
**Perbaikan yang dilakukan:**
- Menghapus deklarasi `int n = 1;` dalam metode `nPrintln`, karena tidak diperlukan dan menyebabkan konflik dengan parameter `int n` yang diterima oleh metode tersebut.
- Mengubah loop `for` untuk menggunakan parameter `n` yang diterima oleh metode `nPrintln` untuk menentukan jumlah pengulangan.
Dengan perbaikan ini, program akan mencetak pesan **"Welcome to Java!" sebanyak 5 kali.**

7. Create a program that allows to receive multiple entries from user to count the total of summation, multiplication, and average using methods for each functionality built.
![Pasted image 20240702145030.png](/img/user/Pasted%20image%2020240702145030.png)
```java
import java.util.Scanner;

public class Calculator {

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        System.out.print("How many numbers will be input: ");
        int count = scanner.nextInt();

        double[] numbers = new double[count];
        for (int i = 0; i < count; i++) {
            System.out.print("Number " + (i + 1) + ": ");
            numbers[i] = scanner.nextDouble();
        }

        double totalSum = calculateSum(numbers);
        double totalProduct = calculateProduct(numbers);
        double average = calculateAverage(numbers);

        System.out.println("Total Summation: " + totalSum);
        System.out.println("Total Multiplication: " + totalProduct);
        System.out.println("Total Avg: " + average);
    }

    public static double calculateSum(double[] numbers) {
        double sum = 0;
        for (double num : numbers) {
            sum += num;
        }
        return sum;
    }

    public static double calculateProduct(double[] numbers) {
        double product = 1;
        for (double num : numbers) {
            product *= num;
        }
        return product;
    }

    public static double calculateAverage(double[] numbers) {
        double sum = calculateSum(numbers);
        return sum / numbers.length;
    }
}
```
- **Metode `main`**:
    - Menggunakan `Scanner` untuk menerima input dari pengguna.
    - Meminta pengguna untuk menentukan berapa banyak angka yang akan dimasukkan.
    - Mengumpulkan angka-angka tersebut dalam array `numbers`.
    - Memanggil metode `calculateSum`, `calculateProduct`, dan `calculateAverage` untuk menghitung total penjumlahan, perkalian, dan rata-rata.
    - Mencetak hasil perhitungan ke layar.
- **Metode `calculateSum`**:
    - Menerima array `double` sebagai parameter dan mengembalikan total penjumlahan angka-angka dalam array tersebut.
- **Metode `calculateProduct`**:
    - Menerima array `double` sebagai parameter dan mengembalikan total perkalian angka-angka dalam array tersebut.
- **Metode `calculateAverage`**:
    - Menggunakan metode `calculateSum` untuk menghitung total penjumlahan dan kemudian membagi hasilnya dengan jumlah elemen dalam array untuk mendapatkan rata-rata.
Dengan program ini, Anda dapat menghitung total penjumlahan, perkalian, dan rata-rata dari sejumlah angka yang dimasukkan oleh pengguna.
---
#12_Sorting
•Create a program that allows to input user authentication details, 
	show the inputted data, 
	sorting name data by ascending.
![Pasted image 20240702134900.png](/img/user/Pasted%20image%2020240702134900.png)

```java
package com.mycompany.usermanagementsystem;

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.Scanner;

class User {
    private String name;
    private String password;
    private String phone;

    public User(String name, String password, String phone) {
        this.name = name;
        this.password = password;
        this.phone = phone;
    }

    public String getName() {
        return name;
    }

    public String getPassword() {
        return password;
    }

    public String getPhone() {
        return phone;
    }

    @Override
    public String toString() {
        return String.format("%-15s %-15s %-15s", name, password, phone);
    }
}

public class UserManagementSystem {
    private ArrayList<User> users;
    private Scanner scanner;

    public UserManagementSystem() {
        users = new ArrayList<>();
        scanner = new Scanner(System.in);
    }

    public void addUser() {
        System.out.print("Enter Name: ");
        String name = scanner.nextLine();
        System.out.print("Enter Password: ");
        String password = scanner.nextLine();
        System.out.print("Enter Phone: ");
        String phone = scanner.nextLine();
        users.add(new User(name, password, phone));
        System.out.println("New data is added");
    }

    public void showUsers() {
        if (users.isEmpty()) {
            System.out.println("No data available.");
        } else {
            System.out.println("===========================================");
            System.out.println(String.format("%-15s %-15s %-15s", "Name", "Password", "Phone"));
            System.out.println("===========================================");
            for (int i = 0; i < users.size(); i++) {
                System.out.println((i + 1) + " | " + users.get(i).toString());
            }
            System.out.println("===========================================");
        }
    }

    public void deleteUser() {
        if (users.isEmpty()) {
            System.out.println("No data available.");
            return;
        }
        showUsers();
        System.out.print("Input data number to be deleted: ");
        int index = Integer.parseInt(scanner.nextLine()) - 1;
        if (index >= 0 && index < users.size()) {
            users.remove(index);
            System.out.println("Data is removed");
        } else {
            System.out.println("Invalid data number.");
        }
    }

    public void sortUsersByName() {
        Collections.sort(users, Comparator.comparing(User::getName));
        System.out.println("Data sorted by name.");
    }

    public void menu() {
        while (true) {
            System.out.println("\n1. Input Data");
            System.out.println("2. Show Data");
            System.out.println("3. Delete Data");
            System.out.println("4. Sorting Data");
            System.out.println("5. Exit");
            System.out.print("Your choice: ");
            int choice = Integer.parseInt(scanner.nextLine());

            switch (choice) {
                case 1:
                    addUser();
                    break;
                case 2:
                    showUsers();
                    break;
                case 3:
                    deleteUser();
                    break;
                case 4:
                    sortUsersByName();
                    break;
                case 5:
                    System.out.println("Exiting program.");
                    return;
                default:
                    System.out.println("Invalid choice, please try again.");
            }
        }
    }

    public static void main(String[] args) {
        UserManagementSystem ums = new UserManagementSystem();
        ums.menu();
    }
}
```
---
#13_Introduction_to_OOP_Concept
•In this assignment, you are require to make a program to handle Student Management System.
•Implement a class of Student (OOP) to complete this assignment
•It has 4 menus:
	**–Add Student**  
	  In this menu, the user will be asked to input 10 digits of NIM, name and phone number
	**–Delete Student** 
	  User need to input NIM that existed in the data in order to delete
	**–View Student**  
	  This menu will only show list of student names.
	**–Exit**  
	  Program end
![Pasted image 20240702135359.png](/img/user/Pasted%20image%2020240702135359.png)
```java
package com.mycompany.studentmanagementsystem;

import java.util.ArrayList;
import java.util.Scanner;

class Student {
    private String nim;
    private String name;
    private String phone;

    public Student(String nim, String name, String phone) {
        this.nim = nim;
        this.name = name;
        this.phone = phone;
    }

    public String getNim() {
        return nim;
    }

    public String getName() {
        return name;
    }

    public String getPhone() {
        return phone;
    }
}

class StudentManagementSystem {
    private ArrayList<Student> students;
    private Scanner scanner;

    public StudentManagementSystem() {
        students = new ArrayList<>();
        scanner = new Scanner(System.in);
    }

    public void addStudent() {
        System.out.print("Enter NIM (10 digits): ");
        String nim = scanner.nextLine();
        if (nim.length() != 10) {
            System.out.println("NIM must be 10 digits long.");
            return;
        }
        System.out.print("Enter Name: ");
        String name = scanner.nextLine();
        System.out.print("Enter Phone: ");
        String phone = scanner.nextLine();
        students.add(new Student(nim, name, phone));
        System.out.println("Student " + name + " added successfully.");
    }

    public void deleteStudent() {
        System.out.print("Enter NIM to delete: ");
        String nim = scanner.nextLine();
        for (Student student : students) {
            if (student.getNim().equals(nim)) {
                students.remove(student);
                System.out.println("Student " + student.getName() + " deleted successfully.");
                return;
            }
        }
        System.out.println("Student with given NIM not found.");
    }

    public void viewStudents() {
        if (students.isEmpty()) {
            System.out.println("No students available.");
        } else {
            for (Student student : students) {
                System.out.println("Name: " + student.getName());
            }
        }
    }

    public void menu() {
        while (true) {
            System.out.println("\nStudent Management System");
            System.out.println("1. Add Student");
            System.out.println("2. Delete Student");
            System.out.println("3. View Students");
            System.out.println("4. Exit");
            System.out.print("Enter your choice: ");
            int choice = Integer.parseInt(scanner.nextLine());

            switch (choice) {
                case 1:
                    addStudent();
                    break;
                case 2:
                    deleteStudent();
                    break;
                case 3:
                    viewStudents();
                    break;
                case 4:
                    System.out.println("Exiting program.");
                    return;
                default:
                    System.out.println("Invalid choice, please try again.");
            }
        }
    }

    public static void main(String[] args) {
        StudentManagementSystem sms = new StudentManagementSystem();
        sms.menu();
    }
}
```
---
