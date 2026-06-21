# Carbon-Footprints-available-platform
My first AI project.
Carbon Footprint Awareness Platform
A Spring Boot web application that helps users log daily transportation, electricity, food, and waste habits, then calculates carbon emissions, visualizes progress, and provides personalized reduction suggestions.
Features
Daily activity input for transport, electricity, diet, waste, and recycling
Carbon emission calculation by category and total kg CO2e
Bootstrap dashboard with summary metrics, history table, and Chart.js visualizations
Personalized recommendations based on the latest high-impact category
MySQL persistence with user history and progress tracking
Tech Stack
Backend: Java 17, Spring Boot, Spring Web, Spring Data JPA
Frontend: HTML, CSS, JavaScript, Bootstrap
Database: MySQL
Charts: Chart.js
Run Locally
Start MySQL:
docker compose up -d
Run the app:
mvn spring-boot:run
Open:
http://localhost:8080
For a quick no-MySQL demo, run with the dev profile:
mvn spring-boot:run -Dspring-boot.run.profiles=dev
Configuration
The app reads database settings from environment variables:
DATABASE_URL=jdbc:mysql://localhost:3306/carbon_footprint?createDatabaseIfNotExist=true&useSSL=false&allowPublicKeyRetrieval=true&serverTimezone=UTC
DATABASE_USERNAME=root
DATABASE_PASSWORD=password
PORT=8080
API
GET /api/entries?userName=demo
GET /api/entries/summary?userName=demo
POST /api/entries
DELETE /api/entries/{id}
Example POST /api/entries body:
{
  "userName": "demo",
  "activityDate": "2026-06-21",
  "transportMode": "CAR",
  "transportKm": 12,
  "electricityKwh": 4.5,
  "dietType": "MIXED",
  "meals": 3,
  "wasteKg": 1.2,
  "recycledKg": 0.4
}
