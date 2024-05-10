# Swiggy_Database_analysis

**`—NOW WE WILL USE Orders.CSV TABLE—`**

**Q.-How many distinct on time delivery?**

---

SELECT count(DISTINCT order_id) as distinct_on_time_dilevery  from orders


where on_time=1;

---
---

**Q.-How many distinct resturant we have order from?**

---

select count(DISTINCT restaurant_name) AS distinct_resturant FROM orders

---
---

**Q.-Which are our fav resturant?**

---

select restaurant_name,COUNT(restaurant_name) AS No_Of_Times_Order from orders

group by restaurant_name

order by No_Of_Times_Order DESC;

---
---

**Q.- What is the latest order we made?**

---

SELECT max(order_time) AS Latest_Order FROM orders;

---
---

**`—NOW WE WILL USE ITEMS.CSV TABLE—`**



**Q.-What is the count of distinct items that were ordered ?**

---

select count(distinct name) from items;

---
---

**Q.-Overall how many items are veg ?**

---

SELECT is_veg,COUNT(is_veg) AS Veg_item_count FROM items

GROUP BY is_veg;

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

**Q.-what are the items contain the word chicken?**

---

select * from items

where name like'%chicken%';

---
---

**Q.-What was the average no. of items per order?**

---

select COUNT(name)/COUNT(DISTINCT order_id) AS Avg_Item_Per_Order FROM items; 
//Customer is ordering atleast 2 items per order

---
---

**Q.-How many times each item is order, we can know which item is in highest sale?**

---

select name, count (*) AS No_Of_Times_Ordered from items

---

group by name

---

order by No_Of_Times_Ordered DESC;

---
---
---
