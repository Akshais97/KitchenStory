# 🍽️ Kitchen Story — Full-Stack E-Commerce Web Application

Kitchen Story is a **full-stack online grocery/food shopping platform** built with a **Spring Boot backend**, **Angular frontend**, and **MySQL database**.  
It provides product browsing, cart management, ordering, and admin product control — similar to a simplified Amazon/BigBasket food-store system.

## ⭐ Features

### 👤 User Features
- User registration & login (JWT secured)
- View all available food products
- Add items to cart / update quantity
- Place orders
- View order history
- Profile & session management

### 🛠️ Admin Features
- Admin login (separate from user)
- Add / edit / delete products (CRUD)
- View all users
- View all orders
- Inventory control

### 🔐 Security
- Spring Security & JWT Authentication
- Custom JWT filter + AuthEntryPoint
- Password hashing
- Role-based access (ADMIN / USER)

## 🧰 Tech Stack

### Frontend
- Angular 13+
- TypeScript
- Angular Routing
- Bootstrap / CSS

### Backend
- Spring Boot 2+
- Spring Security + JWT
- Spring Data JPA (Hibernate)
- Maven

### Database
- MySQL  
- JPA/Hibernate ORM

## 🏗️ Project Architecture

[ Angular Frontend ] --> REST API --> [ Spring Boot Backend ] --> [ MySQL Database ]

## 📁 Folder Structure

KitchenStory-master/
│
├── Backend_SpringBoot/
│   ├── src/main/java/com/kitchenstory/
│   │   ├── controller/       
│   │   ├── config/           
│   │   ├── entities/         
│   │   ├── repository/       
│   │   ├── service/          
│   │   └── util/             
│   └── src/main/resources/
│       └── application.properties
│
└── Frontend_Angular/
    ├── src/app/
    │   ├── components/       
    │   ├── services/         
    │   ├── models/           
    │   └── guards/           

## 🚀 Backend Setup (Spring Boot)

### 1. Configure MySQL
CREATE DATABASE kitchenstory;

### 2. Update application.properties

spring.datasource.url=jdbc:mysql://localhost:3306/kitchenstory
spring.datasource.username=YOUR_DB_USER
spring.datasource.password=YOUR_DB_PASSWORD

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true

### 3. Run Backend
cd Backend_SpringBoot
mvn clean install
mvn spring-boot:run

## 🎨 Frontend Setup (Angular)

cd Frontend_Angular
npm install
ng serve --open

## 🔑 Environment Variables

export const environment = {
  production: false,
  apiBaseUrl: 'http://localhost:8080'
};

## 📡 API Endpoints

### Auth
POST /authenticate — User login  
POST /register — User signup  
POST /admin/login — Admin login  

### Products  
GET /allproducts — List products  
POST /addproduct — Add product  
PUT /updateproduct/{id} — Edit product  
DELETE /deleteproduct/{id} — Remove product  

### Cart
GET /cart/{userId} — Get user cart  
POST /cart/add — Add item  
DELETE /cart/remove/{id} — Remove item  

### Orders
POST /order/place — Place order  
GET /order/user/{userId} — User orders  
GET /order/all — Admin orders  

## 📄 License
MIT License
