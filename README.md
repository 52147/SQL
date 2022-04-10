# SQL

## Join
1. (inner) join
2. left (outer) join
3. right (outer) join
4. cross join

![image](https://user-images.githubusercontent.com/79159894/162604926-3d1f6e35-1b98-4afb-a385-0a77deca0cd9.png)


## DENSE_RANK
-  is one of the vital Analytic functions of Oracle. 
-  It is used to get the rank of a row in a group of rows. It always results in the consecutive ranking of the rows.

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







