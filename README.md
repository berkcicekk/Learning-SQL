## Veritabanı nedir?

Veritabanı, kolayca erişilebilecek, geri alınabilecek, yönetilebilecek ve güncellenebilecek şekilde depolanan ilgili bilgilerin sistematik veya organize bir koleksiyonudur

## Veritabanı tablosu nedir?

Veritabanı tablosu, verilerin düzenli bir şekilde saklandığı, satır ve sütunlardan oluşan bir yapıdır. Her bir tablo, belirli bir konu veya veri türüyle ilgili bilgileri içerir. Örneğin, bir müşteri veritabanında müşteri adı, adresi, telefon numarası gibi bilgilerin bulunduğu bir tablo olabilir. Veritabanı tabloları, verilerin daha düzenli ve erişilebilir bir şekilde saklanmasını sağlar ve veri işleme işlemlerinin daha kolay yapılmasına olanak tanır.

![Untitled](https://github.com/berkcicekk/Learning-SQL/assets/90208101/d6651aaf-f4c7-4069-b6de-a5cf842c9299)

## Database relationship nedir?**

verileri almak için birleştirme ifadeleri kullanılarak oluşturulan tablolar arasındaki ilişkilerdir. Tablo yapılarını iyileştirmeye ve gereksiz verileri azaltmaya yardımcı olur.

**1. One-to-One:**

Bire bir ilişki, her tablonun diğer tabloda yalnızca bir eşleşen satıra sahip olabileceği iki tablo arasındaki ilişkidir.

![Untitled 1](https://github.com/berkcicekk/Learning-SQL/assets/90208101/a06f156d-f53a-4903-99eb-ab7172f300ac)
Örnek olarak yukarıdaki ekran görüntüsünü kullanırsak, iş gerekçesi, her çalışanın ödeme ayrıntılarının, çalışanın iletişim bilgilerine göre ayrı bir tabloda saklanması gerektiğidir. Böyle bir durumda, Ücret tablosunda, Çalışanlar tablosundaki belirli bir çalışanla eşleşen yalnızca bir satır olabilir. 

**2. One-to-Many:**

tablolardan birinde birden çok eşleşen satıra izin vermesi dışında bire bir ilişkiye benzer.
![Untitled 3](https://github.com/berkcicekk/Learning-SQL/assets/90208101/47c2ef65-6ce2-4922-b656-98a090d61186)

Yukarıdaki örnekte, her yazarın birçok kitabı olabilir ancak her kitabın yalnızca bir yazarı olabilir. Bu nedenle Books tablosunun aynı AuthorId değerine sahip birden çok satır içermesine izin verilir. Bir yazar beş kitap yayınlamışsa, Yazarlar'da o yazar için bir satır ve Kitaplar'da her biri o yazarın AuthorId'sine sahip beş satır olacaktır.

**3. Many-to-Many:**

ilişkinin her bir tarafı birden çok satır içerebilir.
![Untitled 3](https://github.com/berkcicekk/Learning-SQL/assets/90208101/95a6dc38-0935-45d8-8db6-0714728442b2)
Bu örnekte, her kitabın birden çok yazarı olabilir. Bu nedenle, hem AuthorId'i hem de BookId'yi saklayan bir arama tablosu ("bağlantı tablosu" olarak da bilinir) oluşturdum. Bu iki sütun, tablonun birincil anahtarı olacak şekilde yapılandırılabilir (bu durumda bunlar "bileşik birincil anahtar" veya yalnızca "bileşik anahtar" olur) veya birincil anahtar olarak ayrı bir sütun oluşturabilirsiniz. Bu durumda Kitaplar tablosunda AuthorId bulunmadığına dikkat edin. Aynı BookId için birçok AuthorId'e sahip olabilmemiz için bu sütun AuthorBooks tablosuna taşındı.


![Untitled 4](https://github.com/berkcicekk/Learning-SQL/assets/90208101/7ee77fea-44cb-440b-99a2-74c642cf2901)

# SQL

SQL'in açılımı "Structured Query Language" yani "Yapılandırılmış Sorgu Dili"dir. SQL, veritabanlarına erişmek, veri eklemek, değiştirmek, sorgulamak ve silmek için kullanılan bir programlama dilidir. Veritabanı yönetim sistemlerinin (DBMS) bir parçası olarak, verilerin etkili bir şekilde saklanması, yönetilmesi ve sorgulanmasına yardımcı olur.
![Untitled 5](https://github.com/berkcicekk/Learning-SQL/assets/90208101/78ada4ae-4378-4419-8ced-485815cf345d)


### SQL Ne Yapabilir?

- *SQL bir veritabanına karşı sorgular yürütebilir*
- *SQL bir veritabanından veri alabilir*
- *SQL bir veritabanına kayıt ekleyebilir*
- *SQL bir veritabanındaki kayıtları güncelleyebilir*
- *SQL bir veritabanından kayıtları silebilir*
- *SQL yeni veritabanları oluşturabilir*
- *SQL bir veritabanında yeni tablolar oluşturabilir,*
- *SQL veritabanında saklı yordamlar oluşturabilir*
- *SQL bir veritabanında görünümler oluşturabilir*
- *SQL tablolar, prosedürler ve görünümler üzerinde izinler ayarlayabilir*

<aside>
💡 SQL bir ANSI/ISO standardı olmasına rağmen, SQL dilinin farklı versiyonları vardır.

</aside>

<aside>
🚨 RMDBS, Relational Database Management System'in kısaltmasıdır. ***İlişkisel veritabanı*** yönetim sistemi anlamına gelir. İlişkisel veritabanları, verileri tablolar halinde depolayan veritabanlarıdır. Her tablo, bir veya daha fazla sütun ve satırdan oluşur. Sütunlar, tablodaki verileri temsil eden sütunlardır. Satırlar, tablodaki verileri içeren satırlardır.

</aside>

<aside>
🚨

1. **Döküman Tabanlı Veritabanlar (Document Store Databases):** Bu tür veritabanları, JSON veya BSON gibi döküman formatlarıyla verileri saklar. Her döküman, kendi alanları ve değerleriyle birlikte veriyi içerir. **Örneğin, MongoDB bu tür bir döküman tabanlı veritabanıdır.**
2. **Anahtar-Değer Tabanlı Veritabanlar (Key-Value Store Databases):** Bu tür veritabanları, bir anahtar (key) ile bir değeri (value) ilişkilendirir. Anahtarlar benzersizdir ve belirli bir anahtara sahip bir değeri hızlıca almanızı sağlar. Örneğin, Redis ve Amazon DynamoDB anahtar-değer tabanlı veritabanlarına örnektir.
3. **Sütun Tabanlı Veritabanlar (Column Store Databases):** Sütun tabanlı veritabanları, veriyi sütunlara göre gruplandırır. Bu yaklaşım, büyük veri analizi ve sorgulama işlemlerini optimize etmeye yardımcı olabilir. HBase ve Apache Cassandra sütun tabanlı veritabanlarına örnektir.
4. **Graf Tabanlı Veritabanlar (Graph Databases):** Graf tabanlı veritabanları, düğümler (nodes) ve kenarlar (edges) arasındaki ilişkileri depolar. Bu tür veritabanları, karmaşık ilişkisel verileri ve ağları modellemek ve sorgulamak için kullanılır. Neo4j bir graf tabanlı veritabanıdır.
</aside>

Veritabanı yönetim sistemi ve kullanım amaçları şunlardır:

1. PostgreSQL: Açık kaynaklı bir ilişkisel veritabanı yönetim sistemi olan PostgreSQL, güçlü ve geniş özellik setine sahiptir. İleri düzey veri türleri, uzantı desteği ve karmaşık sorgular için tercih edilir. Özellikle büyük ölçekli, karmaşık ve çok kullanıcılı uygulamalar için idealdir.
2. Microsoft SQL Server: Microsoft SQL Server, Microsoft tarafından geliştirilen bir ilişkisel veritabanı yönetim sistemidir. Windows tabanlı uygulamalar için tercih edilir ve büyük ölçekli işletmelerde sıkça kullanılır.
3. Oracle Database: Oracle Database, Oracle Corporation tarafından geliştirilen bir ilişkisel veritabanı yönetim sistemidir. Güçlü performans ve yüksek güvenilirlik sunar. Özellikle büyük işletmeler ve kritik uygulamalar için tercih edilir.
4. SQLite: SQLite, hafif ve taşınabilir bir veritabanı yönetim sistemidir. Tek kullanıcılı uygulamalar, gömülü sistemler ve basit veri depolama gereksinimleri için uygundur.
5. MongoDB: MongoDB, NoSQL tabanlı bir veritabanı yönetim sistemi olarak bilinir. Yüksek hacimli ve hızlı büyüyen veri için ölçeklenebilir ve esnek bir seçenektir. JSON benzeri belgeleri saklama yeteneğine sahiptir ve özellikle büyük veri uygulamalarında kullanılır.

### Data Manipülasyon Komutları

`SELECT :` Kayıt Cekme !

`UPDATE :` Kaydın alanını güncelleme 

`DELETE :` Tablodan kayıt silme 

`INSERT :` Yeni Kayıt 

`TRUNCATE :` TAblonun içini bosalt

`CREATE :` Nesne Olustururu 

`ALTER :` Nesne ozelligi değistirir

`DROP :` Veritabanıı nesnesi siler

---

**Data Manipülasyon:**
Data Manipülasyon, genel olarak verilerin işlenmesi, dönüştürülmesi, düzenlenmesi veya analiz edilmesi sürecini ifade eder. Veriler, birçok farklı kaynaktan (dosyalar, sensörler, web servisleri, kullanıcı girişleri vb.) toplanır ve bu verilerin anlamlı hale getirilmesi veya istenilen bir sonuca ulaşmak için işlenmesi gerekir. Data Manipülasyon, verilerin temizlenmesi, dönüştürülmesi, birleştirilmesi, filtrelenmesi ve hesaplamaların yapılması gibi adımları içerebilir. Veriler, çeşitli veri analiz ve işleme araçları veya programlama dilleri kullanılarak manipüle edilebilir.

> Örneğin, bir şirketin satış verileri üzerinde data manipülasyon yapmak için, farklı satış verilerini birleştirmek, boş veya hatalı verileri temizlemek, belirli bir zaman aralığındaki satışları filtrelemek veya toplam satış tutarını hesaplamak gibi işlemler gerçekleştirilebilir.
> 

**Veritabanı Manipülasyonu:**
Veritabanı Manipülasyonu ise, veritabanında bulunan verilerin değiştirilmesi veya yönetilmesi sürecini ifade eder. Veritabanı, verilerin düzenli ve yapılandırılmış bir şekilde saklandığı bir depolama sistemidir. Veritabanı Manipülasyonu, veritabanında yer alan verilerin eklenmesi, güncellenmesi, silinmesi veya sorgulanması gibi işlemleri içerir. Bu işlemler, veritabanı sorgu dilleri (SQL gibi) veya veritabanı yönetim sistemleri (MySQL, PostgreSQL, SQL Server, Oracle vb.) kullanılarak gerçekleştirilir.

> Örneğin, bir müşteri veritabanında bir yeni müşterinin eklendiği, mevcut müşteri bilgilerinin güncellendiği veya belirli bir müşteri grubunu sorgulamak için veritabanı manipülasyonu kullanılabilir.
> 

---

### **The SQL SELECT Statement**

```sql
SELECT * FROM Customers;
```

> *SQL anahtar sözcükleri büyük/küçük harfe duyarlı DEĞİLDİR: select, SELECT ile aynıdır.*
> 

SELECT - bir veritabanından veri çeker
UPDATE - bir veritabanındaki verileri günceller
DELETE - veritabanındaki verileri siler
INSERT INTO - bir veritabanına yeni veri ekler
CREATE DATABASE - yeni bir veritabanı oluşturur
ALTER DATABASE - bir veritabanını değiştirir
CREATE TABLE - yeni bir tablo oluşturur
ALTER TABLE - bir tabloyu değiştirir
DROP TABLE - bir tabloyu siler
CREATE INDEX - bir dizin oluşturur (arama anahtarı)
DROP INDEX - bir dizini siler

### 1. **SQL SELECT Statement**

 `SELECT` ifadesi, bir veritabanından veri seçmek için kullanılır. Döndürülen veriler, sonuç kümesi adı verilen bir sonuç tablosunda saklanır.

```sql
SELECT column1, column2, ...
FROM table_name;
WHERE <ŞARTLAR>
```

sütun1, sütun2, ... veri seçmek istediğiniz tablonun alan adlarıdır. Tabloda bulunan tüm alanları seçmek istiyorsanız,

```sql
SELECT * FROM *table_name*;
```

Aşağıdaki SQL deyimi, "Müşteriler" tablosundan "MüşteriAdı" ve "Şehir" sütunlarını seçer:

```sql
SELECT CustomerName, City FROM Customers;
```

### 2.**The SQL INSERT INTO Statement**

 INSERT INTO ifadesi, bir tabloya yeni kayıtlar eklemek için kullanılır.

```sql
INSERT INTI TABLOADI  (KOLON1,KOLON2,...)
VALUES (DEĞER1,DEĞER2,DEĞER3,...) // ARTAN DEĞER GİRERSEN HATAVERİR.
```

### 3.**The SQL UPDATE Statement**

 `UPDATE` deyimi, bir tablodaki mevcut kayıtları değiştirmek için kullanılır.

```sql
UPDATE table_name
SET column1 = value1, column2 = value2, ...
WHERE condition;
```

### 4.**The SQL DELETE Statement**

`DELETE` ifadesi, bir tablodaki mevcut kayıtları silmek için kullanılır.

```sql
DELETE FROM table_name WHERE condition;
```

### 5.**The SQL TRUNCATE Statement**

`TRUNCATE`, SQL dilinde veritabanındaki bir tabloyu hızlı bir şekilde temizlemek (tüm içeriği silmek) için kullanılan bir komuttur. TRUNCATE komutu, DELETE komutundan farklı olarak daha hızlı çalışır ve verileri fiziksel olarak silerken, veritabanı loglarında daha az kayıt oluşturur.

```sql
TRUNCATE TABLE table_name;
```

### ! Where ile kullanabileceğimiz operatörler !
![Untitled 6](https://github.com/berkcicekk/Learning-SQL/assets/90208101/67e52a61-1af5-41da-bacc-7841ee48fc50)

### 5.**The SQL AND, OR and NOT Operators**

```sql
WHERE cümlesi AND, OR ve NOT operatörleriyle birleştirilebilir.

AND ve OR operatörleri, kayıtları birden fazla koşula göre filtrelemek için kullanılır:

AND operatörü, AND ile ayrılmış tüm koşullar DOĞRU ise bir kaydı görüntüler.
OR operatörü, OR ile ayrılmış koşullardan herhangi biri DOĞRU ise bir kaydı görüntüler.
NOT operatörü, koşul(lar) DOĞRU DEĞİL ise bir kaydı görüntüler.
```

**AND Syntax ( AND Operatörü 1. Koşul ve 2. Koşulun doğru olması durumunda çalışır )**

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 AND condition2 AND condition3 ...;
```

OR **Syntax ( 1. Koşul ya da 2. Koşulun doğru olması durumunda çalışır )**

```sql
SELECT column1, column2, ...
FROM table_name
WHERE condition1 OR condition2 OR condition3 ...;
```

**NOT Syntax**

```sql
SELECT column1, column2, ...
FROM table_name
WHERE NOT condition;
```

### 6.**DISTINC OPERATORS**

`DISTINCT` komutu, veritabanında tekrarlayan değerleri çıkarmak ve yalnızca benzersiz (tekil) değerleri elde etmek için kullanılır. Yani, "DISTINCT" komutu sayesinde sorgu sonucunda yalnızca farklı değerlere sahip olan satırlar görüntülenir, aynı değere sahip olan satırlar ise bir kez görüntülenir.

```sql
SELECT DISTINCT column1, column2, ...
FROM table_name;
```

### 7.**The SQL ORDER BY Keyword**

ORDER BY anahtar sözcüğü, sonuç kümesini artan veya azalan düzende sıralamak için kullanılır. ORDER BY anahtar sözcüğü, kayıtları varsayılan olarak artan düzende sıralar. Kayıtları azalan düzende sıralamak için DESC anahtar sözcüğünü kullanın.

```sql
SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC; 
// ASC KUCUKTEN BUYUGE 
// DESC BUYUKTEN KUCUGE 
```

### 8.**The SQL TOP Keyword**

"TOP" komutu, veritabanından belirli bir sayıda satırı almak için kullanılan bir sorgu ifadesidir. Bu komut, genellikle veritabanından *ilk n adet satırı çekmek için kullanılır*. "TOP" komutu, farklı veritabanı yönetim sistemlerinde farklı şekillerde kullanılabilir.

TOP KOMUTU 2 FARKLI SEKILDE KULLANILIR :

```sql
SELECT TOP n 
column1, column2, ...
FROM table_name;
WHERE <ŞARTLAR>
```

- "n", çekmek istediğiniz ilk n adet satır sayısını belirtir.
- "column1", "column2" gibi sütunlar, tablodan çekmek istediğiniz verilerin sütunlarıdır.
- "table_name", verilerin çekileceği tablonun adını belirtir.

Örnek olarak, bir "Customers" tablosunda ilk 5 müşteriyi listelemek istediğimizi düşünelim:

```sql
SELECT TOP 5 CustomerID, CustomerName, City
FROM Customers;
```

## AGGREGATE FUNCTİONS ( SUM,MIN,MAX,AVG,COUNT )

```sql
SELECT
SUM(PRICE), COUNT(ID),MIN(PRICE)
,MAX(PRICE),AVG(PRICE)
FROM TABLODADI
```

**SUM(PRICE):** "PRICE" sütunundaki tüm değerlerin toplamını hesaplar. Bu, tablodaki "PRICE" sütunundaki tüm değerleri toplayarak bir toplam değer elde eder.

**COUNT(ID):** "ID" sütunundaki tüm değerlerin sayısını hesaplar. Bu, tablodaki "ID" sütunundaki tüm satırların sayısını verir.

**MIN(PRICE)**: "PRICE" sütunundaki en küçük değeri bulur. Bu, tablodaki "PRICE" sütunundaki en düşük değeri gösterir.

**MAX(PRICE):** "PRICE" sütunundaki en büyük değeri bulur. Bu, tablodaki "PRICE" sütunundaki en yüksek değeri gösterir.

**AVG(PRICE):** "PRICE" sütunundaki tüm değerlerin ortalamasını hesaplar. Bu, tablodaki "PRICE" sütunundaki değerlerin toplamını alıp, satır sayısına bölererek ortalama değeri elde eder.
![Untitled 7](https://github.com/berkcicekk/Learning-SQL/assets/90208101/e9aa1794-11cc-4524-bb32-5722a9d3eab0)

### GOURP BY

GROUP BY, "her ülkedeki müşteri sayısını bul" gibi özet satırlarına sahip olan aynı değerlere sahip satırları gruplamak için kullanılan bir SQL anahtar kelimesidir. ***COUNT, SUM, AVG*** vb. gibi toplama işlevleriyle sıklıkla kullanılır. `GROUP BY` ifadesi, bir `SELECT` ifadesinde WHERE ifadesinden sonra gelir ve sonuç kümesini gruplamak için kullanılacak bir veya daha fazla sütunu takip eder.

```sql
SELECT 
KOLON1, KOLON2 ..
SUM(PRICE), COUNT(ID),MIN(PRICE),MAX(PRICE),AVG(PRICE)
FROM TABLOADI
GROUP BY KOLON1,KOLON2...
```

### GOURP BY ORNEK KULLANIM 1 :

GROUP BY, "her ülkedeki müşteri sayısını bul" *gibi* özet satırlarına sahip olan aynı değerlere sahip satırları gruplamak için kullanılan bir SQL anahtar kelimesidir. *COUNT, SUM, AVG* vb. gibi toplama işlevleriyle sıklıkla kullanılır. `GROUP BY` ifadesi, bir `SELECT` ifadesinde `WHERE` ifadesinden sonra gelir ve sonuç kümesini gruplamak için kullanılacak bir veya daha fazla sütunu takip eder.

```sql
SELECT 
KOLON1, KOLON2 ..
SUM(PRICE), COUNT(ID),MIN(PRICE),MAX(PRICE),AVG(PRICE)
FROM TABLOADI
GROUP BY KOLON1,KOLON2...
```
![Untitled 8](https://github.com/berkcicekk/Learning-SQL/assets/90208101/c08a46ae-ae3f-4985-b6f0-34be103175c8)

### GOURP BY ORNEK KULLANIM 2 :

- **`SELECT *`**: Tüm sütunları seçer.
- **`CONVERT(DATE, DATE_) AS DATE2`**: "DATE_" sütununu "DATE" veri türüne dönüştürerek "DATE2" adında yeni bir sütun olarak getirir.
- **`FROM SALES`**: "SALES" tablosundan verileri alır.
- **`WHERE CITY = 'ANKARA'`**: Şehri 'ANKARA' olan satırları filtreler.
- **`ORDER BY DATE_`**: Sonuçları "DATE_" sütununa göre sıralar.

```sql
SELECT *, 
       CONVERT(DATE, DATE_) AS DATE2
  FROM SALES
 WHERE CITY = 'ANKARA'
ORDER BY DATE_;

SELECT CONVERT(DATETIME, '2019-01-01 08:46:10.000');
```

### GOURP BY ORNEK KULLANIM 3 :

```sql
SELECT CITY,DATE2,SUM(TOTALPRICE) AS TOTALPRICE 
--CITY' sütunu, şehir adını; 
--'DATE2' sütunu, satışın gerçekleştiği tarihi; '
--SUM(TOTALPRICE)' ifadesi ise tarih bazında toplam fiyatı gösterir. 
--Sonuç sütunlarına 'TOTALPRICE' adı verilir.

FROM SALES WHERE CITY ='ANKARA'
GROUP BY CITY,DATE2 --STÜNLARA GÖRE GRUPLAMA YAPAR
ORDER BY CITY,DATE2 --NASIL SIRALANACAGINI GOSTERIR
```

### GOURP BY ORNEK KULLANIM 4 :

*bir günün mağaza bazkı satış rakamlarını getirme*  

```sql
SELECT DATE2,CITY,SUM(TOTALPRICE) FROM SALES
--DATE2' sütunu, satış tarihini; 
--'CITY' sütunu, satışın yapıldığı şehri; 
--'SUM(TOTALPRICE)' ifadesi, o tarih ve şehir kombinasyonunda toplam ne kadar gelir elde edildiğini gösterir.
WHERE DATE2='2019-01-01'
--yalnızca 'DATE2' sütunu '2019-01-01' olan satırları seçmesini sağlar.
GROUP BY DATE2,CITY --'DATE2' ve 'CITY' sütunlarına göre gruplama yapılır. 
ORDER BY DATE2,SUM(TOTALPRICE) DESC -- tarih sırasına göre sıralanır ve toplam fiyatlarına göre büyükten küçüğe sıralanır
```

### GOURP BY ORNEK KULLANIM 5 :

*Mağazalara GÖre Satış Rakamını Getirme*

Ayları guncelleme update kodu :

```sql
SELECT * FROM SALES

UPDATE SALES SET MONTHNAME_='01.OCAK' WHERE DATEPART(MONTH,DATE2)=1
UPDATE SALES SET MONTHNAME_='02.SUBAT' WHERE DATEPART(MONTH,DATE2)=2
UPDATE SALES SET MONTHNAME_='03.MART' WHERE DATEPART(MONTH,DATE2)=3
UPDATE SALES SET MONTHNAME_='04.NİSAN' WHERE DATEPART(MONTH,DATE2)=4
UPDATE SALES SET MONTHNAME_='05.MAYIS' WHERE DATEPART(MONTH,DATE2)=5
UPDATE SALES SET MONTHNAME_='06.HAZİRAN' WHERE DATEPART(MONTH,DATE2)=6
UPDATE SALES SET MONTHNAME_='07.TEMMUZ' WHERE DATEPART(MONTH,DATE2)=7
UPDATE SALES SET MONTHNAME_='08.AĞUSTOS' WHERE DATEPART(MONTH,DATE2)=8
UPDATE SALES SET MONTHNAME_='09.EYLÜL' WHERE DATEPART(MONTH,DATE2)=9
UPDATE SALES SET MONTHNAME_='10.EKİM' WHERE DATEPART(MONTH,DATE2)=10
UPDATE SALES SET MONTHNAME_='11.KASIM' WHERE DATEPART(MONTH,DATE2)=11
UPDATE SALES SET MONTHNAME_='12.ARALIK' WHERE DATEPART(MONTH,DATE2)=12
```

```sql
SELECT MONTHNAME ,SUM(TOTALPRICE) AS TOTALPRICE
FROM SALES 

GRUOP BY MONTHNAME_
OREDE BY MONTHNAME_
```
![Untitled 9](https://github.com/berkcicekk/Learning-SQL/assets/90208101/77d4e5d8-6a0d-4239-abb2-eb398c87225c)

### GOURP BY ORNEK KULLANIM 6 :

*Ürün Kategorilerine göre satış rakamlarını getirme* 

```sql
SELECT CATEGORY1, CATEGORY2, CATEGORY3, CATEGORY4,
       SUM(TOTALPRICE) AS TOTAL_SALES,--'SALES' tablosundaki 'TOTALPRICE' sütunundaki değerlerin toplamını alır. Toplamı 'TOTAL_SALES' olarak adlandırır.
       COUNT(*) AS ROW_COUNT,--Tablodaki satır sayısını hesaplar ve 'ROW_COUNT' olarak adlandırır.
       SUM(AMOUNT) AS TOTAL_AMOUNT--SALES' tablosundaki 'AMOUNT' sütunundaki değerlerin toplamını alır. Toplamı 'TOTAL_AMOUNT' olarak adlandırır
FROM SALES
GROUP BY CATEGORY1, CATEGORY2, CATEGORY3, CATEGORY4
ORDER BY CATEGORY1, CATEGORY2, CATEGORY3, CATEGORY4;
```

### GOURP BY ORNEK KULLANIM 7  :

*Mağazaların müşteri sayılarını getirme*  

```sql
SELECT CATEGORY1, CATEGORY2, CATEGORY3, CATEGORY4,
       SUM(TOTALPRICE) AS TOTAL_SALES,--'SALES' tablosundaki 'TOTALPRICE' sütunundaki değerlerin toplamını alır. Toplamı 'TOTAL_SALES' olarak adlandırır.
       COUNT(*) AS ROW_COUNT,--Tablodaki satır sayısını hesaplar ve 'ROW_COUNT' olarak adlandırır.
       SUM(AMOUNT) AS TOTAL_AMOUNT--SALES' tablosundaki 'AMOUNT' sütunundaki değerlerin toplamını alır. Toplamı 'TOTAL_AMOUNT' olarak adlandırır
FROM SALES
GROUP BY CATEGORY1, CATEGORY2, CATEGORY3, CATEGORY4
ORDER BY CATEGORY1, CATEGORY2, CATEGORY3, CATEGORY4;
```

### GOURP BY ORNEK KULLANIM 8  :

*Belli bir cironun üzerinde satış yapan mağazaları getirme.*

```sql
SELECT
    CITY,
    SUM(TOTALPRICE) AS TOTALPRICE, -- "TOTALPRICE" sütunundaki değerlerin toplamını hesaplar ve "TOTALPRICE" olarak adlandırır.
    COUNT(DISTINCT CUSTOMERNAME) AS CUSTOMERCOUNT --Benzersiz müşteri sayısını hesaplar ve "CUSTOMERCOUNT" olarak adlandırır.
FROM SALES
GROUP BY CITY
HAVING COUNT(DISTINCT CUSTOMERNAME) > 500 AND SUM(TOTALPRICE) > 40000 --Gruplama sonrası sonuçları filtreler. Sadece benzersiz müşteri sayısı 500'den büyük ve toplam satış fiyatı 40000'den büyük olan grupları alır.
ORDER BY TOTALPRICE DESC; --
```

## BÖLÜM SONU ÖZET

1. **SQL Server'a Bir Database Nasıl Restore Edilir**:
    - SQL Server Management Studio'yu (SSMS) açın.
    - Bağlantı kurduğunuz sunucunun altındaki "Databases" kısmına sağ tıklayın ve "Restore Database" seçeneğini seçin.
    - "Source" bölümünde yedekleme kaynağınızı seçin.
    - "Destination" bölümünde restore edeceğiniz veritabanının adını ve dosya yollarını belirtin.
    - "Options" bölümünde gerekli ayarları yapın ve "OK" diyerek restore işlemini başlatın.
2. **Aggregate Function (Toplu İşlev) Nedir**:
    - Aggregate function, veritabanı sorgularında kullanılan toplu işlevlerdir.
    - Veri kümesi üzerinde işlem yapar ve tek bir sonuç üretir.
    - Çeşitleri: MIN (minimum), MAX (maksimum), AVG (ortalama), SUM (toplam), COUNT (sayım), COUNT DISTINCT (benzersiz sayım).
3. **GROUP BY Nedir ve Nasıl Kullanılır**:
    - GROUP BY, verileri belirtilen sütuna göre gruplar.
    - Agregate function'lar ile birlikte kullanılır, böylece her grup için bir sonuç elde edilir.
    - Örneğin, belirli bir kritere göre grupladığınızda toplama, ortalama vb. işlemleri her grupta uygulayabilirsiniz.
4. **MIN, MAX, AVG, COUNT, COUNT DISTINCT Komutları**:
    - MIN: Veri kümesindeki en küçük değeri döndürür.
    - MAX: Veri kümesindeki en büyük değeri döndürür.
    - AVG: Veri kümesindeki sayısal değerlerin ortalamasını döndürür.
    - COUNT: Veri kümesindeki toplam satır sayısını döndürür.
    - COUNT DISTINCT: Benzersiz değerlerin sayısını döndürür.
5. **Excel'de Özet Tablo Kullanımı**:
    - Verilerinizi içeren hücre aralığını seçin.
    - "Insert" sekmesinden "PivotTable" seçeneğini seçin.
    - "Create PivotTable" penceresinde sütunlarınızı "Rows" ve "Values" alanlarına sürükleyin.
    - "Values" alanında toplama işlemleri uygulayabilirsiniz.
6. **Excel'den Veritabanına Bağlanma ve Sorgu Çekme**:
    - "Data" sekmesinden "Get Data" veya "From Database" seçeneğini seçin.
    - Gerekli bağlantı bilgilerini girin.
    - "Navigator" penceresinde tablo veya sorguyu seçerek veriyi çekebilirsiniz.
7. **HAVING Komutu Nedir ve Nasıl Kullanılır**:
    - HAVING, GROUP BY ile birlikte kullanılır ve grupları filtrelemek için kullanılır.
    - GROUP BY'dan sonra gelir ve aggregate function'lar ile kullanılır.
    - Örneğin, belirli bir koşulu sağlayan grupları seçmek için kullanılır.
8. **GROUP BY Kullanılan Sorguda Order By Nasıl Kullanılır**:
    - GROUP BY'dan sonra ORDER BY ile birlikte kullanılır.
    - GROUP BY ile oluşturulan grupları belirli bir sıraya göre sıralamak için kullanılır.
9. **Raporların Sorgularını Aggregate Function ve GROUP BY İle Nasıl Yazabilirsiniz**:
    - Öncelikle, raporunuzun amacını anlayın.
    - Hangi verilere ihtiyacınız olduğunu belirleyin ve GROUP BY ile hangi alanlarda gruplama yapmanız gerektiğini belirleyin.
    - Raporunuzda kullanılacak toplama işlevlerini (MIN, MAX, AVG, COUNT, vb.) seçin ve sorgunuzu oluşturun.
    - HAVING ve ORDER BY ifadelerini kullanarak raporunuzu daha fazla özelleştirebilirsiniz.
  
  ![Uploading Untitled 9.png…]()
![Uploading Untitled 13.png…]()

# **1) Metinsel Veri Tipleri**

***! EN COK YER KAPLAYAN VERI TIPIDIR !***

> char: Unicode’u desteklemeyip char(n) şeklinde kullanılırlar. 8000 karaktere kadar değer alabilirler.Belirtilenden(n) az karakter girilse dahi giriş yapılan boyut kadar yer kaplar.Veri giriş boyutları benzer,sabit olan veri kümelerinde kullanılması önerilir
> 
> 
> ***nchar:** Unicode(uluslararası karakter setini,tanımlı tüm alfabeleri içerirç)destekler.Chardan farklı olarak maksimum 4000 karaktere kadar değer alabilir.*
> 
> ***varchar:** Chardan farklı olarak verinin boyutu kadar yere kaplar. 8000 karaktere kadar depolama yapar.Birbirinden farklı uzunlukta veri girişi yapılacağı zaman kullanılması önerilir. varchar(MAX) kullanımı ile 2GB’a kadar depolama yapılabilir.*
> 
> ***nvarchar:**Verinin boyutu kadar yer kaplar.Varchardan farklı olarak unicode’u destekler.4000 karaktere kadar değer alabilir.*
> 
> ***text:** Belirtilenden az değer girilse bile boyutu kadar yer kaplar.2GB’a kadar metinsel veri depolar.Unicode’u desteklemez.*
> 
> ***ntext:** Text’den farklı olarak girilen karakter boyutu kadar yer kaplar ve unicode’u destekler.*
> 

# **2) Binary(İkilik) Veri Tipleri**

> binary: 1 ve 0 ları temsil eden ikilik taban veri tipidir.Sabit uzunluklu veri tiplerinde kullanılırlar.8000 bytre’a kadar depolama yapabilir.
> 
> 
> ***varbinary:** Binary’den farklı olarak girilen karakter kadar yer kaplar.Bu yüzden uzunlukların değişken olduğu durumlarda tercih edilir.*
> 
> ***image:** Resim dosyalarını saklamak için kullanılır. En fazla 2 GB’a kadar veri depolar. Bunun yerine varbinary(MAX) kullanılması tercih edilir.*
> 

# **3) Sayısal Veri Tipleri**

> bit: Bir byte uzunluğunda tam sayı veri tipidir.Genellikle evet/hayır şeklinde mantıksal bilgileri tutmak için kullanılır.
> 
> 
> ***int:** 4 byte büyüklüğünde, -2 milyar /+2 milyar arasında değer tutabilen tam sayı veri tipidir.*
> 
> ***bigint:** 8 byte büyüklüğünde -2⁶³ ve 2⁶³ arasında değer tutabilen tam sayı veri tipidir.*
> 
> ***smallint:** 2 byte büyüklüğünde -32.768 ve 32.768 arası değer alabilen tam sayı veri tipidir.*
> 
> ***tinyint:** 1 byte büyüklğüne sahip, 0–255 arası tam sayı veriler için kullanılan tam sayı veri tipidir.*
> 
> ***decimal,numeric:** İkisinin de kullanımı aynıdır.Bu veri tipinde saklanacak sayının basamak sayısı tanımlanabilir.Veri tipi boyutu belirtilen basamak sayılarına göre değişkenlik gösterebilir.-38 ve +38 basamak arası verileri depolayabilir. -10³⁸ ,10³⁸ arası ondalık ve tam sayı türünde veri saklayabilir.*
> 

# **4)Parasal Veri Tipleri**

> money: 8 byte boyutunda, yaklaşı -2⁶⁴ ile 2⁶⁴ arasında parasal değerleri tutmak için kullanılır. 4 basamağa kadar duyarlı ondalık tipli verileri saklar.
> 
> 
> ***smallmoney:** 4 byte uzunluğunda yaklaşık -214.000 ile 214.000 arası parasal değerleri tutmak için kullanılır.Money tipinde olduğu gibi 4 basamağa kadar duyarlı ondalık tipli verileri saklarken kullanılır.*
> 

# **5)Tarih-Zaman Veri Tipleri**

> date: Tarihleri YYYY-AA-GG (yıl-ay-gün) formatında saklar. 3 byte uzunluğunda veri tipidir.
> 
> 
> ***smalldatetime:** Tarih ve zaman verilerini yıl-ay-gün ve saat-dakika-saniye-salise şeklide saklar. 4 byte uzunluğunda veri tipidir.*
> 
> ***datetime:** YYYY-AA-GG şeklinde tarih ve zaman verilerini tutan 8 byte uzunluğunda veri tipidir. 1 Ocak 1753–31 Aralık 9999 arası veriler için kullanılır.*
> 
> ***datetime2**: Datetime’dan farklı olarak 1 Ocak 0001–31 Aralık 9999 tarihleri arasu verileri tutan ekstra olarak salise hassasiyeti daha yüksektir.Kapladığı alan salise hassasiyetine göre 6–8 byte arası değişebilir.*
> 
> ***time:** Sadece saat verilerini saat-dakika-saniye-salise(7 basamaklı) şeklinde saklayan , boyutu kullanıcı tarafından değiştirilebilen 3–5 byte arası yer kaplayan veri tipidir.*
> 
> ***datetimeoffset:** Ülkelere göre değişen zaman farkını hesaplayıp tutarken kullanılır.*
> 

# **6) Diğer Veri Tipleri**

> sql_variant: sayı,metin, binary gibi farklı veri tiplerini depolamak için kullanılan veri tipidir.Yani bir sütun ya da fonksiyonda birden fazla veri tipi kullanmamız gerektiğinde tercih etmeliyiz.
> 
> 
> ***xml:** XML türünde veri saklamak için kullanılır. Kapasitesi 2 GB’dır.Bellekteki boyutu, saklanan XML verisine göre değişkenlik gösterir.*
> 
> ***geometry:** Öklid koordinat sistemine ait verileri tutmak için kullanılır.Geometrik şekillerin en-boy-yükselik verilerini saklar.*
> 
> ***timestamp:** Tabloya kayıt eklendiğinde , güncellendiğinde binary türünde özel değer alan veri tipidir.*
> 
> ***uniqueidentifier:** 16 byte uzunluğunda benzersiz GUID tipinde veri tutar.İki GUID birbirinden tamamen farklıdır eşit olamazlar.*
> 
> ***hierarchyid:** Ağaç veri modeli ve ya hiyerarşik olarak sınflandırılmış verileri saklamak için kullanılır.*
> 
> ***geography:** Coğrafi koordinat ve GPS verilerini tutmak için kullanılır.*
> 

[Kaynakça:](https://docs.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-2017) **https://docs.microsoft.com/en-us/sql/t-sql/data-types/data-types-transact-sql?view=sql-server-2017**


# SQL RDMS ( İLİŞKİSEL VERTABANI KAVRAMI )

![Untitled 14](https://github.com/berkcicekk/Learning-SQL/assets/90208101/13fd8cc6-6ead-4dfa-9411-0a74c0417d4e)

<aside>
⚠️ Default Value Or Binding boş gelirse `GETDATE()` yaz

</aside>

<aside>
⚠️ ID alanını otomatık artan işaretleme : Her kaydın benzersiz bir ID değeri olacağı için farklı kayıtları rahatlıkla ayırt edebilirsiniz. Bu, verilerin birbirine karışmasını engeller.

</aside>

### Relation Kavramı

lişkisel veritabanı sistemlerinde "relation" terimi, tablolar arasındaki yapılardan birini ifade eder. Bir relation, verilerin mantıksal olarak düzenlendiği ve ilişkilendirildiği bir yapıdır.

![Untitled 15](https://github.com/berkcicekk/Learning-SQL/assets/90208101/ff29ead3-1761-4950-afba-1db0ae9604c8)
![Untitled 16](https://github.com/berkcicekk/Learning-SQL/assets/90208101/4eb4484f-691c-49c9-b87c-d4b20e84f926)
![Untitled 17](https://github.com/berkcicekk/Learning-SQL/assets/90208101/e5f25697-c11c-41a3-9b85-1ddfa790e189)
<aside>
⚠️ birincil anahtarlar her kaydı benzersiz bir şekilde tanımlamak için kullanılırken, yabancı anahtarlar tablolar arasındaki ilişkileri tanımlamak ve bu ilişkileri sürdürmek için kullanılır. Yabancı anahtarlar, bir tablodaki verinin başka bir tabloyla ilişkilendirilmesine ve veritabanının veri bütünlüğünün sağlanmasına yardımcı olur.

</aside>

![Untitled 18](https://github.com/berkcicekk/Learning-SQL/assets/90208101/325ca62c-03fb-4119-aa36-386a53c94fec)
![Untitled 19](https://github.com/berkcicekk/Learning-SQL/assets/90208101/3bcc6fbb-9b9f-44aa-afda-9b95db5d0359)

### Scriptitle Tablo Oluşturma

```sql
CREATE TABLE COUNTRIES ( -- "COUNTRIES" adında yeni bir tablo oluşturulacağı
ID TINYINT IDENTITY(1,1), --tablo stünları tanımlama | IDENTITY(1,1) ifadesi, otomatik artan bir değer olduğu
COUNTRY VARCHAR (50) -- 
CONSTRAINT PK_COUNTRIES PRIMARY KEY CLUSTERED (ID ASC))
```

**`CONSTRAINT PK_COUNTRIES PRIMARY KEY CLUSTERED (ID ASC)`**: Bu bölüm, tablodaki birincil anahtarın tanımlandığını belirtir:

- **`CONSTRAINT PK_COUNTRIES`**: Bu, birincil anahtarın bir adı olduğunu belirtir. "PK_COUNTRIES" adı verilen birincil anahtar kullanılıyor.
- **`PRIMARY KEY CLUSTERED`**: Bu, birincil anahtarın tabloda bir grup olarak (clustered) saklanacağını belirtir.
- **`(ID ASC)`**: Bu, birincil anahtarın "ID" sütununu kullanarak artan bir şekilde (ASC) sıralanacağını belirtir. Yani, "ID" değeri küçükten büyüğe doğru sıralanmış olur.

---

## BÖLÜM SONU

**İlişkisel Veritabanı (RDBMS) Nedir?**

İlişkisel Veritabanı Yönetim Sistemi (RDBMS), verileri tablo şeklinde organize eden ve bu tablolardaki veriler arasındaki ilişkileri tanımlayabilen bir veritabanı türüdür.  İlişkisel veritabanları, SQL (Structured Query Language) adlı dil kullanılarak veri manipülasyonu ve sorgulama işlemlerinin gerçekleştirildiği sistemlerdir.

**RDMS Sistemi Temelde Nasıl Çalışır? (Fatura Örneği)**

1. **Veritabanı Oluşturma:** bir RDBMS ile bir veritabanı oluşturulur. Bu veritabanı, faturaların ve müşteri bilgilerinin saklanacağı tabloları içerebilir.
2. **Tablo Oluşturma:** Faturalar ve müşteri bilgileri için ayrı ayrı tablolar oluşturulur. Her tablo belirli bir konsepti (örneğin, faturalar veya müşteriler) temsil eder. Tablolar, sütunlar (alanlar) ve sütunların veri türleri ile tanımlanır.
3. **İlişki Tanımlama:** Faturalar ve müşteri bilgileri arasındaki ilişkiyi tanımlamak için yabancı anahtarlar kullanılır. Fatura tablosunda bir "Müşteri Kimliği" (CustomerID) sütunu olabilir ve bu sütun, müşteri tablosundaki birincil anahtar olan "Müşteri Kimliği" sütunu ile ilişkilendirilir.
4. **Veri Ekleme ve Sorgulama:** Fatura oluşturulduğunda, fatura bilgileri fatura tablosuna eklenirken, ilgili müşteri bilgileri müşteri tablosundan çekilir ve ilişki sayesinde ilişkilendirilir. Sorgular, SQL kullanılarak yapılarak faturaların ve müşteri bilgilerinin çeşitli yollarla çekilmesi veya güncellenmesi sağlanır.

**Bir E-Ticaret Sistemi Temelde Nasıl Çalışır?**

Bir E-Ticaret sistemi, kullanıcıların ürünleri seçmelerine, sepetlerine eklemelerine, ödemeleri gerçekleştirmelerine ve siparişleri tamamlamalarına olanak tanır. Temel adımlar şunlar olabilir:

1. **Ürün Yönetimi:** Ürünler ve özellikleri (fiyat, stok durumu vb.) bir veritabanında saklanır.
2. **Kullanıcı Hesapları:** Kullanıcılar kaydolur veya giriş yapar. Kullanıcı bilgileri ve sipariş geçmişi gibi veriler veritabanında tutulur.
3. **Sepet İşlemleri:** Kullanıcılar ürünleri seçer ve sepetlerine ekler. Sepet verisi oturum (session) veya kullanıcı hesabına bağlı olarak saklanır.
4. **Ödeme İşlemleri:** Kullanıcılar sepetlerini görüntüler, ödeme yapar. Ödeme işlemi sonrası sipariş verisi oluşturulur.
5. **Sipariş İşlemleri:** Sipariş verisi, kullanıcı bilgileri ve ürün detayları içerir. Sipariş veritabanında saklanır.

**RDMS Veritabanı Mimarisi Nasıl Oluşturulur?**

Bir RDBMS veritabanı mimarisi oluştururken aşağıdaki adımlar genellikle takip edilir:

1. **Veri Modellemesi:** Veri ihtiyaçlarınıza uygun bir veri modeli oluşturun. Tabloları, sütunları ve ilişkileri tanımlayın.
2. **Tabloları Oluşturma:** Her veri kategorisi (örneğin, ürünler, müşteriler, siparişler) için ayrı tablolar oluşturun. Tablolardaki sütunları ve veri tiplerini belirleyin.
3. **İlişkileri Tanımlama:** Tablolar arasındaki ilişkileri tanımlayın. Yabancı anahtarları kullanarak ilişkileri kurun.
4. **Veri Ekleme:** İlk verileri tablolara ekleyin.
5. **Sorgulama ve Güncelleme:** SQL sorguları kullanarak veritabanını sorgulayın ve güncelleyin. Verileri filtrelemek, eşleştirmek veya dönüştürmek için sorgular oluşturun.
6. **Veri Güvenliği:** Erişim hakları ve güvenlik ayarlarını belirleyin. Kullanıcıların sadece gerekli verilere erişimini sağlayın.
7. **Performans İyileştirmeleri:** Büyük veri kütleleri için performans iyileştirmeleri yapın. İndeksler ve sorgu optimizasyonu gibi teknikleri kullanarak veritabanını hızlandırın.
8. **Yedekleme ve Kurtarma:** Verilerinizi düzenli olarak yedekleyin ve veri kaybını önlemek için kurtarma planları oluşturun.

---

## Alias Kullanımı

Sütunlar veya tablolar için kısa isimler veya takma adlar oluşturmanıza olanak tanıyan bir kavramdır. Aliaslar, sorgularınızı daha okunabilir hale getirmek, sütun isimlerini değiştirmek veya tablo isimlerini kısaltmak gibi durumlarda kullanılır.

- users → u  address → a

SQL'de iki veya daha fazla tabloyu birleştirerek veya ilişkilendirerek kullanmanız gereken durumlar oldukça yaygındır. Bu tür işlemler, ilişkisel veritabanlarında verileri farklı tablolarda saklayarak daha karmaşık ve anlamlı sorgular oluşturmanıza olanak tanır. İşte bu tür senaryolara örnekler:

1. **JOIN İşlemleri**: İki veya daha fazla tabloyu birleştirerek, ortak sütun değerlerine göre verileri eşleştirebilirsiniz. JOIN işlemleri kullanarak farklı tablolardan gelen verileri birleştirebilir ve daha kapsamlı sonuçlar elde edebilirsiniz. INNER JOIN, LEFT JOIN, RIGHT JOIN ve FULL JOIN gibi farklı türlerde birleştirme işlemleri yapabilirsiniz.

Örnek:

```sql
sqlCopy code
SELECT orders.order_id, customers.customer_name
FROM orders
INNER JOIN customers ON orders.customer_id = customers.customer_id;

```

1. **Alt Sorgular**: Bir tabloyu veya alt sorguyu diğer bir sorguda kullanabilirsiniz. Alt sorgular, daha karmaşık mantık veya hesaplamalar gerektiren durumlar için kullanışlıdır.

Örnek:

```sql
sqlCopy code
SELECT product_name
FROM products
WHERE category_id IN (SELECT category_id FROM categories WHERE category_name = 'Electronics');

```

1. **Daha Fazla Tablo İlişkilendirmesi**: Üç veya daha fazla tabloyu ilişkilendirerek daha karmaşık veri analizleri veya raporlar oluşturabilirsiniz.

Örnek:

```sql
sqlCopy code
SELECT customers.customer_name, orders.order_id, order_details.quantity
FROM customers
INNER JOIN orders ON customers.customer_id = orders.customer_id
INNER JOIN order_details ON orders.order_id = order_details.order_id;

```

1. **Alt Sorgu Kullanarak İlişkilendirme**: Alt sorguları, daha fazla tabloyu ilişkilendirirken ve bu ilişkilendirmeyi daha anlamlı hale getirirken de kullanabilirsiniz.

Örnek:

```sql
sqlCopy code
SELECT product_name
FROM products
WHERE category_id IN (SELECT category_id FROM categories WHERE category_name = 'Electronics')
AND unit_price > (SELECT AVG(unit_price) FROM products);

```

## İlişkisel veri tabanı üzerinden groupby örnekleri

```sql
SELECT U.NAMESURNAME
FROM USERS U, ADDRESS A, COUNTRIES C, CITIES CT, TOWNS T, DISTRICTS D
WHERE U.ID = A.USERID AND C.ID = A.COUNTRYID AND CT.ID = A.CITYID
AND T.ID = A.TOWNID AND D.ID = A.DISTRICTID;
```

**`USERS`**, **`ADDRESS`**, **`COUNTRIES`**, **`CITIES`**, **`TOWNS`** ve **`DISTRICTS`** adlı altı farklı tabloyu birleştirerek veri çeker. Her bir tablo belirli verilere sahip olmalıdır.

- **`USERS`** tablosu, kullanıcıların temel bilgilerini içerir. **`ID`** sütunu, kullanıcı kimliklerini temsil eder.
- **`ADDRESS`** tablosu, kullanıcı adreslerini saklar. Kullanıcının adres bilgisi farklı tablolardan alınarak çekilecektir.
- **`COUNTRIES`**, **`CITIES`**, **`TOWNS`** ve **`DISTRICTS`** tabloları, ülke, şehir, ilçe ve kasaba bilgilerini içerir. Bu tablolarda yerleşim yerlerinin isimleri ve kimlikleri bulunur.

Sorgu, belirli bir kullanıcının adını ve soyadını almak için tüm bu tablolardaki ilişkileri kullanır. Örneğin, **`USERS`** tablosundaki bir kullanıcının adres bilgisi **`ADDRESS`** tablosunda saklanır ve **`ID`** alanları aracılığıyla bağlanır. Aynı şekilde, adres bilgisi ülke, şehir, ilçe ve kasaba tablolarıyla ilişkilendirilir.
## İlişkisel tablolardan veri sorgulama

## - JOIN

 SQL de birbiri ile ilişkili tablolardan veri çekmek için JOIN komutlarını kullanırız.
 

![Uploading Untitled 22.png…]()
![Uploading Untitled 21.png…]()

**INNER JOIN**

Tablodaki verileri birleştirerek bize cevabı döndürür.

```sql
SELECT kitaplar.kitap_isim, yazarlar.yas
FROM kitaplar
INNER JOIN yazarlar ON kitaplar.yazarid = yazarlar.id
```

| kitap_isim | yas |
| --- | --- |
| bulantı | 25 |
| gelecek | 60 |

**LEFT JOIN**

İki tabloyu birleştirmenin ikinci yolu ise “LEFT JOIN” kullanmaktır.

Aşağıdaki sql cümlesini ele alalım:

```sql
SELECT kitaplar.kitap_isim, yazarlar.yazar_isim
FROM kitaplar
LEFT JOIN yazarlar ON yazarlar.id = kitaplar.yazarid
```

| kitap_isim | yazar_isim |
| --- | --- |
| saklı ev | ekrem |
| son moda | null |
| gelecek | orhan |
| bir umut | orhan |

**RIGHT JOIN**

LEFT JOIN ile RIGHT JOIN hemen hemen aynıdırlar, RIGHT JOIN cümlesinin yaptığı iş sadece sağdaki tablonun tamamını almaktır.

```sql
SELECT kitaplar.kitap_isim, yazarlar.yazar_isim
FROM kitaplar
RIGHT JOIN yazarlar ON yazarlar.id = kitaplar.yazarid
```

| kitap_isim | yazar_isim |
| --- | --- |
| saklı ev | ekrem |
| son moda | orhan |
| gelecek | orhan |
| bir umut | orhan |
| NULL | isa |

Görüldüğü gibi sağda yer alan yazarlar tablosunun tamamını sonuç olarak aldı ve yazara karşılık gelen bir kitap bulunmadıysa ilgili alanın değerini `“null`” olarak atadı.

İlişkili veritabanlarında “join” cümleleri çok işe yarar, ve genellikle “inner join” pek çok kez kullanılır. LEFT JOIN ile RIGHT JOIN birbirlerine benzerler, sadece biri soldaki, diğeri sağdaki tablonun tamamını alır ve yukarıdaki örnekte olduğu gibi, eğer ilgili yazarın her hangi bir kitabı yoksa, geri döndürdüğü değerlerde “null” kelimesine rastlanır.


# 👽Uygulama2

```sql
SELECT
    -- KULLANICI ADI, AD SOYAD, İL, İLÇE, SEMT, AÇIK ADRES
    U.USERNAME_ AS KULLANICIADI,
    U.NAMESURNAME AS ADSOYAD,
    CT.CITY AS IL,
    T.TOWN AS ILCE,
    D.DISTRICT AS SEMT,
    A.ADDRESSTEXT AS ACIKADRES,
    -- SIPARIS ID, TARİH, TOPLAM TUTAR, ODEME TARİHİ
    O.ID AS SIPARISID,
    O.DATE_ AS TARIH,
    O.TOTALPRICE AS TOPLAMTUTAR,
    P.DATE_ AS ODEMETARIHI,
    -- BANKA ONAY KODU, FATURA TARIHI, FIS NO
    P.APPROVECODE AS BANKAONAYKODU,
    I.DATE_ AS FATURATARIHI,
    I.CARGOFICHENO AS KARGOFISNO,
    -- 
	ITM.ITEMCODE AS URUNKODU, 
	ITM.ITEMNAME AS URUNADI, 
	OD.AMOUNT AS MIKTAR, 
	OD.UNITPRICE AS BIRIMFIYAT,
	OD.LINETOTAL AS SATIRTOPLAMI

FROM
    ORDERS O
INNER JOIN 
    USERS U ON U.ID = O.USERID
INNER JOIN
    ADDRESS A ON A.ID = O.ADDRESSID
INNER JOIN
    CITIES CT ON CT.ID = A.CITYID
INNER JOIN
    TOWNS T ON T.ID = A.TOWNID
INNER JOIN
    DISTRICTS D ON D.ID = A.DISTRICTID
INNER JOIN
    PAYMENTS P ON P.ORDERID = O.ID
INNER JOIN
    INVOICES I ON I.ORDERID = O.ID
INNER JOIN
    ORDERDETAILS OD ON OD.ORDERID = O.ID
INNER JOIN
    ITEMS ITM ON ITM.ID=OD.ITEMID

WHERE
	--U.NAMESURNAME='Ceyda GEZGİNCİ'
   O.ID = 24601;
```

# 👽Uygulama 3

ŞEHİRLERE GÖRE VERİLEN SİPARİŞLERİ TOPLAM OLARAK LİSTELEME

```sql
--ŞEHİRLERE GÖRE TOPLAM VERİLEN SİPARİŞ MİKTARLARI
SELECT
	CT.CITY AS SEHIRADI,
	SUM(OD.LINETOTAL) AS TOPLAMSIPARIS_TUTARI,
	SUM(OD.AMOUNT) AS TOPLAMSIPARIS_ADEDI,
	COUNT(OD.ID) AS TOPLAMSIPARIS_SAYISI

FROM ORDERS O
	INNER JOIN USERS U ON U.ID = O.USERID
	INNER JOIN ADDRESS A ON A.ID = O.ADDRESSID
	INNER JOIN CITIES CT ON CT.ID = A.CITYID
	INNER JOIN TOWNS T ON T.ID = A.TOWNID
	INNER JOIN DISTRICTS D ON D.ID = A.DISTRICTID
	INNER JOIN PAYMENTS P ON P.ORDERID = O.ID
	INNER JOIN INVOICES I ON I.ORDERID = O.ID
	INNER JOIN ORDERDETAILS OD ON OD.ORDERID = O.ID
	INNER JOIN ITEMS ITM ON ITM.ID = OD.ITEMID

GROUP BY CT.CITY
ORDER BY SUM(OD.LINETOTAL) DESC
```

Her şirket her şirkete e-fatura kesebiliyormuş. E-fatura oluşturulunca hedef şirkete kurye ile tebligat gidiyormuş. Bu teslimatta gerçekleşen gecikmeler faturanın zamanaşımına uğraması veya itiraz süresinin geçmesi gibi sorunlara yol açıyormuş. Bu süreç dijitale taşınırsa her şirket kendisine kesilen e-faturaları görüp daha hızlı aksiyon alabilir

Sovos'taki senaryoda da bir e-fatura sağlayıcı (Sovos) ve bir denetleyici kurum (Gelir İdaresi Başkanlığı) aralarındaki süreçleri blockchain üzerinden yürütüyor. Sovos fatura oluşturuyor, GİB faturayı onaylıyor veya reddediyor

## SUBQUERY KAVRAMI

SQL'de alt sorgu (subquery), bir ana sorgunun içinde yer alan ve kendi başına bir sorgu gibi çalışan sorgu parçacığıdır. Alt sorgular, genellikle ana sorgunun sonucunu etkilemek veya daha spesifik verileri çekmek için kullanılır. Alt sorgular, sorguları daha karmaşık hale getirmek yerine daha modüler ve anlaşılır hale getirir.

Alt sorgular iki temel türde olabilir:

1. **Dahili (Inner) Alt Sorgu:** Ana sorgunun WHERE, FROM veya HAVING bölümlerinde kullanılır. Bu tür alt sorgular, genellikle ana sorgunun sonucunu filtrelemek veya sınırlamak amacıyla kullanılır.
2. **Alt Sorgu İçeren (Subquery Containing) Alt Sorgu:** Ana sorgunun SELECT bölümünde kullanılır. Bu tür alt sorgular, ana sorgunun her satırı için ayrı ayrı hesaplamalar yapmak veya alt sorgunun sonuçlarına dayalı işlemler gerçekleştirmek için kullanılır.

Örnekler:

**Dahili Alt Sorgu Örneği:**

```sql

SELECT FirstName, LastName
FROM Customers
WHERE Country IN (SELECT Country FROM Suppliers);
```

Bu sorguda, "Customers" tablosundan müşteri adını ve soyadını alıyoruz ancak sadece "Suppliers" tablosunda yer alan ülkelerden olan müşterileri seçiyoruz.

**Alt Sorgu İçeren Alt Sorgu Örneği:**

```sql

SELECT OrderID, OrderDate, (SELECT COUNT(*) FROM OrderDetails WHERE OrderID = Orders.OrderID) AS ItemCount
FROM Orders;
```

Bu sorguda, "Orders" tablosundaki her siparişin detaylarından kaç ürün olduğunu hesaplıyoruz ve sonucu "ItemCount" sütununda görüntülüyoruz.

Alt sorgular, SQL sorgularını daha esnek ve özelleştirilebilir hale getirmenin yanı sıra, karmaşık veri çekme veya manipülasyon işlemlerini gerçekleştirmek için de kullanılır.

## String İşlemleri

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/a62603a0-4792-476b-9065-e11e6098d5d2/Untitled.png)

`Örnek Senaryo:` Bir veritabanında bulunan "Products" tablosunda ürünlerin isimleri ve açıklamaları saklanmaktadır. Ürün açıklamalarının içindeki ilk 50 karakteri çekmek istiyoruz.

```sql
SELECT ProductName,
       (SELECT SUBSTRING(Description, 1, 50) FROM Products P2 WHERE P2.ProductID = P.ProductID) AS ShortDescription
FROM Products P;
```

Bu sorguda, her ürün için bir alt sorgu kullanarak "Description" sütununun ilk 50 karakterini çekiyoruz. Alt sorgu, ana sorgunun her satırı için ayrı ayrı çalışır ve istenilen substring'i döndürür.

Bu örnek, bir alt sorgu ile substring işleminin nasıl gerçekleştirilebileceğini göstermektedir. Alt sorgu içinde substring işlemi yapılarak verileri daha spesifik bir şekilde çekebilir ve sonuçları istediğiniz gibi formatlayabilirsiniz.


![logo_beyaz2x](https://github.com/berkcicekk/Learning-SQL/assets/90208101/7fd41c9a-14f9-4760-a9f8-a9d87d5f452f)
# 🐲 BERK ÇİÇEK | SERİM YAZILIM









