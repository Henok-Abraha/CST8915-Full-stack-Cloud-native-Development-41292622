# CST8915 Lab 1: Algonquin Pet Store on Azure VM

**Student Name:** Henok Abraha  
**Student ID:** 41292622  
**Course:** CST8915 Full-stack Cloud-native Development  
**Semester:** Fall 2026  

---

## Demo Video

[Watch Demo Video](hhttps://www.youtube.com/watch?v=RypCBSfzQVo)


---

## Technical Explanations

### Order Service (Node.js)

The Order Service is responsible for receiving orders from the Store Front. It is built using Node.js and runs on port 3000. When a customer selects a product, enters a quantity, and places an order, the Store Front sends the order information to the Order Service.

The Order Service communicates with RabbitMQ and publishes the order as a message to the `order_queue`. RabbitMQ then stores the message in the queue. This allows the Order Service to handle orders separately from the other services in the application.

### Product Service (Rust)

The Product Service is responsible for providing the product catalog for the Pet Store. It is written in Rust and runs on port 3030. It provides information about the available products, including their IDs, names, and prices.

The Store Front communicates with the Product Service to retrieve the available products and display them to the customer. This separates the product data from the user interface and allows the Product Service to manage product information independently.

### Store Front (Vue.js)

The Store Front is the user interface of the Algonquin Pet Store. It is built using Vue.js and runs on port 8080. It allows customers to view the available products, select a product, enter a quantity, see the total price, and place an order.

The Store Front communicates with both the Product Service and the Order Service. It gets product information from the Product Service and displays it to the customer. When the customer places an order, the Store Front sends the order information to the Order Service, which then publishes the order to RabbitMQ.

---

## Acknowledgments

This lab was completed using the CST8915 Lab 1 instructions and starter application provided by the course instructor.
