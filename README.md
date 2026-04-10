# 🎵 AKATSUKI Music Store Database

## 📌 Project Overview
The **AKATSUKI Music Store** project is a relational database system designed to simulate a digital music store.  
It manages data related to artists, albums, tracks, customers, employees, invoices, and playlists.

This project demonstrates:
- Database design (ER modeling)
- SQL queries for business insights
- Data analysis on customer behavior and sales

---

## 🧠 Objectives
- Track music sales and customer purchases
- Analyze revenue across countries and cities
- Identify top customers and popular genres
- Support business decision-making using SQL

---

## 🗂️ Database Schema
The project includes the following tables:

- Genre
- MediaType
- Employee
- Customer
- Artist
- Album
- Track
- Invoice
- InvoiceLine
- Playlist
- PlaylistTrack

---

## 🔗 ER Diagram
![ER Diagram](ER_Diagram.png)

---

## 📊 Key SQL Analysis

### 1. Senior Most Employee
```sql
SELECT * FROM Employee 
ORDER BY hire_date 
LIMIT 1;
```

### 2. Countries with Most Invoices
```sql
SELECT billing_country, COUNT(*) AS total_invoices
FROM Invoice
GROUP BY billing_country
ORDER BY total_invoices DESC;
```

### 3. Top 3 Invoice Totals
```sql
SELECT total FROM invoice 
ORDER BY total DESC 
LIMIT 3;
```

### 4. City with Highest Revenue
```sql
SELECT billing_city, SUM(total) AS revenue
FROM invoice 
GROUP BY billing_city
ORDER BY revenue DESC
LIMIT 1;
```

### 5. Best Customer
```sql
SELECT c.customer_id, c.first_name, c.last_name, 
SUM(i.total) AS Total_Spent 
FROM customer c
JOIN invoice i ON c.customer_id = i.customer_id
GROUP BY c.customer_id
ORDER BY Total_Spent DESC
LIMIT 1;
```

---

## 📁 Project Structure
```
AKATSUKI-Music-Store/
│── sql/
│   ├── queries.sql
│── data/
│   ├── playlist_track.csv
│── assets/
│   ├── ER_Diagram.png
│── docs/
│   ├── Project_Presentation.pdf
│── README.md
```

---

## ⚙️ Setup Instructions

1. Install MySQL
2. Create database:
```sql
CREATE DATABASE AKATSUKI_MUSIC_STORE;
```

3. Run schema file
4. Import CSV data
5. Execute queries

---

## 📽️ Presentation
📄 [View Project PPT](docs/Project_Presentation.pdf)

---

## 🚀 Features
- Fully normalized database
- Real-world business queries
- Advanced SQL (JOIN, GROUP BY, RANK)
- Data-driven insights

---

## 👨‍💻 Contributors
- Aditya Kumar Lotti
- Satyanjani Gubbala
- Thejasri Thallapalli

---

## ⭐ If you like this project
Give it a star ⭐ on GitHub!
