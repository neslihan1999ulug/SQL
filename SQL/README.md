# ÖDEV-1 CEVAPLARI

1. film tablosunda bulunan title ve description sütunlarındaki verileri sıralayınız.
   `SELECT title, description FROM film;`

2. film tablosunda bulunan tüm sütunlardaki verileri film uzunluğu (length) 60 dan büyük VE 75 ten küçük olma koşullarıyla sıralayınız.
   `SELECT * FROM film WHERE length > 60 AND length < 75;`

3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99 VE replacement_cost 12.99 VEYA 28.99 olma koşullarıyla sıralayınız.
   `SELECT * FROM film WHERE rental_rate = 0.99 AND (replacement_cost = 12.99 OR replacement_cost = 28.99);`

4. customer tablosunda bulunan first_name sütunundaki değeri 'Mary' olan müşterinin last_name sütunundaki değeri nedir?
   `SELECT last_name FROM customer WHERE first_name ='Mary';`

5. film tablosundaki uzunluğu(length) 50 ten büyük OLMAYIP aynı zamanda rental_rate değeri 2.99 veya 4.99 OLMAYAN verileri sıralayınız. 
5.1:
   `SELECT * FROM film WHERE length <= 50 AND rental_rate NOT IN (2.99,4.99);`
5.2:
   `SELECT * FROM film WHERE length <= 50 AND rental_rate NOT BETWEEN 2.99 AND 4.99;`
   
---

# ÖDEV-2 CEVAPLARI

1. film tablosunda bulunan tüm sütunlardaki verileri replacement cost değeri 12.99 dan büyük eşit ve 16.99 küçük olma koşuluyla sıralayınız ( BETWEEN - AND yapısını kullanınız.)
   `SELECT * FROM film WHERE replacement_cost BETWEEN 12.99 AND 16.99;`

2. actor tablosunda bulunan first_name ve last_name sütunlardaki verileri first_name 'Penelope' veya 'Nick' veya 'Ed' değerleri olması koşuluyla sıralayınız. ( IN operatörünü kullanınız.)
   `SELECT first_name, last_name FROM actor WHERE first_name IN ('Penelope','Nick','Ed');`

3. film tablosunda bulunan tüm sütunlardaki verileri rental_rate 0.99, 2.99, 4.99 VE replacement_cost 12.99, 15.99, 28.99 olma koşullarıyla sıralayınız. ( IN operatörünü kullanınız.)
   `SELECT * FROM film WHERE rental_rate IN (0.99,2.99,4.99) AND replacement_cost IN (12.99,15.99,28.99);`
   
---

# ÖDEV-3 CEVAPLARI 

1. country tablosunda bulunan country sütunundaki ülke isimlerinden 'A' karakteri ile başlayıp 'a' karakteri ile sonlananları sıralayınız.
   `SELECT * FROM country WHERE country LIKE 'A%a';`

2. country tablosunda bulunan country sütunundaki ülke isimlerinden en az 6 karakterden oluşan ve sonu 'n' karakteri ile sonlananları sıralayınız.
   `SELECT * FROM country WHERE country ILIKE '______%n';`

3. film tablosunda bulunan title sütunundaki film isimlerinden en az 4 adet büyük ya da küçük harf farketmesizin 'T' karakteri içeren film isimlerini sıralayınız.
   `SELECT * FROM film WHERE title ILIKE '%t%t%t%t%';`

4. film tablosunda bulunan tüm sütunlardaki verilerden title 'C' karakteri ile başlayan ve uzunluğu (length) 90 dan büyük olan ve rental_rate 2.99 olan verileri sıralayınız.
   `SELECT * FROM film WHERE title ILIKE 'C%' AND length > 90 AND rental_rate = 2.99;`
   
---

# ÖDEV-4 CEVAPLARI
 
1. film tablosunda bulunan replacement_cost sütununda bulunan birbirinden farklı değerleri sıralayınız.
   `SELECT DISTINCT replacement_cost FROM film;`

2. film tablosunda bulunan replacement_cost sütununda birbirinden farklı kaç tane veri vardır?
   `SELECT COUNT (DISTINCT replacement_cost) FROM film;`

3. film tablosunda bulunan film isimlerinde (title) kaç tanesini T karakteri ile başlar ve aynı zamanda rating 'G' ye eşittir?
   `SELECT * FROM film WHERE title ILIKE 'T%' AND rating = 'G';`
   
4. country tablosunda bulunan ülke isimlerinden (country) kaç tanesi 5 karakterden oluşmaktadır?
   `SELECT * FROM country WHERE country ILIKE '_____';`

5. city tablosundaki şehir isimlerinin kaç tanesi 'R' veya r karakteri ile biter?
    `SELECT COUNT (city) FROM city WHERE city ILIKE '%r';`

---

# ÖDEV-5 CEVAPLARI

1. film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en uzun (length) 5 filmi sıralayınız.
   `SELECT * FROM film WHERE title LIKE '%n'ORDER BY length DESC
LIMIT 5;`
2. film tablosunda bulunan ve film ismi (title) 'n' karakteri ile biten en kısa (length) ikinci(6,7,8,9,10) 5 filmi(6,7,8,9,10) sıralayınız.
   `SELECT * FROM film WHERE title LIKE '%n' ORDER BY length ASC OFFSET 5 LIMIT 5;`

3.customer tablosunda bulunan last_name sütununa göre azalan yapılan sıralamada store_id 1 olmak koşuluyla ilk 4 veriyi sıralayınız.
   `SELECT * FROM customer WHERE store_id = 1 ORDER BY last_name DESC LIMIT 5;`

---

# ÖDEV-6 CEVAPLARI

1. film tablosunda bulunan rental_rate sütunundaki değerlerin ortalaması nedir?
   `SELECT AVG (rental_rate) FROM film;`

2. film tablosunda bulunan filmlerden kaç tanesi 'C' karakteri ile başlar?
   `SELECT COUNT(*) FROM film WHERE title LIKE 'C%';`

3. film tablosunda bulunan filmlerden rental_rate değeri 0.99 a eşit olan en uzun (length) film kaç dakikadır?
   `SELECT MAX (length) FROM film WHERE rental_rate = 0.99;`
   
4. film tablosunda bulunan filmlerin uzunluğu 150 dakikadan büyük olanlarına ait kaç farklı replacement_cost değeri vardır?
   `SELECT COUNT (DISTINCT replacement_cost) FROM film WHERE length > 150;`

 ---

  # ÖDEV-7 CEVAPLARI 

1. film tablosunda bulunan filmleri rating değerlerine göre gruplayınız.
   `SELECT rating FROM film GROUP BY rating;`
2. film tablosunda bulunan filmleri replacement_cost sütununa göre grupladığımızda film sayısı 50 den fazla olan replacement_cost değerini ve karşılık gelen film sayısını sıralayınız.
   `SELECT repLacement_cost, COUNT (*) FROM film GROUP BY replacement_cost HAVING COUNT (*) > 50 ;`
3. customer tablosunda bulunan store_id değerlerine karşılık gelen müşteri sayılarını nelerdir? 
   `SELECT store_id, COUNT (*) FROM customer GROUP BY store_id;`
4. city tablosunda bulunan şehir verilerini country_id sütununa göre gruplandırdıktan sonra en fazla şehir sayısı barındıran country_id bilgisini ve şehir sayısını paylaşınız.
   `SELECT country_id ,COUNT(*) FROM city GROUP BY country_id ORDER BY COUNT(country_id)DESC ;`

---

 # ÖDEV-8 CEVAPLARI 

1. test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
   `CREATE TABLE employee (	id SERIAL,	name VARCHAR(50),	birthday DATE, email VARCHAR(100));`
2. Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
   `
insert into employee (Name, birthday, email) values ('Trudi Dossett', '1998-03-03', 'tdossett0@live.com');
insert into employee (Name, birthday, email) values ('Tades Manueli', '1999-11-07', 'tmanueli1@sakura.ne.jp');
insert into employee (Name, birthday, email) values ('Anselm Horwell', '2008-04-04', 'ahorwell2@skyrock.com');
insert into employee (Name, birthday, email) values ('Ned Garnsey', '2005-06-16', 'ngarnsey3@g.co');
insert into employee (Name, birthday, email) values ('Nanni Fahrenbach', '1997-12-30', 'nfahrenbach4@ebay.com');
insert into employee (Name, birthday, email) values ('Carlita Dimmack', '1999-01-19', 'cdimmack5@ihg.com');
insert into employee (Name, birthday, email) values ('Bertram Gippes', '1998-08-15', 'bgippes6@seattletimes.com');
insert into employee (Name, birthday, email) values ('Tess Czapla', '1994-11-29', 'tczapla7@sourceforge.net');
insert into employee (Name, birthday, email) values ('Aylmar Tyers', '2006-03-24', 'atyers8@yolasite.com');
insert into employee (Name, birthday, email) values ('Kristopher GiacobbiniJacob', '1996-10-16', 'kgiacobbinijacob9@ebay.co.uk');
insert into employee (Name, birthday, email) values ('Darby Bergen', '2004-05-20', 'dbergena@jimdo.com');
insert into employee (Name, birthday, email) values ('Carroll Kibard', '2003-03-07', 'ckibardb@163.com');
insert into employee (Name, birthday, email) values ('Franciskus Tague', '2003-06-21', 'ftaguec@feedburner.com');
insert into employee (Name, birthday, email) values ('Rufe Van Ross', '2003-09-14', 'rvand@hexun.com');
insert into employee (Name, birthday, email) values ('Hunt Duckitt', '1994-10-20', 'hduckitte@economist.com');
insert into employee (Name, birthday, email) values ('Clarance Dilke', '1995-12-07', 'cdilkef@google.com.br');
insert into employee (Name, birthday, email) values ('Nikoletta Ackerley', '2001-11-13', 'nackerleyg@wikimedia.org');
insert into employee (Name, birthday, email) values ('Cherise Jimenez', '1996-04-13', 'cjimenezh@go.com');
insert into employee (Name, birthday, email) values ('Allard Nutbean', '1991-10-24', 'anutbeani@sciencedaily.com');
insert into employee (Name, birthday, email) values ('Bartlett Glavis', '2008-11-26', 'bglavisj@t.co');
insert into employee (Name, birthday, email) values ('Rosemarie Longfut', '1991-03-21', 'rlongfutk@nps.gov');
insert into employee (Name, birthday, email) values ('Francesca Crowcroft', '2008-08-19', 'fcrowcroftl@arstechnica.com');
insert into employee (Name, birthday, email) values ('Joela Warden', '2006-04-03', 'jwardenm@craigslist.org');
insert into employee (Name, birthday, email) values ('Shayne Clowes', '1991-08-01', 'sclowesn@indiatimes.com');
insert into employee (Name, birthday, email) values ('Mitchel Taffs', '2007-06-03', 'mtaffso@icq.com');
insert into employee (Name, birthday, email) values ('Peri Heck', '1994-05-19', 'pheckp@sakura.ne.jp');
insert into employee (Name, birthday, email) values ('Denver Brabant', '1995-10-17', 'dbrabantq@ibm.com');
insert into employee (Name, birthday, email) values ('Hilary Ortelt', '1995-09-01', 'horteltr@ocn.ne.jp');
insert into employee (Name, birthday, email) values ('Kleon Diehn', '2006-03-02', 'kdiehns@sbwire.com');
insert into employee (Name, birthday, email) values ('Teresa Flea', '1992-04-08', 'tfleat@stumbleupon.com');
insert into employee (Name, birthday, email) values ('Phillipp Gavrielly', '2002-07-05', 'pgavriellyu@privacy.gov.au');
insert into employee (Name, birthday, email) values ('Maximilien Sinkinson', '2004-11-26', 'msinkinsonv@usda.gov');
insert into employee (Name, birthday, email) values ('Dayle Iacobassi', '1999-08-05', 'diacobassiw@yandex.ru');
insert into employee (Name, birthday, email) values ('Orv Hamsley', '2004-01-26', 'ohamsleyx@java.com');
insert into employee (Name, birthday, email) values ('Dyann Ashborn', '1994-04-15', 'dashborny@elpais.com');
insert into employee (Name, birthday, email) values ('Wye Kassman', '1995-10-08', 'wkassmanz@histats.com');
insert into employee (Name, birthday, email) values ('Geordie Dikles', '2002-06-08', 'gdikles10@ox.ac.uk');
insert into employee (Name, birthday, email) values ('Lacie Padly', '1991-01-03', 'lpadly11@wired.com');
insert into employee (Name, birthday, email) values ('Irvin Cornelleau', '1992-06-24', 'icornelleau12@umn.edu');
insert into employee (Name, birthday, email) values ('Lorilyn Lotte', '1996-01-30', 'llotte13@cbc.ca');
insert into employee (Name, birthday, email) values ('Neale Brickhill', '2003-01-14', 'nbrickhill14@ycombinator.com');
insert into employee (Name, birthday, email) values ('Forbes Haseley', '2006-02-05', 'fhaseley15@upenn.edu');
insert into employee (Name, birthday, email) values ('Neall Penritt', '2007-01-11', 'npenritt16@ameblo.jp');
insert into employee (Name, birthday, email) values ('Daryl O''Hanlon', '2004-12-16', 'dohanlon17@youtube.com');
insert into employee (Name, birthday, email) values ('Edgar Moralee', '2005-12-16', 'emoralee18@goo.gl');
insert into employee (Name, birthday, email) values ('Dinnie Kennedy', '1997-07-11', 'dkennedy19@bbb.org');
insert into employee (Name, birthday, email) values ('Nikita Morgen', '2001-02-21', 'nmorgen1a@istockphoto.com');
insert into employee (Name, birthday, email) values ('Therine Antonietti', '2007-10-16', 'tantonietti1b@fotki.com');
insert into employee (Name, birthday, email) values ('Roxanne Bartolomeo', '2006-12-11', 'rbartolomeo1c@usatoday.com');
insert into employee (Name, birthday, email) values ('Orelee Medina', '2004-12-17', 'omedina1d@wikispaces.com');
`
3. Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım. 
   `UPDATE employee
SET 
	name = 'Tahsin Güral',
	birthday = '1998-06-02',
	email = 'tahsingural98@tahsin.com'
WHERE id = 18;`

`UPDATE employee
SET 
	name = 'update edildi',
	birthday = '1998-06-02',
	email = 'update@update.com'
WHERE name LIKE 'T%';`

`UPDATE employee
SET 
	birthday = '2011-06-02',
	email = 'update@update.com'
WHERE birthday = '2008-04-04';`

`UPDATE employee
SET 
	email = 'mail@allard.com'
WHERE birthday = '1991-10-24';`

`UPDATE employee
SET 
	email = 'Dinnieupdate@update.com'
WHERE name = 'Dinnie Kennedy';`

4. Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
`DELETE FROM employee
WHERE name LIKE 'R%';`
`DELETE FROM employee
WHERE id = 10 ;`
`DELETE FROM employee
WHERE name = 'Tahsin';`
`DELETE FROM employee
WHERE birthday = '1997-12-30';`
`DELETE FROM employee
WHERE email LIKE 'u%';`

---

  # ÖDEV-9 CEVAPLARI
  
1. city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
 `SELECT city.city, country.country FROM city
INNER JOIN country ON city.country_id = country.country_id;`
2. customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
`SELECT payment.payment_id, customer.first_name, customer.last_name FROM customer
INNER JOIN payment ON payment.customer_id = customer.customer_id;`
3.customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz INNER JOIN sorgusunu yazınız.
`SELECT rental.rental_id, customer.firsT_name, customer.last_name
FROM customer
INNER JOIN rental ON rental.customer_id = customer.customer_id;`

---

  # ÖDEV-10 CEVAPLARI
  
1. city tablosu ile country tablosunda bulunan şehir (city) ve ülke (country) isimlerini birlikte görebileceğimiz LEFT JOIN sorgusunu yazınız.
 `SELECT city.city, country.country FROM city
LEFT JOIN country ON city.country_id = country.country_id;`
2. customer tablosu ile payment tablosunda bulunan payment_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz RIGHT JOIN sorgusunu yazınız.
`SELECT payment.payment_id, customer.first_name, customer.last_name
FROM payment
LEFT JOIN customer ON customer.customer_id = payment.customer_id;`
3. customer tablosu ile rental tablosunda bulunan rental_id ile customer tablosundaki first_name ve last_name isimlerini birlikte görebileceğimiz FULL JOIN sorgusunu yazınız.
`SELECT rental.rental_id, customer.firsT_name, customer.last_name
FROM customer
FULL JOIN rental ON rental.customer_id = customer.customer_id;`

---

  # ÖDEV-11 CEVAPLARI

1. actor ve customer tablolarında bulunan first_name sütunları için tüm verileri sıralayalım.
`SELECT first_name FROM actor UNION SELECT first_name FROM customer;`
2. actor ve customer tablolarında bulunan first_name sütunları için kesişen verileri sıralayalım.
`SELECT first_name FROM actor INTERSECT SELECT first_name FROM customer;`
3. actor ve customer tablolarında bulunan first_name sütunları için ilk tabloda bulunan ancak ikinci tabloda bulunmayan verileri sıralayalım.
`SELECT first_name FROM actor EXCEPT SELECT first_name FROM customer;`
4. İlk 3 sorguyu tekrar eden veriler için de yapalım.
`SELECT first_name FROM actor UNION ALL SELECT first_name FROM customer;`
`SELECT first_name FROM actor INTERSECT ALL SELECT first_name FROM customer;`
`SELECT first_name FROM actor EXCEPT ALL SELECT first_name FROM customer;`

---

  # ÖDEV-12 CEVAPLARI

1. film tablosunda film uzunluğu length sütununda gösterilmektedir. Uzunluğu ortalama film uzunluğundan fazla kaç tane film vardır?
`SELECT COUNT(*) FROM film
WHERE length > ANY
( SELECT AVG(length) FROM film);`
2.film tablosunda en yüksek rental_rate değerine sahip kaç tane film vardır?
`SELECT COUNT (film.rental_rate) FROM film
GROUP BY rental_rate
ORDER BY rental_rate DESC
LIMIT 1;`
3. film tablosunda en düşük rental_rate ve en düşün replacement_cost değerlerine sahip filmleri sıralayınız.
`SELECT  film.title, film.rental_rate, film.replacement_cost FROM film
 WHERE rental_rate = (SELECT MIN(rental_rate)FROM film) 
 AND replacement_cost = (SELECT MIN(replacement_cost)FROM film);`
4. payment tablosunda en fazla sayıda alışveriş yapan müşterileri(customer) sıralayınız.
`SELECT SUM(amount), customer.first_name, customer.last_name FROM customer
JOIN payment ON customer.customer_id = payment.customer_id
GROUP BY payment.customer_id, customer.first_name, customer.last_name
ORDER BY SUM(amount) DESC
LIMIT 1;`




