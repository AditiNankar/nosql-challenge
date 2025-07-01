# 🧪 NoSQL Challenge – UK Food Hygiene Ratings

## 📌 Overview

Welcome to the **UK Food Hygiene Ratings Analysis** project!  
In this challenge, we work with food hygiene inspection data from the UK’s Food Standards Agency using a **NoSQL database (MongoDB)**. The goal is to evaluate and prepare insights for a food magazine called _Eat Safe, Love_.

This project involves:
- Importing and preparing MongoDB collections from JSON
- Performing updates and cleaning the dataset
- Running analysis using PyMongo and Pandas
- Delivering answers through queries and DataFrames

---

## 🧰 Technologies Used

- Python
- MongoDB
- PyMongo
- Pandas
- Pretty Print
- Jupyter Notebook

---

## 🔄 Part 1: MongoDB Setup

# 📂 Data Import

MongoDB shell command used to import:
mongoimport --db uk_food --collection establishments --drop --jsonArray --file Resources/establishments.json

✅ Tasks Completed
	•	Imported establishments.json into a MongoDB database called uk_food
	•	Verified data import and structure using:
	•	list_database_names()
	•	list_collection_names()
	•	find_one() with pprint
	•	Assigned establishments collection to a working variable for reuse
---
# ✏️ Part 2: Data Cleaning and Updates

✅ Modifications Performed
	•	Added a new restaurant: “Penang Flavours” in Greenwich (not yet rated)
	•	Updated BusinessTypeID for the new restaurant
	•	Removed all establishments within the “Dover” Local Authority
	•	Cleaned numeric fields by converting:
	•	latitude and longitude to float
	•	RatingValue to int (ignoring invalid entries like "Pass")
---
# 🔍 Part 3: Exploratory Analysis

All analysis was completed using PyMongo queries and converted into Pandas DataFrames.

📊 Insights Discovered

1. Establishments with a Hygiene Score of 20
	•	Number of documents: 41
	•	Returned the first document and converted the result to a DataFrame

2. London Establishments with RatingValue ≥ 4
	•	Used $regex to search for "London" in long-form LocalAuthorityName
	•	Number of documents: 33
	•	Returned first document and converted to DataFrame

3. Top 5 Nearby Establishments with a RatingValue of 5
	•	Found within 0.01 degrees of “Penang Flavours”
	•	Sorted by lowest hygiene score
	•	Returned 5 documents and converted to DataFrame

4. Local Authorities with Most Hygiene Score 0
	•	Used MongoDB aggregation pipeline with $match, $group, and $sort
---
### 📤 Output

All queries were validated with:
	•	count_documents() for volume checks
	•	pprint() for a sample result
	•	Pandas DataFrames for tabular viewing and export (if needed)

🧑‍💻 Author

Aditi Nankar
Data Enthusiast | MongoDB Analyst
