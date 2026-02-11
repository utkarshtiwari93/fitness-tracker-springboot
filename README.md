
# 🏋️ FitTrack - Fitness Tracking Application

![Spring Boot](https://img.shields.io/badge/Spring%20Boot-4.0.2-brightgreen.svg)
![Java](https://img.shields.io/badge/Java-25-orange.svg)
![MySQL](https://img.shields.io/badge/MySQL-8.0-blue.svg)

A full-stack fitness tracking application for monitoring workouts, tracking metrics, and receiving personalized recommendations.

---

## ✨ Features

- 🔐 **JWT Authentication** - Secure, stateless user authentication
- 📊 **Activity Tracking** - Log workouts (Running, Cycling, Yoga, Weight Training, etc.)
- 📈 **Performance Metrics** - Track duration, calories, distance, and custom data
- 💡 **Recommendations** - Personalized fitness suggestions
- 📱 **Responsive UI** - Clean, modern frontend interface
- 📚 **API Documentation** - Interactive Swagger UI

---

## 🛠️ Tech Stack

**Backend:** Spring Boot 4.0.2, Spring Security, JWT, JPA/Hibernate, MySQL  
**Frontend:** HTML5, CSS3, Vanilla JavaScript  
**Tools:** Maven, Lombok, Swagger/OpenAPI

---

## 🚀 Quick Start

### Prerequisites
- Java 25+
- Maven 3.8+
- MySQL 8.0+

### Installation
```bash
# Clone repository
git clone https://github.com/yourusername/fittrack.git
cd fittrack

# Create database
mysql -u root -p
CREATE DATABASE fitness_db;

# Configure application.properties
spring.datasource.url=jdbc:mysql://localhost:3306/fitness_db
spring.datasource.username=your_username
spring.datasource.password=your_password

# Build and run
mvn clean install
mvn spring-boot:run
```

### Access
- **App:** http://localhost:8080
- **Swagger:** http://localhost:8080/swagger-ui.html
- **API Docs:** http://localhost:8080/v3/api-docs

---

## 📚 API Endpoints

### Authentication
```http
POST /api/auth/register  # Register new user
POST /api/auth/login     # Login and get JWT token
```

### Activities
```http
POST /api/activities     # Track new activity (requires JWT)
GET  /api/activities     # Get user activities (requires JWT)
```

### Recommendations
```http
POST /api/recommendation/generate      # Generate recommendation
GET  /api/recommendation/user/{userId} # Get user recommendations
```

**Example Request:**
```bash
curl -X POST http://localhost:8080/api/auth/login \
  -H "Content-Type: application/json" \
  -d '{"email":"user@example.com","password":"password123"}'
```

---

## 🏗️ Architecture
```
Frontend (HTML/CSS/JS)
      ↓
Security Layer (JWT Filter)
      ↓
Controllers (REST API)
      ↓
Services (Business Logic)
      ↓
Repositories (Data Access)
      ↓
Database (MySQL)
```

**Entity Relationships:**
- User (1) → (N) Activities
- Activity (1) → (N) Recommendations

---

## 📁 Project Structure
```
src/main/java/com/project/fitness/
├── controller/      # REST controllers
├── dto/             # Data transfer objects
├── model/           # JPA entities
├── repository/      # Data repositories
├── service/         # Business logic
├── security/        # JWT & Spring Security
└── exception/       # Error handling

src/main/resources/
├── static/          # Frontend files
└── application.properties
```

---

## 🔒 Security

- **Password Encryption:** BCrypt hashing
- **Authentication:** JWT tokens (24-hour expiry)
- **Authorization:** Role-based access (USER/ADMIN)
- **Input Validation:** Bean Validation annotations
- **SQL Injection Prevention:** JPA parameterized queries

---

## 🔮 Future Enhancements

- [ ] Analytics dashboard with charts
- [ ] Social features (friends, leaderboards)
- [ ] Wearable device integration
- [ ] Mobile app (iOS/Android)
- [ ] Machine learning recommendations
- [ ] Redis caching
- [ ] Docker containerization

---



## 📞 Contact

**Utkarsh Tiwari ** - utkarshtiwari9369@gmail.com 
** Link:** https://github.com/utkarshtiwari93

---

⭐ **Star this repo if you find it helpful!**
