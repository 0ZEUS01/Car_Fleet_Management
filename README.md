# 🚗 Car Fleet Management System

The **Car Fleet Management System** is a full-stack solution designed to monitor and manage a fleet of vehicles in real-time. It includes:

- 📱 A mobile app (Android) to track car locations
- 🕸️ A web platform (Spring Boot) for admin control
- 🔗 An integrated REST API for communication
- 📊 Documentation and database schema for deployment and maintenance

---

## 📱 Android Application

The **Android app** is used by drivers and installed in each vehicle. It periodically sends the GPS coordinates of the car to the backend system using HTTP requests or background services.

### Features

- 📍 Real-time location tracking via GPS
- 🔐 Secure login for drivers
- 📡 Sends location to server via REST API
- 📷 Optionally capture vehicle images or documents
- 🔋 Optimized for background usage with minimal battery drain

### Tech Stack

- Language: Java or Kotlin
- IDE: Android Studio
- Permissions:
  ```xml
  <uses-permission android:name="android.permission.INTERNET" />
  <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
  <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
  <uses-permission android:name="android.permission.FOREGROUND_SERVICE" />
  ```

### Firebase or Local DB
Optional: Firebase used for auth/logging, or Room database for local data caching.

---

## 🕸️ Web Application (Admin Dashboard)

Built using **Spring Boot**, the web application allows fleet managers to monitor and manage the car fleet in real-time.

### Features

- 🗺️ View car positions on an interactive map
- 🚘 Register and manage vehicles
- 👤 Manage drivers and accounts
- 🧾 View movement history and logs
- 📊 Dashboard with key metrics (e.g., number of active cars)

### Tech Stack

- Spring Boot (REST + Web MVC)
- Thymeleaf or React for frontend (if applicable)
- MySQL / PostgreSQL for persistent storage
- Hibernate / JPA for ORM
- Spring Security for authentication

---

## 🔗 API (Communication Layer)

The Android and web apps communicate using a RESTful API built in **Spring Boot**.

### Example Endpoints

- `POST /api/location` – Submit current location
- `GET /api/vehicles/{id}/location` – Get last known location
- `GET /api/vehicles` – List all vehicles
- `PUT /api/vehicles/{id}` – Update vehicle status/info

---

## 🗃️ Repository Contents

```
Car_Fleet_Management/
├── AndroidApp/              # Android Studio project
├── WebApp/                  # Spring Boot web project
├── API/                     # REST API layer (if separated)
├── docs/
│   ├── report.pdf           # Full project report
│   ├── conception/          # UML diagrams, ERD, use case diagrams
│   └── BD/                  # SQL Scripts, database schema
└── README.md                # You're here!
```

---

## 🧠 System Overview

### Architecture

```
[ANDROID APP] 📱
     ↕ REST API
[SPRING BOOT BACKEND] ☁️
     ↕ JDBC / JPA
[DATABASE] 🗃️
```

### Database Design

- Vehicles table
- Users (Admins, Drivers)
- Location logs
- Sessions / Logs / Events

---

## 🧪 Running the Project

### Android App

1. Open `AndroidApp` in Android Studio
2. Add location permissions and run on a real device
3. Set the backend API base URL in the app settings

### Web Dashboard

1. Open `WebApp` in IntelliJ or Eclipse
2. Configure `application.properties`:
   ```properties
   spring.datasource.url=jdbc:mysql://localhost:3306/fleetdb
   spring.datasource.username=root
   spring.datasource.password=yourpassword
   ```
3. Run the application:
   ```bash
   ./mvnw spring-boot:run
   ```
4. Access it via: `http://localhost:8080`

---

## 🛠️ Technologies Used

| Tech               | Purpose                        |
|--------------------|--------------------------------|
| Java / Kotlin      | Android Development            |
| Spring Boot        | Backend Web & API              |
| MySQL/PostgreSQL   | Data Storage                   |
| REST API           | Communication between apps     |
| Firebase (optional)| Notifications/Auth             |
| Google Maps API    | Displaying live car locations  |

---

## 📄 Documentation

All related documentation is available in the `/docs` folder:

- 📘 `report.pdf`: Full system report
- 🗺️ `conception/`: Diagrams (UML, sequence, ER, use cases)
- 🧾 `BD/`: SQL scripts and database exports

---

## 🚀 Future Improvements

- [ ] Push notifications for alerts (speeding, geo-fencing)
- [ ] Role-based access for companies with multiple admins
- [ ] Analytics dashboard (avg speed, distance, idle time)
- [ ] Offline caching of car movements in Android app

---

## 📄 License

This project is licensed under the MIT License. See `LICENSE` for details.

---

## 🙌 Authors & Contributions

Feel free to contribute via pull requests or issues. This project was developed as part of a fleet tracking solution for real-world deployment.

> “Managing a car fleet has never been this smart 🚗💨”
