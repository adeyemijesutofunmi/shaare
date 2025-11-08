# System Architecture: Shaare Mobile App

## 🏗️ Overview
The Shaare platform is designed as a **mobile-first service marketplace** connecting customers to verified cleaning professionals. It uses a modular client-server architecture for scalability, performance, and real-time communication.

---

## 🧩 Architecture Diagram (Text Overview)
[Flutter App] ⇄ [REST API / GraphQL Gateway] ⇄ [Application Server]
↓
[Database Layer]
↓
[Cloud Storage + Notifications]



---

## 🖥️ Frontend
**Technology:** Flutter  
**Description:**  
The Flutter mobile application provides a clean, intuitive UI for both customers and cleaners. It handles:
- Authentication and onboarding  
- Service booking forms  
- Real-time job status updates  
- In-app payments and reviews  

**Reasoning:**  
Flutter enables fast cross-platform deployment (iOS + Android) with consistent UI and lower development cost.

---

## ⚙️ Backend
**Technology Options:** Node.js (NestJS) *or* .NET 8 Web API  
**Responsibilities:**
- Expose RESTful or GraphQL APIs for all user actions  
- Handle business logic (booking, scheduling, payments, notifications)  
- Manage authentication and role-based access (Customer, Cleaner, Admin)  
- Integrate with third-party APIs (payment gateway, push notifications)  

**Communication:**  
The frontend interacts with the backend through HTTPS API calls secured by JWT-based authentication.

---

## 🗄️ Database
**Technology:** PostgreSQL (SQL) or Firebase Firestore (NoSQL)  
**Core Tables/Collections:**
- `Users` (customer, cleaner, admin profiles)
- `Bookings` (service type, date, time, status)
- `Payments` (transaction history)
- `Reviews` (ratings and comments)
- `Notifications` (push and in-app alerts)

**Reasoning:**  
PostgreSQL ensures strong data consistency and structured relationships; Firestore offers flexibility for scalability. Either option supports future analytics and service recommendations.

---

## ☁️ Cloud Services & Integrations
- **Storage:** AWS S3 / Firebase Storage for images and proof-of-work uploads  
- **Authentication:** Firebase Auth or AWS Cognito for secure login  
- **Notifications:** Firebase Cloud Messaging (FCM) for updates and reminders  
- **Payments:** Paystack or Stripe for local and international transactions  

---

## 🔐 Security Considerations
- JWT-based authentication for API requests  
- Encrypted data transmission (HTTPS)  
- Field-level validation on all API endpoints  
- User input sanitization and role-based access control  

---

## 🔄 Scalability and Feasibility
The system’s modular design supports:
- Horizontal scaling of the backend using AWS ECS or Firebase Functions  
- Easy onboarding of new service categories  
- Continuous deployment through GitHub Actions or AWS CodePipeline  

This architecture is technically feasible with widely used frameworks, ensuring maintainability, performance, and ease of developer onboarding.

