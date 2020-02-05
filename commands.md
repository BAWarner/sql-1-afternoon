## Step 1 - Table: person

1.  CREATE TABLE person(
        id SERIAL PRIMARY KEY,
        name TEXT,
        age INTEGER,
        height INTEGER,
        city TEXT,
        favorite_color TEXT
    );

2.  INSERT INTO person(name, age, height, city, favorite_color)
    VALUES ('Wayne Campell', 25, 176, 'Aurora', 'blue'),
        ('Garth Algar', 27, 175, 'Aurora', 'green'),
        ('Bruce Wayne', 40, 187, 'Gotham', 'black'),
        ('John Wayne', 72, 193, 'Winterset', 'red'),
        ('Wayne Gretzky', 59, 183, 'Brantford', 'red');

3.  SELECT * from person
    ORDER BY height DESC;

4.  SELECT * from person
    ORDER BY height ASC;

5.  SELECT * FROM person
    ORDER BY age DESC;

6.  SELECT * FROM person
    WHERE age > 20;

7.  SELECT * FROM person
    WHERE age = 18;

8.  SELECT * FROM person
    WHERE age < 20 OR age > 30;

9.  SELECT * FROM person
    WHERE age != 27;

10. SELECT * FROM person
    WHERE favorite_color != 'red';

11. SELECT * FROM person
    WHERE favorite_color != 'red'
    AND favorite_color != 'blue';

12. SELECT * FROM person
    WHERE favorite_color = 'orange'
    OR favorite_color = 'green';

13. SELECT * FROM person
    WHERE favorite_color IN ('green', 'blue', 'orange');

14. SELECT * FROM person
    WHERE favorite_color IN ('yellow', 'purple');


## Step 2 - Table: Orders

1.  CREATE TABLE orders(
        order_id SERIAL PRIMARY KEY,
        person_id INTEGER,
        product_name TEXT,
        product_price FLOAT,
        quantity INTEGER
    );

2.  INSERT INTO orders(person_id, product_name, product_price, quantity)
    VALUES		      (4, 'Chips and Salsa', 3.99, 1),
					  (4, 'Soda', 2.14, 2),
                      (1, 'Club Sandwich', 5.43, 4),
                      (17, 'Pizza', 7.88, 2),
                      (82, 'Milk Shake', 4.67, 3);

3.  SELECT * FROM orders;

4.  SELECT SUM(quantity) FROM orders;

5.  SELECT SUM(product_price * quantity) FROM orders;

6.  SELECT SUM(product_price * quantity) FROM orders
    WHERE person_id = 4;


## Step 3 - Table: artist

1.  INSERT INTO artist(name)
    VALUES			  ('M83'),
					  ('The Kooks'),
                      ('Bleachers');

2.  SELECT * FROM artist
    ORDER BY name DESC
    LIMIT 10;

3.  SELECT * FROM artist
    LIMIT 5;

4.  SELECT * FROM artist
    WHERE name ILIKE 'black%';

5.  SELECT * FROM artist
    WHERE name ILIKE '%black%';


## Step 4 - Table: employee

1.  SELECT first_name, last_name FROM employee
    WHERE city = 'Calgary';

2.  SELECT MIN(birth_date) FROM employee;

3.  SELECT MAX(birth_date) FROM employee;

4.  SELECT * from employee
    WHERE reports_to = 2;

5.  SELECT COUNT(*) FROM employee
    WHERE city = 'Lethbridge';


## Step 5 - Table: invoice

1.  SELECT COUNT(*) FROM invoice
    WHERE billing_country = 'USA';

2.  SELECT MAX(total) FROM invoice;

3.  SELECT MIN(total) FROM invoice;

4.  SELECT * FROM invoice
    WHERE total > 5;

5.  SELECT COUNT(*) FROM invoice
    WHERE total < 5;

6.  SELECT COUNT(*) FROM invoice
    WHERE billing_state IN ('CA', 'TX', 'AZ');

7.  SELECT AVG(total) FROM invoice;

8.  SELECT SUM(total) FROM invoice;

