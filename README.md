md_water_services Database Analysis
Overview
This project analyzes the md_water_services database, which contains field data related to rural and urban water access, source types, population served, and field visits by employees. It is part of a larger effort to support water access accountability, improve resource allocation, and understand the human impact of water infrastructure across towns and provinces.

Objectives
Understand employee activity by location and visits

Analyze types and accessibility of water sources

Aggregate population served by water source types

Explore queue times and usage patterns for taps and wells

Support auditors and stakeholders with structured insights from data

Features
Aggregated statistics on:

Employee performance (top and bottom performers)

Water source distribution and type usage

Queue time patterns by day and hour

Pivot table insights for time-based usage analysis

Clean SQL scripts for:

Counting, grouping, and filtering by town, location, and source

Calculating running averages and annual rate of change (ARC)

Formatting dates and trimming text

ERD (Entity Relationship Diagram) guidance for database structure

Technologies Used
MySQL / MariaDB

SQL Window Functions

SQL Aggregation, Grouping, and Filtering

SQL Pivot and CASE Statements (for time block analysis)

Visualization Tools (MySQL Workbench / dbdiagram.io for ERD)

Schema Overview
The database includes the following core tables:

employee – stores employee info and location

visits – logs visits to water sources by employees

location – details towns, provinces, and types of water access

water_source – records source types and people served

Sample Queries
sql
Copy
Edit
-- Top 3 employees by visits
SELECT assigned_employee_id, COUNT(location_id) AS location_count
FROM md_water_services.visits
GROUP BY assigned_employee_id
ORDER BY location_count DESC
LIMIT 3;
sql
Copy
Edit
-- Population served by water taps
SELECT SUM(number_of_people_served) AS tap_population
FROM water_source
WHERE type_of_water_source LIKE '%tap%';
How to Use
Clone or download the project.

Connect to your local or cloud MySQL server.

Import the database if needed.

Run the SQL scripts in your preferred SQL client.

Use pivot tables and visualizations to enhance insight sharing.

ERD
For a better understanding of table relationships, please refer to the ERD included in the /docs folder or generate one using MySQL Workbench.

Author
Dinah Buyeke Masanda
Fourth-year Bachelor of Commerce (Marketing), Cooperative University of Kenya
Passionate about using data to drive social good.
