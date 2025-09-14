# SQL Querries and Results for CFPB Consumer Complaints Dataset

This file contains key SQL queries I ran on the CFPB Consumer Complaints dataset (>10M rows)
---
## Query 1. Count number of rows in table Complaint
SELECT COUNT (*) AS total_rows
FROM complaints

Result: 
10,935,662

This matches data size, conforming that data was imported successfully.
