## 1. Find all Delivered orders and display only orderDate, status, shippingCity, and customerId. Sort the result by orderDate from newest to oldest.

## 2. Find all products from the Electronics category having a rating of 4.5 or higher. Display only product name, brand, price, and rating.

## 3. Find the 5 most expensive products in the database. Display product name, category, brand, and price. 

## 4. Find the 3 products with the lowest stock. Display their name, category, stock, and price.

## 5. Find all customers who are either Gold or Platinum members and are older than 25. Display only name, city, age, and membership.

## 6. Find the number of customers in each membership category. Sort the membership categories by customer count in descending order.

## 7. Calculate the average product price for each category. Display category and averagePrice, sorted by average price from highest to lowest.

## 8. Find the total stock available for each product category. Display category and total stock, sorted by total stock descending.

## 9. Find the average rating of products for each brand. Display only brands having an average rating greater than 4.4.

## 10. Count the number of orders for each order status. Sort the result from the status having the highest number of orders to the lowest.

## 11. Find the total quantity of products ordered across all orders. You must use $unwind on the items array
## 12. Find the total quantity sold for each product. The result should contain productId and totalQuantity. Sort products by total quantity sold in descending order.

## 13. Find the top 5 most frequently ordered products based on total quantity. Use the items array from the orders collection and $lookup to display the product name instead of only productId.

## 14. Find how many different products have been included in orders. Do not simply count the number of order documents. Use $unwind and determine the number of unique productIds.

## 15. Find the total number of items purchased by each customer. Use $unwind and $group. The output should contain customerId and totalItems. Sort customers by total items purchased.

## 16. Display all orders along with the customer's name, email, and city. Use $lookup between orders and customers. Do not display the complete customer document.

## 17. Display all orders along with customer name, order date, order status, and shipping city. Sort the orders by order date descending. 

## 18. Find all Delivered orders placed by Gold members. You will need to combine orders and customers and filter based on both order status and customer membership.

## 19. Find the total number of orders placed by each customer. Display customerName, city, and totalOrders. Sort customers by total orders descending.

## 20. Find customers who have placed more than one order. Display their name, membership, city, and number of orders.

## 21. Calculate the total quantity sold for each product, and display productName, category, brand, and totalQuantitySold. You must use $unwind, $lookup, $group, and $sort.

## 22. Find the top 5 products by total quantity sold, but only consider products belonging to the Electronics category. The result should include product name, brand, price, and total quantity sold.

## 23. Find the total number of products purchased by customers from each city. For every city, calculate the total quantity of items ordered. You will need to combine orders, customers, and the items array.

## 24. Create a single aggregation using $facet that returns three reports simultaneously: (1) Product Statistics — total number of products and average product price; (2) Category Statistics — number of products in each category and average price for each category; (3) Rating Statistics — products with rating >= 4.5 and products with rating < 4.5.

## 25. Final Challenge: Create an E-commerce Sales Dashboard aggregation using $facet. Return all of the following in a single aggregation result: (A) Order Summary — total, delivered, pending, cancelled, and shipped orders; (B) Customer Summary — top 5 customers based on number of orders, with name, city, membership, and order count; (C) Product Summary — top 5 products based on quantity sold, with product name, category, brand, and total quantity sold; (D) Payment Summary — total amount of Paid payments grouped by payment method; (E) Category Summary — number of products and average price for every product category. Constraint: solve the complete dashboard using one aggregation pipeline and use $facet to generate the different reports.