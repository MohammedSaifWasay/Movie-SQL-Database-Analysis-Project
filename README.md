# 🎬 Movie Database Analysis Project

This project explores and analyzes a relational database containing comprehensive movie industry data, including movies, actors, box office revenue, and production companies. The database schema is built using SQLite and includes multiple related tables.

## 🗂️ Dataset Overview

The database (`module11-1.db`) consists of the following tables:

- **`movies_1`**: Contains information related to various movies.
- **`ActorInfo`**: Includes data about actors involved in movies.
- **`BoxOffice`**: Captures box office performance metrics.
- **`Movie`**: A central table describing movie metadata.
- **`ProductionCompany`**: Lists production companies associated with films.

## 🧾 Entity Relationship Diagram (ERD)

The diagram below shows how the tables are connected:

![Entity Relationship Diagram](movie_database_erd.png)

## 🧪 Objectives

- Understand database schema and relationships between tables.
- Perform SQL queries to:
  - Retrieve and join data across tables.
  - Summarize actor and box office information.
  - Analyze production company involvement.
- Gain hands-on experience with database exploration using SQLite.

## 🛠️ Technologies Used

- **SQLite** — For relational database management  
- **Python (pandas, sqlite3)** — For database interaction and analysis  
- **Jupyter Notebook** — For querying and visualizing results

## 📊 Sample Queries

```sql
-- Retrieve top 10 highest-grossing movies
SELECT m.Title, b.WorldwideGross
FROM Movie m
JOIN BoxOffice b ON m.MovieID = b.MovieID
ORDER BY b.WorldwideGross DESC
LIMIT 10;
-- List actors who have worked with more than 3 production companies
SELECT a.ActorName, COUNT(DISTINCT p.CompanyName) as NumCompanies
FROM ActorInfo a
JOIN Movie m ON a.MovieID = m.MovieID
JOIN ProductionCompany p ON m.CompanyID = p.CompanyID
GROUP BY a.ActorName
HAVING COUNT(DISTINCT p.CompanyName) > 3;
---
🚀 Getting Started
Clone this repository:
🔗https://github.com/yourusername/movie-db-analysis.git
cd movie-db-analysis
Launch the SQLite viewer or use the included Jupyter Notebook to run queries.

Explore, analyze, and visualize!
## 🧠 Author  
**Mohammed Saif Wasay**  
*Data Analytics Graduate — Northeastern University*  
*Machine Learning Enthusiast | Passionate about turning data into insights*  
🔗 [Connect with me on LinkedIn](https://www.linkedin.com/in/mohammed-saif-wasay-4b3b64199/)
