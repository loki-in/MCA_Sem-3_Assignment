# UNIT 3 ASSIGNMENT — MongoDB Aggregation Pipeline

## Medium–Hard Level | 25 Questions

This assignment focuses on solving real-world E-commerce data analysis problems using the MongoDB Aggregation Pipeline.

The provided E-commerce dataset contains information about:

- Customers
- Products
- Orders
- Payments

The objective is to understand and implement MongoDB aggregation stages such as `$match`, `$project`, `$sort`, `$limit`, `$group`, `$unwind`, `$lookup`, and `$facet`.

---

## 📌 Assignment Objectives

The main objectives of this assignment are:

- Understand MongoDB Aggregation Pipeline.
- Filter documents using `$match`.
- Select required fields using `$project`.
- Sort and limit results using `$sort` and `$limit`.
- Perform calculations and grouping using `$group`.
- Work with arrays using `$unwind`.
- Combine collections using `$lookup`.
- Generate multiple reports using `$facet`.
- Perform E-commerce sales and customer analysis.

---

## 🗂️ Dataset Collections

The assignment uses an E-commerce dataset containing the following collections:

```text
customers
products
orders
payments
```

**1. Customers**

Contains customer-related information such as:

- customerId
- name
- email
- city
- age
- membership

**2. Products**

Contains product information such as:

- productId
- name
- category
- brand
- price
- stock
- rating

**3. Orders**

Contains order information such as:

- orderId
- customerId
- orderDate
- status
- shippingCity
- items

The **items** field contains an array of ordered products.

**4. Payments**

Contains payment information such as:

- paymentId
- orderId
- amount
- status
- paymentMethod

---

## 📚 Assignment Questions

### Q1. Find All Delivered Orders

Find all **Delivered** orders and display only:

- orderDate
- status
- shippingCity
- customerId

Sort the result by **orderDate** from newest to oldest.

### Q2. Highly Rated Electronics

Find all products from the **Electronics** category having a rating of **4.5 or higher**.

Display only:

- Product name
- Brand
- Price
- Rating

### Q3. Five Most Expensive Products

Find the **5 most expensive** products in the database.

Display:

- Product name
- Category
- Brand
- Price

### Q4. Three Products with Lowest Stock

Find the **3 products with the lowest stock**.

Display:

- Name
- Category
- Stock
- Price

### Q5. Gold or Platinum Customers

Find all customers who are either **Gold** or **Platinum** members and are **older than 25**.

Display only:

- Name
- City
- Age
- Membership

### Q6. Number of Customers by Membership

Find the number of customers in each membership category.

Sort the membership categories by customer count in descending order.

### Q7. Average Product Price by Category

Calculate the average product price for each category.

Display:

- category
- averagePrice

Sort by average price from highest to lowest.

### Q8. Total Stock by Category

Find the total stock available for each product category.

Display:

- category
- totalStock

Sort by total stock in descending order.

### Q9. Average Rating by Brand

Find the average rating of products for each brand.

Display only brands having an average rating greater than **4.4**.

### Q10. Number of Orders by Status

Count the number of orders for each order status.

Sort the result from the status having the highest number of orders to the lowest.

---

### 🔄 Working with Arrays Using $unwind

### Q11. Total Quantity of Products Ordered

Find the total quantity of products ordered across all orders.

You must use `$unwind` on the **items** array.

### Q12. Total Quantity Sold for Each Product

Find the total quantity sold for each product.

The result should contain:

- productId
- totalQuantity

Sort products by total quantity sold in descending order.

### Q13. Top 5 Most Frequently Ordered Products

Find the top 5 most frequently ordered products based on total quantity.

Requirements:

- Use the **items** array from the **orders** collection.
- Use `$unwind`.
- Use `$lookup`.
- Display the **product name** instead of only **productId**.

### Q14. Number of Different Products Ordered

Find how many different products have been included in orders.

Requirements:

- Use `$unwind`.
- Determine the number of unique **productId** values.
- Do not simply count the number of order documents.

### Q15. Total Items Purchased by Each Customer

Find the total number of items purchased by each customer.

Requirements:

- Use `$unwind`.
- Use `$group`.

The output should contain:

- customerId
- totalItems

Sort customers by total items purchased.

---

### 🔗 Joining Collections Using $lookup

### Q16. Orders with Customer Information

Display all orders along with the customer's:

- Name
- Email
- City

Use `$lookup` between **orders** and **customers**.

Do not display the complete customer document.

### Q17. Orders with Customer Name

Display:

- Customer name
- Order date
- Order status
- Shipping city

Sort the orders by order date in descending order.

### Q18. Delivered Orders by Gold Members

Find all **Delivered** orders placed by **Gold** members.

You will need to combine:

- orders
- customers

Filter based on both:

- order status
- customer membership

### Q19. Total Orders Placed by Each Customer

Find the total number of orders placed by each customer.

Display:

- customerName
- city
- totalOrders

Sort customers by total orders in descending order.

### Q20. Customers with More Than One Order

Find customers who have placed **more than one order**.

Display:

- Name
- Membership
- City
- Number of orders

---

### 🚀 Advanced Aggregation

### Q21. Total Quantity Sold for Each Product

Calculate the total quantity sold for each product.

Display:

- productName
- category
- brand
- totalQuantitySold

You must use:

- `$unwind`
- `$lookup`
- `$group`
- `$sort`

### Q22. Top 5 Electronics Products by Quantity Sold

Find the top 5 products by total quantity sold, but only consider products belonging to the **Electronics** category.

The result should include:

- productName
- brand
- price
- totalQuantitySold

### Q23. Total Products Purchased by City

Find the total number of products purchased by customers from each city.

For every city, calculate the total quantity of items ordered.

You will need to combine:

- orders
- customers
- items array

---

### 🎯 $facet Aggregation

### Q24. Multiple Product Reports

Create a single aggregation using `$facet` that returns **three reports** simultaneously.

**A. Product Statistics**

Return:

- Total number of products
- Average product price

**B. Category Statistics**

Return:

- Number of products in each category
- Average price for each category

**C. Rating Statistics**

Return:

- Products with rating >= 4.5
- Products with rating < 4.5

### 🏆 Q25. Final Challenge — E-commerce Sales Dashboard

Create an **E-commerce Sales Dashboard** aggregation using `$facet`.

Return all of the following in a single aggregation result.

**A. Order Summary**

Return:

- Total orders
- Delivered orders
- Pending orders
- Cancelled orders
- Shipped orders

**B. Customer Summary**

Find the top 5 customers based on number of orders.

Display:

- name
- city
- membership
- orderCount

**C. Product Summary**

Find the top 5 products based on quantity sold.

Display:

- productName
- category
- brand
- totalQuantitySold

**D. Payment Summary**

Find the total amount of **Paid** payments grouped by payment method.

Display:

- paymentMethod
- totalAmount

**E. Category Summary**

For every product category, calculate:

- numberOfProducts
- averagePrice

**Constraint**

The complete dashboard must be solved using:

- One aggregation pipeline
- `$facet`

Use different `$facet` branches to generate the different reports.

---

## 🧩 MongoDB Operators Covered

| Operator  | Questions                  |
|-----------|----------------------------|
| $match    | 1–5, 18, 22                |
| $project  | 1–5, 16–18                 |
| $sort     | 1–4, 6–10, 12–13, 17, 19–22|
| $limit    | 3, 4, 13, 22               |
| $group    | 6–15, 19–23                |
| $unwind   | 11–15, 21–23               |
| $lookup   | 13, 16–23                  |
| $facet    | 24–25                      |

---

## 🛠️ Requirements

The following tools are required:

- MongoDB
- MongoDB Compass or MongoDB Shell
- MongoDB Atlas (optional)
- E-commerce dataset
- Basic MongoDB knowledge
- Understanding of Aggregation Pipeline

---

## ▶️ How to Run

**Step 1: Start MongoDB**

You can use either:

- MongoDB Local Server
- MongoDB Atlas

**Step 2: Open MongoDB Compass**

Connect to your MongoDB database.

For a local MongoDB server:

```text
mongodb://localhost:27017
```

For MongoDB Atlas, use your Atlas connection string.

**Step 3: Select the Database**

Open the database containing:

- customers
- products
- orders
- payments

**Step 4: Open Aggregations**

Select the required collection and open the **Aggregations** tab.

Create the pipeline stages according to each question.

---

## 💻 Example Aggregation

Example solution for **Question 1**:

```javascript
[
  {
    $match: {
      status: "Delivered"
    }
  },
  {
    $project: {
      _id: 0,
      orderDate: 1,
      status: 1,
      shippingCity: 1,
      customerId: 1
    }
  },
  {
    $sort: {
      orderDate: -1
    }
  }
]
```

---

## 📁 Recommended Repository Structure

```text
MongoDB-Aggregation-Pipeline/
│
├── README.md
│
├── dataset/
│   ├── customers.json
│   ├── products.json
│   ├── orders.json
│   └── payments.json
│
├── solutions/
|   ├── Ans.md
│   └──Questions.md
 

---

## ⚠️ Important Instructions

The questions are provided **without solutions or aggregation pipelines**.

Students are expected to:

1. Understand the problem.
2. Identify the required collection.
3. Identify the required aggregation operators.
4. Decide the correct aggregation stage order.
5. Construct the aggregation pipeline.
6. Execute and verify the result.
7. Understand and explain the pipeline.

Copied projects or pipelines without understanding are not recommended.

---

## 🎓 Learning Outcomes

After completing this assignment, the student should be able to:

- Build MongoDB aggregation pipelines.
- Filter documents using `$match`.
- Select fields using `$project`.
- Sort and limit results.
- Group documents using `$group`.
- Perform calculations using `$sum` and `$avg`.
- Work with arrays using `$unwind`.
- Join collections using `$lookup`.
- Generate multiple reports using `$facet`.
- Analyze E-commerce sales data.
- Build a MongoDB-based sales dashboard.

---

## 📌 Assignment Summary

| Section       | Questions | Main Concepts                          |
|---------------|-----------|----------------------------------------|
| Basic Queries | Q1–Q5     | $match, $project, $sort, $limit        |
| Grouping      | Q6–Q10    | $group, $sort                          |
| Arrays        | Q11–Q15   | $unwind, $group                        |
| Lookup        | Q16–Q20   | $lookup, $match, $group                |
| Advanced      | Q21–Q23   | $unwind, $lookup, $group, $sort        |
| Facet         | Q24–Q25   | $facet                                 |

---

## 👨‍💻 Author

**Lokesh**

MCA Student

Assignment: Unit 3 — MongoDB Aggregation Pipeline