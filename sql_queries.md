# SQL-запросы 

-- 1. Все товары, цена которых больше 10 000 рублей
```sql
SELECT *
FROM products
WHERE price > 10000;
```

-- 2. Список всех товаров вместе с названием категории
```sql
SELECT 
    p.id,
    p.name AS product_name,
    p.price,
    c.name AS category_name
FROM products p
LEFT JOIN categories c ON p.category_id = c.id;
```

-- 3. Количество товаров в каждой категории
```sql
SELECT 
    c.name AS category_name,
    COUNT(p.id) AS products_count
FROM categories c
LEFT JOIN products p ON c.id = p.category_id
GROUP BY c.id, c.name
ORDER BY products_count DESC;
```

-- 4. Товары, отсортированные по цене от дешёвых к дорогим — только первые три
```sql
SELECT *
FROM products
ORDER BY price ASC
LIMIT 3;
```
