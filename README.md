# Room Link - A Full-Stack Room Rental Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Java](https://img.shields.io/badge/Java-17+-orange.svg?logo=java)](https://www.oracle.com/java/technologies/downloads/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.x-green.svg?logo=spring)](https://spring.io/projects/spring-boot)
[![React](https://img.shields.io/badge/React-18-61DAFB.svg?logo=react)](https://react.dev/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14-336791.svg?logo=postgresql)](https://www.postgresql.org/)
[![Docker](https://img.shields.io/badge/Docker-Supported-2496ED.svg?logo=docker)](https://www.docker.com/)

**Room Link** is a modern, broker-free web application designed to directly connect room owners and renters in Pune. It provides a seamless, map-based interface to simplify the rental search process, backed by a robust and secure Spring Boot API.

---

## 🖼️ Platform Demo

### Homepage & Search Interface

![Homepage Demo](https://github.com/sanikapawar74/Room-Link/blob/main/img-1.png)
*Clean, intuitive homepage with advanced search filters and location-based browsing*

### Interactive Map View

![Map View Demo](https://github.com/sanikapawar74/Room-Link/blob/main/img-2.png)
*Interactive map interface showing room listings with location markers and detailed popups*

### Room Listing Details

![Listing Details Demo](https://raw.githubusercontent.com/sanikapawar74/Room-Link/main/docs/demo/listing-details-demo.png)
*Comprehensive room listing page with image gallery, amenities, and contact information*

### User Dashboard

![User Dashboard Demo](https://raw.githubusercontent.com/sanikapawar74/Room-Link/main/docs/demo/user-dashboard-demo.png)
*User-friendly dashboard for managing listings, favorites, and account settings*



---

## Table of Contents

- [The Problem &amp; Solution](#the-problem--solution)
- [Platform Demo](#️-platform-demo)
- [Key Features](#key-features)
- [Technical Architecture](#technical-architecture)
- [Tech Stack](#tech-stack)
- [Getting Started](#getting-started)
- [API Endpoints](#api-endpoints)
- [Configuration](#configuration)
- [Project Structure](#project-structure)
- [Development Workflow](#development-workflow)
- [Testing](#testing)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)

---

## 🎯 The Problem & Solution

### The Problem

In many Indian cities, particularly Pune, the rental market is dominated by brokers who:

- Charge hefty commission fees (typically 1-2 months rent)
- Create information asymmetry between owners and renters
- Add unnecessary complexity to the rental process
- Often provide outdated or inaccurate property information

### Our Solution

**Room Link** eliminates the middleman by providing:

- **Direct Communication**: Connect property owners directly with potential renters
- **Zero Commission**: No hidden fees or broker charges
- **Real-time Updates**: Live property availability and accurate information
- **Transparent Process**: Clear pricing and property details upfront
- **Geographic Intelligence**: Location-based search with interactive maps

---

## ✨ Key Features

### 🔐 **Authentication & Security**

- Secure JWT-based authentication system
- Password encryption and validation
- Protected routes and API endpoints
- User session management

### 🏠 **Property Management**

- **Complete CRUD Operations**: Create, read, update, and delete room listings
- **Rich Media Support**: Multiple image uploads with compression and optimization
- **Detailed Property Information**: Comprehensive forms for property specifications
- **Real-time Availability**: Instant updates on property status

### 🗺️ **Advanced Search & Discovery**

- **Interactive Map Interface**: Powered by React Leaflet with custom markers
- **Location-based Filtering**: Search by specific areas, neighborhoods, or proximity
- **Advanced Filters**: Price range, property type, amenities, availability date
- **Saved Searches**: Bookmark favorite search criteria for quick access

### 🎨 **Modern User Experience**

- **Responsive Design**: Seamless experience across desktop, tablet, and mobile
- **Material-UI Components**: Consistent and professional interface design
- **Dark/Light Theme Support**: User preference-based theme switching
- **Progressive Web App**: Fast loading with offline capabilities

### 📊 **Analytics & Insights**

- **User Dashboard**: Personal analytics for property owners
- **Listing Performance**: View metrics and engagement statistics
- **Market Trends**: Insights into rental market dynamics (coming soon)

---

## 🏗️ Technical Architecture

This project follows a **modern three-tier architecture** with clear separation of concerns:

![Architecture Diagram](https://raw.githubusercontent.com/sanikapawar74/Room-Link/main/docs/architecture.png)

### Frontend Layer (Presentation Tier)

- **React 18** with functional components and hooks
- **Single Page Application (SPA)** with client-side routing
- **State Management** using React Context and custom hooks
- **HTTP Client** with Axios for API communication

### Backend Layer (Business Logic Tier)

- **Spring Boot 3** with RESTful API design
- **Spring Security** with JWT for stateless authentication
- **Service Layer** for business logic separation
- **Repository Pattern** with Spring Data JPA

### Data Layer (Persistence Tier)

- **PostgreSQL** for relational data storage
- **Hibernate/JPA** for object-relational mapping
- **Connection Pooling** for optimal database performance
- **Migration Support** with Flyway (optional)

---

## 🛠️ Tech Stack

| Category                     | Technology / Library                                                       |
| :--------------------------- | :------------------------------------------------------------------------- |
| **Backend Framework**  | `Java 17`, `Spring Boot 3.x`, `Spring Security`, `Spring Data JPA` |
| **Frontend Framework** | `React 18`, `Vite`, `TypeScript` (optional), `React Router DOM`    |
| **UI/UX Libraries**    | `Material-UI (MUI)`, `React Leaflet`, `Axios`, `React Hook Form`   |
| **Database**           | `PostgreSQL 14+`, `Hibernate ORM`                                      |
| **Authentication**     | `JSON Web Tokens (JWT)`, `BCrypt Password Encoding`                    |
| **Development Tools**  | `Docker & Docker Compose`, `Maven`, `ESLint`, `Prettier`           |
| **Testing Frameworks** | `JUnit 5`, `Mockito`, `TestContainers` (Backend)                     |
| **Deployment**         | `Docker`, `Nginx` (reverse proxy), `PM2` (process management)        |

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your development machine:

- **Java Development Kit (JDK) 17+** - [Download Eclipse Temurin](https://adoptium.net/)
- **Node.js 18+** and **npm** - [Download Node.js](https://nodejs.org/)
- **Docker** and **Docker Compose** - [Install Docker](https://docs.docker.com/get-docker/)
- **Git** - [Install Git](https://git-scm.com/downloads)

### Quick Start Guide

1. **Clone the Repository**

   ```bash
   git clone https://github.com/sanikapawar74/Room-Link.git
   cd Room-Link
   ```
2. **Environment Configuration**

   Create a `.env` file in the `backend` directory:

   ```bash
   cd backend
   cp .env.example .env
   ```

   Update the `.env` file with your configuration:

   ```env
   # Database Configuration
   DB_URL=jdbc:postgresql://localhost:5432/roomlinkdb
   DB_USER=roomlink_user
   DB_PASSWORD=secure_password_123

   # JWT Configuration
   JWT_SECRET=your_super_secure_jwt_secret_key_here_min_32_chars
   JWT_EXPIRATION=86400000

   # File Upload Configuration
   UPLOAD_PATH=./uploads
   MAX_FILE_SIZE=10MB

   # CORS Configuration (for production)
   CORS_ALLOWED_ORIGINS=http://localhost:3000,https://yourdomain.com
   ```
3. **Database Setup**

   ```bash
   # Start PostgreSQL container
   docker-compose up -d postgresql

   # Verify database is running
   docker-compose ps
   ```
4. **Backend Setup**

   ```bash
   cd backend

   # Install dependencies and run tests
   ./mvnw clean install

   # Start the Spring Boot application
   ./mvnw spring-boot:run
   ```

   The backend API will be available at `http://localhost:8080`
5. **Frontend Setup**

   Open a new terminal:

   ```bash
   cd frontend

   # Install dependencies
   npm install

   # Start development server
   npm run dev
   ```

   The React application will be available at `http://localhost:5173`

### 🔧 Development Setup Verification

1. **Check Backend Health**: Visit `http://localhost:8080/actuator/health`
2. **Check Frontend**: Visit `http://localhost:5173`
3. **Test API Connection**: Try registering a new user through the frontend

---

## 📡 API Endpoints

### Authentication Endpoints

| Method   | Endpoint               | Description         | Request Body                           |
| -------- | ---------------------- | ------------------- | -------------------------------------- |
| `POST` | `/api/auth/register` | Register new user   | `{username, email, password, phone}` |
| `POST` | `/api/auth/login`    | User authentication | `{email, password}`                  |
| `POST` | `/api/auth/refresh`  | Refresh JWT token   | `{refreshToken}`                     |
| `POST` | `/api/auth/logout`   | User logout         | -                                      |

### Listing Management

| Method     | Endpoint                      | Description                  | Auth Required |
| ---------- | ----------------------------- | ---------------------------- | ------------- |
| `GET`    | `/api/listings`             | Get all public listings      | ❌            |
| `GET`    | `/api/listings/{id}`        | Get specific listing         | ❌            |
| `POST`   | `/api/listings`             | Create new listing           | ✅            |
| `PUT`    | `/api/listings/{id}`        | Update listing               | ✅            |
| `DELETE` | `/api/listings/{id}`        | Delete listing               | ✅            |
| `GET`    | `/api/listings/my-listings` | Get user's listings          | ✅            |
| `GET`    | `/api/listings/search`      | Search listings with filters | ❌            |

### File Management

| Method     | Endpoint                   | Description           | Auth Required |
| ---------- | -------------------------- | --------------------- | ------------- |
| `POST`   | `/api/upload/image`      | Upload listing image  | ✅            |
| `DELETE` | `/api/upload/image/{id}` | Delete uploaded image | ✅            |
| `GET`    | `/api/files/{filename}`  | Serve uploaded files  | ❌            |

### User Management

| Method  | Endpoint                       | Description         | Auth Required |
| ------- | ------------------------------ | ------------------- | ------------- |
| `GET` | `/api/users/profile`         | Get user profile    | ✅            |
| `PUT` | `/api/users/profile`         | Update user profile | ✅            |
| `PUT` | `/api/users/change-password` | Change password     | ✅            |

---

## ⚙️ Configuration

### Backend Configuration

**Application Properties** (`backend/src/main/resources/application.yml`):

```yaml
server:
  port: 8080
  servlet:
    context-path: /api

spring:
  datasource:
    url: ${DB_URL}
    username: ${DB_USER}
    password: ${DB_PASSWORD}
  
  jpa:
    hibernate:
      ddl-auto: update
    show-sql: false
    properties:
      hibernate:
        format_sql: true

  servlet:
    multipart:
      max-file-size: 10MB
      max-request-size: 50MB

jwt:
  secret: ${JWT_SECRET}
  expiration: ${JWT_EXPIRATION:86400000}

app:
  upload:
    directory: ${UPLOAD_PATH:./uploads}
```

### Frontend Configuration

**Vite Configuration** (`frontend/vite.config.js`):

```javascript
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

export default defineConfig({
  plugins: [react()],
  server: {
    port: 5173,
    proxy: {
      '/api': {
        target: 'http://localhost:8080',
        changeOrigin: true,
        secure: false
      }
    }
  },
  build: {
    outDir: 'dist',
    assetsDir: 'assets'
  }
})
```

---

## 📁 Project Structure

```
Room-Link/
├── 📂 backend/                    # Spring Boot Backend
│   ├── 📂 src/main/java/com/roomlink/
│   │   ├── 📂 config/             # Configuration classes
│   │   ├── 📂 controller/         # REST Controllers
│   │   ├── 📂 dto/                # Data Transfer Objects
│   │   ├── 📂 entity/             # JPA Entities
│   │   ├── 📂 repository/         # Data Repositories
│   │   ├── 📂 service/            # Business Logic
│   │   ├── 📂 security/           # Security Configuration
│   │   └── 📂 util/               # Utility Classes
│   ├── 📂 src/main/resources/
│   │   ├── application.yml        # Application Configuration
│   │   └── 📂 static/             # Static Resources
│   └── 📂 src/test/               # Test Classes
│
├── 📂 frontend/                   # React Frontend
│   ├── 📂 public/                 # Public Assets
│   ├── 📂 src/
│   │   ├── 📂 components/         # Reusable Components
│   │   ├── 📂 pages/              # Page Components
│   │   ├── 📂 hooks/              # Custom React Hooks
│   │   ├── 📂 services/           # API Services
│   │   ├── 📂 utils/              # Utility Functions
│   │   ├── 📂 context/            # React Context
│   │   └── 📂 assets/             # Images, Styles
│   ├── package.json
│   └── vite.config.js
│
├── 📂 docs/                       # Documentation
│   ├── 📂 demo/                   # Demo Screenshots
│   ├── architecture.png
│   └── setup-guide.md
│
├── docker-compose.yml             # Docker Configuration
├── .gitignore
└── README.md
```

---

## 🔄 Development Workflow

### Setting up Development Environment

1. **Fork and Clone**

   ```bash
   git clone https://github.com/yourusername/Room-Link.git
   cd Room-Link
   git remote add upstream https://github.com/sanikapawar74/Room-Link.git
   ```
2. **Create Feature Branch**

   ```bash
   git checkout -b feature/your-feature-name
   ```
3. **Make Changes and Test**

   ```bash
   # Backend tests
   cd backend && ./mvnw test

   # Frontend tests (if applicable)
   cd frontend && npm test
   ```
4. **Commit and Push**

   ```bash
   git add .
   git commit -m "feat: add your feature description"
   git push origin feature/your-feature-name
   ```

### Code Quality Standards

- **Backend**: Follow Spring Boot best practices and Java coding conventions
- **Frontend**: Use ESLint and Prettier for code formatting
- **Git**: Use conventional commit messages
- **Testing**: Maintain test coverage above 80%

---

## 🧪 Testing

### Backend Testing

```bash
cd backend

# Run all tests
./mvnw test

# Run specific test class
./mvnw test -Dtest=UserServiceTest

# Generate test coverage report
./mvnw jacoco:report
```

### Frontend Testing

```bash
cd frontend

# Run unit tests
npm test

# Run tests with coverage
npm run test:coverage

# Run end-to-end tests
npm run test:e2e
```

---

## 🚀 Deployment

### Production Build

1. **Backend Production Build**

   ```bash
   cd backend
   ./mvnw clean package -Pprod
   ```
2. **Frontend Production Build**

   ```bash
   cd frontend
   npm run build
   ```

### Docker Deployment

```bash
# Build and start all services
docker-compose up --build -d

# Check service status
docker-compose ps

# View logs
docker-compose logs -f
```

### Environment-specific Configurations

- **Development**: Use local PostgreSQL and hot-reload
- **Staging**: Docker containers with test data
- **Production**: Optimized builds with environment variables

---

## 🤝 Contributing

We welcome contributions from the community! Here's how you can help:

### Ways to Contribute

1. **🐛 Bug Reports**: Found a bug? Open an issue with detailed steps to reproduce
2. **💡 Feature Requests**: Have an idea? Share it in the issues section
3. **📖 Documentation**: Help improve our docs and README
4. **🔧 Code Contributions**: Submit pull requests for bug fixes or new features

### Contribution Guidelines

1. **Check existing issues** before creating new ones
2. **Follow the code style** and existing patterns
3. **Write tests** for new features
4. **Update documentation** as needed
5. **Keep PRs focused** - one feature/fix per PR

### Development Setup for Contributors

1. Fork the repository
2. Follow the [Getting Started](#-getting-started) guide
3. Create a feature branch
4. Make your changes
5. Test thoroughly
6. Submit a pull request

---

## 📜 License

This project is licensed under the **MIT License** - see the [LICENSE](LICENSE) file for details.

### What this means:

- ✅ Commercial use allowed
- ✅ Modification allowed
- ✅ Distribution allowed
- ✅ Private use allowed
- ❌ No liability or warranty

---

## 🙏 Acknowledgments

- **Spring Boot Team** for the excellent framework
- **React Team** for the powerful frontend library
- **Material-UI** for the beautiful component library
- **Leaflet** for the interactive mapping solution
- **PostgreSQL** for the robust database system

---

## 📞 Support & Contact

- **Issues**: [GitHub Issues](https://github.com/sanikapawar74/Room-Link/issues)
- **Discussions**: [GitHub Discussions](https://github.com/sanikapawar74/Room-Link/discussions)
- **Email**: your-email@example.com

---

<div align="center">

**Made with ❤️ for the Pune rental community**

[⭐ Star this repo](https://github.com/sanikapawar74/Room-Link) | [🐛 Report Bug](https://github.com/sanikapawar74/Room-Link/issues) | [✨ Request Feature](https://github.com/sanikapawar74/Room-Link/issues)

</div>
