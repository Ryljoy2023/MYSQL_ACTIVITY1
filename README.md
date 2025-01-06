Submitted by:
  Sonjay Cimanes
  Mary Joy Monter
  
Subject: 
  ITBAN 2
  

1.1.SELECT name, description FROM products;
![Database Screenshot](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/b04d2612ebe76e208b54deaf49941b92cec0ab86/1.JPG)

1.2.SELECT name, description, JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size, JSON_EXTRACT(attributes,'$.prize') AS prize FROM products;
![Database Screenshot (401)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/b04d2612ebe76e208b54deaf49941b92cec0ab86/1.2.JPG)

2.1.SELECT o.order_date, o.customer_id, p.name AS product_name, od.quantity, od.price FROM orders o JOIN order_details od ON o.order_id = od.order_id JOIN products p ON od.product_id = p.product_id;
![Database Screenshot (402)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/b04d2612ebe76e208b54deaf49941b92cec0ab86/2.JPG)

2.2.SELECT o.order_id, SUM(od.quantity * od.price) AS total_cost FROM orders o JOIN order_details od ON o.order_id = od.order_id GROUP BY o.order_id;
![Database Screenshott (403)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/2.1.JPG)

3.1.SELECT name,JSON_EXTRACT(attributes,'$.price') FROM products WHERE JSON_EXTRACT(attributes,'$.price') > 50;
![Database Screenshot (404)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/3.1%20CORRECT.JPG)

3.2.SELECT name, JSON_EXTRACT(attributes,'$.price') AS price FROM products JSON_EXTRACT(attributes,'$.color') = 'Hotpink' AND JSON_EXTRACT(attributes,'$.brand') = 'Holt Group';
![Database Screenshot (405)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/3.2.JPG)

4.1.SELECT p.name, SUM(od.quantity * od.price) AS total_revenue FROM products p JOIN order_details od ON p.product_id = od.product_id GROUP BY p.name;
![Database Screenshot (406)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/4.JPG)

4.2.SELECT p.name, SUM(od.quantity) AS total_quantity_ordered FROM products p JOIN order_details od ON p.product_id = od.product_id GROUP BY p.name;
![Database Screenshot (407)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/4.1.JPG)

5.1.SELECT p.name, SUM(od.quantity) AS total_quantity_sold FROM products p JOIN order_details od ON p.product_id = od.product_id GROUP BY p.name ORDER BY total_quantity_sold DESC LIMIT 5;
![Database Screenshot(408)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/5.JPG)

5.2.SELECT AVG(CAST(JSON_EXTRACT(attributes,'$.prize') AS DECIMAL)) AS avg_price FROM products WHERE JSON_EXTRACT(attributes,'$.brand') = 'Meyer Inc';
![Database Screenshot (409)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/5.1.JPG)

6.1.SELECT JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size FROM products WHERE product_id = 1;
![Database Screenshot(410)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/6.JPG)

6.2.SELECT JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size, JSON_EXTRACT(attributes,'$.prize') AS prize, JSON_EXTRACT(attributes,'$.brand') AS brand FROM products;
![Databas Screenshot (411)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/6.1.JPG)

7.1.SELECT o.order_id, o.order_date, o.customer_id, p.name AS product_name, od.quantity FROM orders o JOIN order_details od ON o.order_id = od.order_id JOIN products p ON od.product_id = p.product_id;
![Databas Screenshot (412)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/7.JPG)

7.2.SELECT o.customer_id, SUM(od.quantity * od.price) AS total_revenue FROM orders o JOIN order_details od ON o.order_id = od.order_id GROUP BY o.customer_id;
![Databas Screenshot (413)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/7.1.JPG)

8.1.UPDATE products SET attributes = JSON_SET(attributes, '$.price', '61') WHERE product_id = 1;
![Databas Screenshot (414)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/8.JPG)
![Databas Screenshot (415)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/8%20continue.JPG)

8.2.UPDATE products SET attributes = JSON_SET(attributes, '$.bagong_COlumn ', 'mao_NANI');
![Databas Screenshot (416)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/8.2.JPG)

9.1.SELECT * FROM products WHERE JSON_CONTAINS_PATH(attributes, 'one', '$.color') = 1;
![Databas Screenshot (417)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/9.JPG)

9.2. SELECT JSON_EXTRACT(attributes, '$.color[0]') AS first_feature FROM products;
![Databas Screenshot (418)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/3dab5f2a7453cdaaaaea85c45923ed908d0acc27/9.1.JPG)






