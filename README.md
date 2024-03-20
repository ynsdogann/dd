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


Ödev7
--film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
SELECT rating FROM film GROUP BY rating
--film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan
--replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.

select replacement_cost,count(*) from film  GROUP BY replacement_cost GROUP BY replacement_cost

-- customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 
select store_id,first_name,last_name,count(*) from customer group by first_name,last_name,store_id ORDER BY store_id

--4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en 
--fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.
select  city,country_id,COUNT (DISTINCT(city))from city group by country_id,city order by country_id

