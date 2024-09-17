## First Query:
### What is the average age and standard deviation of customers who have a male cosmetic consultant and are also allergic?


```
SELECT

  ROUND(AVG(Customer.age), 2) AS average_age,
  
  ROUND(STDDEV(Customer.age), 2) AS age_stddev
  
FROM Customer

  INNER JOIN Cosmetic_Consultant ON Customer.cosmetic_ssn =Cosmetic_Consultant.cosmetic_ssn
  
WHERE Cosmetic_Consultant.gender = 'M'

  AND EXISTS ( 
  
                SELECT *
                
                FROM Allergic
                
               WHERE Allergic.customer_ssn = Customer.customer_ssn) ; 
```
            

## Second Query:
### What are the top 3 best-selling products, and what are their categories, manufacturers, average price, and the quantity purchased?

```
SELECT 

Sell.category, Manufacturing_Company.name, AVG(Cosmetic_Product_Recommendation.quantity) AS product_count, AVG(Sell.price) 

AS average_price

FROM 

    Cosmetic_Product_Recommendation
    
INNER JOIN 

    Product ON Cosmetic_Product_Recommendation.product_id = Product.product_id
    
INNER JOIN 

Manufacturing_Company ON Product.manufacturing_company_id = Manufacturing_Company.manufacturing_company_id INNER JOIN 

     Sell ON Product.product_id = Sell.product_id
     
GROUP BY 

    Sell.category, Manufacturing_Company.name  
    
ORDER BY

 `product_count` DESC
 
LIMIT 3;
```

## Third Query:
### Which 3 pharmacies are expected to sell the most products?

```
SELECT

  Pharmacy.name,
  
  SUM(Cosmetic_Product_Recommendation.quantity) AS total_sales
  
FROM Cosmetic_Product_Recommendation

INNER JOIN Product ON Product.product_id = Cosmetic_Product_Recommendation.product_id

INNER JOIN Sell ON Sell.product_id = Product.product_id

INNER JOIN Pharmacy on Pharmacy.pharmacy_id = Sell.pharmacy_id

GROUP BY Pharmacy.name

ORDER BY total_sales DESC

LIMIT 3; 
```

## Fourth Query:
### Which customers are expected to purchase products from exactly one category, with each purchase including more than 50 units?

```
SELECT

Customer.name, COUNT(DISTINCT Sell.category) AS category_count, Sell.category

FROM Customer 

INNER JOIN Cosmetic_Product_Recommendation ON Customer.customer_ssn = Cosmetic_Product_Recommendation.Customer_ssn

INNER JOIN Product  ON Product.product_id = Cosmetic_Product_Recommendation.product_id

INNER JOIN Sell ON Sell.product_id = Product.product_id

WHERE Cosmetic_Product_Recommendation.quantity > 50

GROUP BY Customer.customer_ssn, Sell.category

HAVING category_count = 1;
```

## Fifth Query:
### What is the number and percentage of customers who purchased more than 30 products and are expected to pay above the average total cost?

```
SELECT

    COUNT(DISTINCT Customer.customer_ssn) AS total_count,
    
    (COUNT(DISTINCT Customer.customer_ssn) / (SELECT COUNT(DISTINCT Customer.customer_ssn) FROM Customer)) * 100 AS percentage 
    
     FROM
     
    Customer
    
INNER JOIN

    (
    
        SELECT
        
            Cosmetic_Product_Recommendation.Customer_ssn,
            
            SUM(Cosmetic_Product_Recommendation.quantity * Sell.price) AS total_cost
            
        FROM
        
            Cosmetic_Product_Recommendation
            
        INNER JOIN
        
            Sell ON Cosmetic_Product_Recommendation.product_id = Sell.product_id
            
        WHERE
        
            Cosmetic_Product_Recommendation.quantity >30
            
        GROUP BY
        
            Cosmetic_Product_Recommendation.Customer_ssn
            
    ) AS t ON Customer.customer_ssn = t.Customer_ssn
    
WHERE

t.total_cost > (

        SELECT AVG(total_cost)
        
        FROM
        
            (
                SELECT
                    Cosmetic_Product_Recommendation.Customer_ssn,
                    SUM(Cosmetic_Product_Recommendation.quantity * Sell.price) AS total_cost
                FROM
                    Cosmetic_Product_Recommendation
                INNER JOIN
                    Sell ON Cosmetic_Product_Recommendation.product_id = Sell.product_id
                WHERE
                    Cosmetic_Product_Recommendation.quantity >30
                GROUP BY
                    Cosmetic_Product_Recommendation.Customer_ssn 
            ) AS t
    );
```




