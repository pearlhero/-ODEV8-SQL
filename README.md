# -ODEV8-SQL
tablolarla çalışmak
Sorgu 1- test veritabanınızda employee isimli sütun bilgileri id(INTEGER), name VARCHAR(50), birthday DATE, email VARCHAR(100) olan bir tablo oluşturalım.
Çözüm 1- CREATE TABLE employee (
    id INTEGER,
	name VARCHAR(50),
	birthday DATE,
	email VARCHAR(100)
);
<img width="846" alt="Ekran Resmi 2023-03-06 19 28 21" src="https://user-images.githubusercontent.com/116847744/223171172-df6d69d7-c6af-4f29-8e83-4632269d3a96.png">

Sorgu 2- Oluşturduğumuz employee tablosuna 'Mockaroo' servisini kullanarak 50 adet veri ekleyelim.
Çözüm 2- <img width="728" alt="Ekran Resmi 2023-03-06 20 05 53" src="https://user-images.githubusercontent.com/116847744/223180501-fb76e463-5606-4b26-9595-3d5d38caffea.png">

Sorgu 3- Sütunların her birine göre diğer sütunları güncelleyecek 5 adet UPDATE işlemi yapalım.
Çözüm 3- UPDATE employee
SET name = 'Inci'
WHERE id between 1 AND 10
RETURNING *; 

UPDATE employee
SET birthday = '1993-08-13'
WHERE id BETWEEN 11 AND 20
RETURNING *;

UPDATE employee
SET email = 'inci@inci'
WHERE id BETWEEN 21 AND 30
RETURNING *;

UPDATE employee
SET name = 'HERO'
WHERE id BETWEEN 31 AND 40
RETURNING *;

UPDATE employee
SET email = 'inci@hero'
WHERE id BETWEEN 41 AND 50
RETURNING *;

Sorgu 4- Sütunların her birine göre ilgili satırı silecek 5 adet DELETE işlemi yapalım.
Çözüm 4- DELETE FROM employee
WHERE id <= 10
RETURNING *;

DELETE FROM employee
WHERE birthday = '1993-08-13'
RETURNING *;

DELETE FROM employee
WHERE email = 'inci@inci'
RETURNING *;

DELETE FROM employee
WHERE name = 'HERO'
RETURNING *;

DELETE FROM employee
WHERE email = 'inci@hero'
RETURNING *;
