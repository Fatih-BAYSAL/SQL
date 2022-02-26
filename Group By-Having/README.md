# Homework - Group By, Having

Aşağıdaki sorgu senaryolarının tümü **dvdrental** örnek veri tabanı üzerinden gerçekleştirilmiştir.

`1` Film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
```sql
SELECT rating 
FROM film 
GROUP BY rating;
```
`2` Film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
```sql
SELECT replacement_cost, COUNT(*) 
FROM film 
GROUP BY replacement_cost HAVING COUNT(*) > 50;
```
`3` Customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir?
```sql
SELECT store_id, COUNT(customer_id) 
FROM customer 
GROUP BY store_id;
```
`4` City tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.
```sql
SELECT country_id, COUNT(city) 
FROM city 
GROUP BY country_id 
ORDER BY COUNT(city) DESC 
LIMIT 1;
```