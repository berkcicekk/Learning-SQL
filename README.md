## Veritabanı nedir?

Veritabanı, kolayca erişilebilecek, geri alınabilecek, yönetilebilecek ve güncellenebilecek şekilde depolanan ilgili bilgilerin sistematik veya organize bir koleksiyonudur

## Veritabanı tablosu nedir?

Veritabanı tablosu, verilerin düzenli bir şekilde saklandığı, satır ve sütunlardan oluşan bir yapıdır. Her bir tablo, belirli bir konu veya veri türüyle ilgili bilgileri içerir. Örneğin, bir müşteri veritabanında müşteri adı, adresi, telefon numarası gibi bilgilerin bulunduğu bir tablo olabilir. Veritabanı tabloları, verilerin daha düzenli ve erişilebilir bir şekilde saklanmasını sağlar ve veri işleme işlemlerinin daha kolay yapılmasına olanak tanır.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d40f109c-b267-4b2c-ac10-3fce640fb697/Untitled.png)

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/d40f109c-b267-4b2c-ac10-3fce640fb697/Untitled.png)

## D**atabase relationship nedir?**

verileri almak için birleştirme ifadeleri kullanılarak oluşturulan tablolar arasındaki ilişkilerdir. Tablo yapılarını iyileştirmeye ve gereksiz verileri azaltmaya yardımcı olur.

**1. One-to-One:**

Bire bir ilişki, her tablonun diğer tabloda yalnızca bir eşleşen satıra sahip olabileceği iki tablo arasındaki ilişkidir.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/7d12d916-f5c4-4492-ace5-36337b4f7bb9/Untitled.png)

Örnek olarak yukarıdaki ekran görüntüsünü kullanırsak, iş gerekçesi, her çalışanın ödeme ayrıntılarının, çalışanın iletişim bilgilerine göre ayrı bir tabloda saklanması gerektiğidir. Böyle bir durumda, Ücret tablosunda, Çalışanlar tablosundaki belirli bir çalışanla eşleşen yalnızca bir satır olabilir. 

**2. One-to-Many:**

tablolardan birinde birden çok eşleşen satıra izin vermesi dışında bire bir ilişkiye benzer.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/0c221c43-31f4-477b-ad03-d30acf991c29/Untitled.png)

Yukarıdaki örnekte, her yazarın birçok kitabı olabilir ancak her kitabın yalnızca bir yazarı olabilir. Bu nedenle Books tablosunun aynı AuthorId değerine sahip birden çok satır içermesine izin verilir. Bir yazar beş kitap yayınlamışsa, Yazarlar'da o yazar için bir satır ve Kitaplar'da her biri o yazarın AuthorId'sine sahip beş satır olacaktır.

**3. Many-to-Many:**

ilişkinin her bir tarafı birden çok satır içerebilir.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/1f898047-982a-4066-9cf1-979746bdc175/Untitled.png)

Bu örnekte, her kitabın birden çok yazarı olabilir. Bu nedenle, hem AuthorId'i hem de BookId'yi saklayan bir arama tablosu ("bağlantı tablosu" olarak da bilinir) oluşturdum. Bu iki sütun, tablonun birincil anahtarı olacak şekilde yapılandırılabilir (bu durumda bunlar "bileşik birincil anahtar" veya yalnızca "bileşik anahtar" olur) veya birincil anahtar olarak ayrı bir sütun oluşturabilirsiniz. Bu durumda Kitaplar tablosunda AuthorId bulunmadığına dikkat edin. Aynı BookId için birçok AuthorId'e sahip olabilmemiz için bu sütun AuthorBooks tablosuna taşındı.

![Untitled](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fdadf7b9-d2d9-4a69-8c45-8146e427bfd2/Untitled.png)
