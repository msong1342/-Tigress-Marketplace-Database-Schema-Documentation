# 📌 **Tigress Marketplace Database Schema Documentation**

## 📚 **Overview**
This document outlines the **database schema** for the **Tigress Marketplace** platform. The database is structured to support user management, product listings, order processing, rentals, payments, notifications, and support ticketing.

## 🏢 **Database Structure**
The schema consists of **multiple tables**, each serving a specific role. Below is a breakdown of key tables and their relationships.

---

## **🛠 Core Tables**
### 1️⃣ **Users & Employees**
- **`personal_info`**: Stores user details like name, email, and contact info.
- **`employees`**: Tracks staff members, including roles (`admin, support_agent, manager, IT, etc.`), salaries, and employment status.

### 2️⃣ **Listings & Products**
- **`listings`**: Represents marketplace products with attributes like brand, size, price, and status (`active, sold, pending`).
- **`listing_images`**: Stores image URLs related to product listings.
- **`favorites`**: Tracks user-favorited products.

### 3️⃣ **Orders & Transactions**
- **`order_details`**: Stores general order information.
- **`purchased_order`**: Handles direct purchases.
- **`rental_orders`**: Manages rental-based transactions, including return tracking.
- **`payments`**: Stores payment transactions.

### 4️⃣ **Addresses & Delivery**
- **`addresses`**: Stores user addresses, including city, state, and country.
- **`delivery_methods`** (if applicable): Defines delivery options.

### 5️⃣ **Support & Notifications**
- **`support_tickets`**: Tracks customer support issues.
- **`user_notifications`**: Stores system-generated notifications.

---

## **🔗 Database Relationships**
### ✅ **Key Foreign Keys**
- **`listings.user_id`** → `personal_info.user_id`
- **`order_details.listing_id`** → `listings.listing_id`
- **`purchased_order.order_id`** → `order_details.id`
- **`rental_orders.order_details_id`** → `order_details.id`
- **`support_tickets.user_id`** → `personal_info.user_id`
- **`payments.user_id`** → `personal_info.user_id`
- **`employees.user_id`** → `personal_info.user_id`

---

## **🎯 Features & Functionalities**
### 🛍 **E-commerce & Rental Support**
- Users can **buy or rent products** with separate tracking for purchase vs. rental orders.
- **Automated order processing** to differentiate rental and purchase transactions.

### 🔔 **Notifications & Customer Support**
- Users receive **notifications** for orders and updates.
- A **support ticket system** allows customers to raise issues.

### 🔒 **Security & Access Control**
- **Row-Level Security (RLS)** policies are in place for protecting sensitive user data.
- Employees have restricted permissions based on roles.

---

## **🛠 Future Improvements**
- Implement **order tracking** for shipments.
- Introduce **user reviews & ratings**.
- Optimize **RLS policies** for a more secure data access structure.

---

## **📌 Notes**
- The current setup **does not yet collect real data** as the platform is still under development.
- Further improvements will be **implemented as the website launches** and data collection begins.

---

