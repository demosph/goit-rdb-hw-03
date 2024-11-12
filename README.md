# Завантаження даних та основи SQL. DQL команди

### Завдання 1

Напишіть SQL команду, за допомогою якої можна:

- вибрати всі стовпчики (за допомогою wildcard \*) з таблиці `products`;
- вибрати тільки стовпчики _name_, _phone_ з таблиці `shippers`;

та перевірте правильність її виконання в MySQL Workbench.

```sql
SELECT * FROM mydb.products;
```

```sql
SELECT name, phone FROM mydb.shippers;
```

### Завдання 2

Напишіть SQL команду, за допомогою якої можна знайти середнє, максимальне та мінімальне значення стовпчика _price_ таблички `products`, та перевірте правильність її виконання в MySQL Workbench.

```sql
SELECT
    AVG(price) as avg_price,
    MAX(price) as max_price,
    MIN(price) as min_price
FROM mydb.products;
```

### Завдання 3

Напишіть SQL команду, за допомогою якої можна обрати унікальні значення колонок _category_id_ та _price_ таблиці `products`.

Оберіть порядок виведення на екран за спаданням значення _price_ та виберіть тільки 10 рядків. Перевірте правильність виконання команди в MySQL Workbench.

```sql
SELECT DISTINCT
    category_id, price
FROM
    mydb.products
ORDER BY price DESC
LIMIT 10;
```

### Завдання 4

Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків), які знаходиться в цінових межах від 20 до 100, та перевірте правильність її виконання в MySQL Workbench.

```sql
SELECT
    COUNT(*) AS product_count
FROM
    mydb.products
WHERE
    price BETWEEN 20 AND 100;
```

### Завдання 5

Напишіть SQL команду, за допомогою якої можна знайти кількість продуктів (рядків) та середню ціну (_price_) у кожного постачальника (_supplier_id_), та перевірте правильність її виконання в MySQL Workbench.

```sql
SELECT
    supplier_id,
    COUNT(*) AS order_count,
    AVG(price) AS avg_price
FROM
    mydb.products
GROUP BY supplier_id;
```
