# MAY-7-github-actions

![Actions App CI](https://github.com/gurban200OK/MAY-7-github-actions/actions/workflows/ci.yml/badge.svg)
![Deploy to Render](https://github.com/gurban200OK/MAY-7-github-actions/actions/workflows/deploy.yml/badge.svg)

A Spring Boot REST API backed by PostgreSQL, with a fully automated CI/CD pipeline powered by GitHub Actions and hosted on Render.

---

## Live Application

**Base URL:** `https://devops-app-z1rm.onrender.com`

> Free-tier Render services spin down after inactivity. The first request after idle time may take **30–90 seconds** to respond.

Quick test:

```bash
curl -s https://devops-app-z1rm.onrender.com/actuator/health | jq .
```

---

## API Endpoints

| Method | Path | Description |
|--------|------|-------------|
| GET | `/actuator/health` | Application health status |

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Language | Java 21 |
| Framework | Spring Boot 4.0 |
| Database (local) | H2 (in-memory) |
| Database (prod) | PostgreSQL 18 on Render |
| Build tool | Maven |
| Containerization | Docker (multi-stage build) |
| CI/CD | GitHub Actions |
| Hosting | Render (free tier) |

---

## CI/CD Pipeline

```
Push to main
    │
    ▼
Actions App CI
├── Checkout code
├── Set up JDK 17
├── Cache Maven dependencies
└── Build and test (mvn clean verify)
    │
    ▼ (only on success)
Deploy to Render
├── Trigger Render deploy hook
├── Wait for rebuild and restart
├── Health check → /actuator/health
└── Verify {"status": "UP"}
```

---

## Spring Profiles

| Profile | Database | Usage |
|---------|----------|-------|
| `default` | H2 in-memory | Local development |
| `prod` | PostgreSQL on Render | Production |

---

## Running Locally

### Prerequisites
- Java 17+
- Maven 3.9+

### Steps

```bash
git clone https://github.com/gurban200OK/MAY-7-github-actions.git
cd MAY-7-github-actions
mvn spring-boot:run
```

App starts on `http://localhost:8080`.

### With Docker

```bash
docker build -t may7-app:local .
docker run -p 8080:8080 may7-app:local
```

---

## Project Structure

```
src/
├── main/
│   ├── java/com/example/actions/
│   │   ├── controller/
│   │   ├── model/
│   │   ├── repository/
│   │   └── service/
│   └── resources/
│       ├── application.properties
│       └── application-prod.properties
├── test/
.github/
└── workflows/
    ├── ci.yml
    └── deploy.yml
Dockerfile
```