# 🔐 Role-Based Authorization (RBAC) using Spring Boot

## 📌 Project Overview

This project demonstrates **Role-Based Authorization (RBAC)** using Spring Boot and Spring Security.

The application allows:

* User authentication using Basic Auth
* Role-based access control (USER, ADMIN)
* Secured APIs based on roles
* Testing using Postman

---

## 🎯 Objective

* Implement authentication and authorization in Spring Boot
* Restrict API access based on roles
* Understand **401 Unauthorized** and **403 Forbidden**
* Test secured APIs using Postman

---

## 🛠️ Technologies Used

* Java 17
* Spring Boot
* Spring Security
* Spring Data JPA
* H2 Database
* Maven
* Postman

---

## 📁 Project Structure

```
experiment7/
├── src/
│   ├── main/
│   │   ├── java/com/example/experiment7/
│   │   │   ├── config/
│   │   │   ├── controller/
│   │   │   ├── entity/
│   │   │   ├── repository/
│   │   │   └── service/
│   │   └── resources/
│   │       ├── application.properties
│   │       └── data.sql
├── screenshots/
├── pom.xml
└── README.md
```

---

## 🔐 Roles

* ROLE_USER
* ROLE_ADMIN

---

## 🌐 API Endpoints

| Endpoint               | Access      | Description              |
| ---------------------- | ----------- | ------------------------ |
| `/api/public/hello`    | Public      | Accessible without login |
| `/api/user/profile`    | USER, ADMIN | User-level access        |
| `/api/admin/dashboard` | ADMIN only  | Admin-only access        |

---

## 🔑 Authentication

* HTTP Basic Authentication is used
* Credentials:

| Username | Password | Role  |
| -------- | -------- | ----- |
| user1    | 12345    | USER  |
| admin1   | 12345    | ADMIN |

---

## 🔒 Authorization Rules

* Public endpoints → No authentication required
* User endpoints → Accessible by USER and ADMIN
* Admin endpoints → Accessible by ADMIN only

---

## ⚠️ HTTP Status Codes

| Code             | Meaning                           |
| ---------------- | --------------------------------- |
| 200 OK           | Request successful                |
| 401 Unauthorized | Authentication required / invalid |
| 403 Forbidden    | Access denied due to role         |

---

## 🧪 Testing using Postman

### ✅ Public Endpoint

```
GET /api/public/hello
```

### ✅ USER Access

```
GET /api/user/profile
Auth: user1 / 12345
```

### ❌ USER → ADMIN

```
GET /api/admin/dashboard
Auth: user1 / 12345
→ 403 Forbidden
```

### ✅ ADMIN Access

```
GET /api/admin/dashboard
Auth: admin1 / 12345
```

### ❌ Without Login

```
GET /api/user/profile
→ 401 Unauthorized
```

---

## 📸 Screenshots

Screenshots are available in the `screenshots/` folder:

* Login success
* User accessing user endpoint
* Admin accessing admin endpoint
* Access denied (403)

---

## ▶️ How to Run

1. Clone the repository
2. Open project in VS Code
3. Run:

```
mvn spring-boot:run
```

4. Open Postman and test APIs

---

## 🧠 Key Concepts

### 🔹 Authentication

Verifies user identity using username and password.

### 🔹 Authorization

Determines access rights based on roles.

### 🔹 RBAC

Access control mechanism based on assigned roles.

---

## 🎯 Conclusion

This project successfully demonstrates:

* Role-based access control
* Secure API development
* Authentication and authorization using Spring Security

---

## 👨‍💻 Author

Prashant Bishnoi
