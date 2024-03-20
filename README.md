 Ödev5
 select  title,length from film where title not Ilike ('a%') order by length desc
--film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
SELECT title,length from film where title like ('%n') limit 5
--film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
SELECT title,length from film where title Like('%n') order by length asc offset 2 limit 5
--customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
SELECT store_id,first_name,last_name FROM customer where store_id=1 ORDER BY last_name limit 4



Ödev6
--film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?
SELECT  AVG(rental_rate) from film
--film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?
SELECT COUNT(title) from film where title ilike('c%');
--film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
SELECT title,rental_rate,length FROM film where rental_rate=0.99 ORDER BY length desc limit 3
--film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?
SELECT  count(replacement_cost) from film where length>150
