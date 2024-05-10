# Swiggy_Database_analysis

**`—NOW WE WILL USE Orders.CSV TABLE—`**

**Q.-How many distinct on time delivery?**

---

SELECT count(DISTINCT order_id) as distinct_on_time_dilevery  from orders


where on_time=1;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/fc13ff36-9687-4ed2-889e-39d4c71e1f39)    

---
---

**Q.-How many distinct resturant we have order from?**

---

select count(DISTINCT restaurant_name) AS distinct_resturant FROM orders

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/36478f14-ee5a-4ffd-86e4-5cda81e16882)

---
---

**Q.-Which are our fav resturant?**

---

select restaurant_name,COUNT(restaurant_name) AS No_Of_Times_Order from orders

group by restaurant_name

order by No_Of_Times_Order DESC;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/125a83ac-4405-4bed-8f5f-4a5478ecaa02)

---
---

**Q.- What is the latest order we made?**

---

SELECT max(order_time) AS Latest_Order FROM orders;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/25a04132-ecb8-4518-bcb7-fd4a1c6942d8)

---
---

**`—NOW WE WILL USE ITEMS.CSV TABLE—`**



**Q.-What is the count of distinct items that were ordered ?**

---

select count(distinct name) from items;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/dbc01504-23dd-4f15-8ee9-f29f8af43ab2)

---
---

**Q.-Overall how many items are veg ?**

---

SELECT is_veg,COUNT(is_veg) AS Veg_item_count FROM items

GROUP BY is_veg;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/c493d33f-2a03-43a8-8ab0-a4e0e628ec29)

---
---

**Q.-what is other then veg or non veg?**

---

select * FROM items

where is_veg=2;

---
---

**Q.-Overall what is the count of distinct orders were placed?**

---

select count(Distinct order_id) from items;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/a7efcaab-bd8b-4b52-829f-8295a9693131)

---
---

**Q.-what are the items contain the word chicken?**

---

select * from items

where name like'%chicken%';

---
---

---
---

**Q.-What was the average no. of items per order?**

---

select COUNT(name)/COUNT(DISTINCT order_id) AS Avg_Item_Per_Order FROM items; 
//Customer is ordering atleast 2 items per order

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/5cd5afba-5d69-4fa4-adee-8bcbde62960a)

---
---

**Q.-How many times each item is order, we can know which item is in highest sale?**

---

select name, count (*) AS No_Of_Times_Ordered from items

group by name

order by No_Of_Times_Ordered DESC;

---
---
![image](https://github.com/ds-ecode/Swiggy_Database_analysis/assets/158248079/8375fe8d-6f31-4488-a707-d4435a237614)

---
---
---
