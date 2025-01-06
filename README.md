Submitted by: Sonjay Cimanes
              Mary Joy Monter
Subject: ITBAN 2

1.1.SELECT name, description FROM products;
![Database Screenshot](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/b04d2612ebe76e208b54deaf49941b92cec0ab86/1.JPG)

1.2.SELECT name, description, JSON_EXTRACT(attributes,'$.color') AS color, JSON_EXTRACT(attributes,'$.size') AS size, JSON_EXTRACT(attributes,'$.prize') AS prize FROM products;
![Database Screenshot (401)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/b04d2612ebe76e208b54deaf49941b92cec0ab86/1.2.JPG)

2.1.SELECT o.order_date, o.customer_id, p.name AS product_name, od.quantity, od.price FROM orders o JOIN order_details od ON o.order_id = od.order_id JOIN products p ON od.product_id = p.product_id;
![Database Screenshot (402)](https://github.com/Ryljoy2023/MySQL-ACTIVITY1/blob/b04d2612ebe76e208b54deaf49941b92cec0ab86/2.JPG)
