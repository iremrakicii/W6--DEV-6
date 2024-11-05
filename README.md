SQL Sorgu Açıklamaları

Bu dosya, film veritabanında kullanılan SQL sorgularının amacını ve sonuçlarını açıklar.

---

## 1. Ortalama Kiralama Ücreti Hesaplama

**Sorgu:**
```sql
SELECT AVG (rental_rate) FROM film;
```
Açıklama: Bu sorgu, film tablosundaki tüm filmler için rental_rate (kiralama ücreti) sütununun ortalama değerini hesaplar. Ortalama kiralama ücreti, filmlerin genel olarak kiralama ücretlerinin ne düzeyde olduğu hakkında bilgi verir.

### 2. "C" Harfiyle Başlayan Filmlerin Sayısını Bulma
Sorgu:
```sql
SELECT COUNT(*) FROM film
WHERE title ILIKE 'C%';
```
Açıklama: Bu sorgu, başlığı "C" harfi ile başlayan filmlerin sayısını döndürür. ILIKE ifadesi, büyük-küçük harf duyarsız bir arama sağlar. Bu sayede, "C" harfiyle başlayan filmlerin toplam sayısı elde edilir.

### 3. 0.99 Kiralama Ücreti Olan Filmler Arasındaki En Uzun Filmi Bulma
Sorgu:
```sql
SELECT MAX (length) FROM film
WHERE rental_rate=0.99;
```
Açıklama: Bu sorgu, kiralama ücreti 0.99 olan filmler arasından en uzun süreye sahip filmi bulur. MAX(length) ifadesi, bu koşula uygun olan filmler arasından length (uzunluk) sütununun maksimum değerini döndürür.

### 4. Uzunluğu 150 Dakikadan Fazla Olan Filmler İçin Farklı Yedekleme Maliyetlerini Sayma
Sorgu:
```sql
SELECT COUNT(DISTINCT replacement_cost) FROM film
WHERE length>150;
```
Açıklama: Bu sorgu, uzunluğu 150 dakikadan fazla olan filmler arasındaki farklı replacement_cost (yedekleme maliyeti) değerlerini sayar. COUNT(DISTINCT replacement_cost) ifadesi, yalnızca farklı değerleri dikkate alarak, bu filmler için yedekleme maliyetlerinin kaç farklı değere sahip olduğunu belirler.
