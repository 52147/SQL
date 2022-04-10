# SQL

## Join
1. (inner) join
2. left (outer) join
3. right (outer) join
4. cross join : returns the Cartesian product of the joined tables

![image](https://user-images.githubusercontent.com/79159894/162604926-3d1f6e35-1b98-4afb-a385-0a77deca0cd9.png)


## DENSE_RANK
-  It is used to get the rank of a row in a group of rows. 
-  It always results in the consecutive ranking of the rows.

## COALESCE
- The COALESCE() function returns the first non-null value in a list.
- SELECT COALESCE(NULL, 1, 2, 'W3Schools.com');

- output:
- 1

##  <>/ != 

- != functions the same as the <> (Not Equal To) comparison operator.

## FETCH
FETCH is an SQL command used along with ORDER BY clause with an OFFSET(Starting point) to retrieve or fetch selected rows sequentially using a cursor that moves and processes each row one at a time till the number of rows mentioned in the query are displayed.

FETCH NEXT 1 ROWS ONLY
```
SELECT *

FROM table_name

ORDER BY col_name

OFFSET starting point

FETCH NEXT k(constant) ROWS ONLY;
```
## Having

The HAVING clause was added to SQL because the WHERE keyword cannot be used with aggregate functions.
```
SELECT column_name(s)

FROM table_name

WHERE condition

GROUP BY column_name(s)

HAVING condition

ORDER BY column_name(s);
```


The following SQL statement lists the number of customers in each country. Only include countries with more than 5 customers:

```
SELECT COUNT(CustomerID), Country

FROM Customers

GROUP BY Country

HAVING COUNT(CustomerID) > 5;
```

The following SQL statement lists the number of customers in each country, sorted high to low (Only include countries with more than 5 customers):

```
SELECT COUNT(CustomerID), Country

FROM Customers

GROUP BY Country

HAVING COUNT(CustomerID) > 5

ORDER BY COUNT(CustomerID) DESC;
```


## CASE
The CASE statement goes through conditions and returns a value when the first condition is met (like an if-then-else statement). So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.

If there is no ELSE part and no conditions are true, it returns NULL.
```
CASE
    WHEN condition1 THEN result1
    WHEN condition2 THEN result2
    WHEN conditionN THEN resultN
    ELSE result
END;
```

The following SQL goes through conditions and returns a value when the first condition is met:

```
SELECT OrderID, Quantity,
CASE
    WHEN Quantity > 30 THEN 'The quantity is greater than 30'
    WHEN Quantity = 30 THEN 'The quantity is 30'
    ELSE 'The quantity is under 30'
END AS QuantityText
FROM OrderDetails;
```
The following SQL will order the customers by City. However, if City is NULL, then order by Country:

```
SELECT CustomerName, City, Country
FROM Customers
ORDER BY
(CASE
    WHEN City IS NULL THEN Country
    ELSE City
END);

```
