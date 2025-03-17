# nosql-challenge
Module 12 Challenge: I've been contracted by the editors of magazine, Eat Safe, Love, to evaluate some of the ratings data in order to help their journalists and food critics decide where to focus future articles.
# Code Source
Jupyter Notebook (NoSQL_analysis_starter.ipynb and NoSQL_setup_starter.ipynb)  
Resources (establishments.json)
# Part 1: Database and Jupyter Notebook Set Up
1. Imported the data in the establishments.json file from Terminal. Named the database uk_food and collection establishments.  
2. Imported the PyMongo and Pretty Print(pprint) libraries.  
3. Created an instance of the Mongo Client.  
4. Confirmed I've created the database and loaded the data properly:  
- Listed the databases in MongoDB. Confirmed uk_food is listed.  
- Listed the collection(s) in the database to ensure establishments in there.  
- Found and displayed one document in the establishments collection using find_one and display with pprint.  
5. Assigned the establishments collection to a variable to prepare the collection for use.
# Part 2: Update Database
The magazine editors have some requested modifications for the database before you can perform any queries or analysis for them. Made the below changes to the establishments collection:  
1. Added a new halal restaurant in Greenwich information to the database.  
2. Found the BusinessTypeID for "Restaurant/Cafe/Canteen" and returned on the BusinessTypeID and BusinessType fields.  
3. Updated the new restaurant with the BusinessTypeID.  
4. Checked how many documents contain the Dover Local Authority. Then removed any establishments within the Dover Local Authority from the database, and checked the number of documents to ensure they deleted.  
5. Some of the number values are stored as strings, when they should be stored as numbers.  
- Used update_many to convert latitude and longitude to decimal numbers.  
- Used update_many to convert RatingValue to integer numbers.
# Part 3: Exploratory Analysis
Eat Safe, Love has specific questions they want you to answer, which will help them find the locations they wish to visit and avoid.  
Used the below questions to explore the database, and find the answers, so you can provide them to the magazine editors:  
- Used count_documents to display the number of documents contained in the result.  
- Displayed the first document in the results using pprint.  
- Converted the result to a Pandas DataFrame, print the number of rows in the DataFrame, and displayed the first 10 rows.  
1. Which establishments have a hygiene score equal to 20? Answer found in jupyter notebook (NoSQL_analysis_starter).  
2. Which establishments in London have a RatingValue greater than or equal to 4? Answer found in jupyter notebook (NoSQL_analysis_starter).  
3. What are the top 5 establishments with a RatingValue of 5, sorted by lowest hygiene score, nearest to the new restaurant added, "Penang Flavours"? Answer found in jupyter notebook (NoSQL_analysis_starter).  
4. How many establishments in each Local Authority area have a hygiene score of 0? Sort the results from highest to lowest, and print out the top ten local authority areas. Answer found in jupyter notebook (NoSQL_analysis_starter).
# References:
UK Food Standards Agency (2022). UK food hygiene rating data API. https://ratings.food.gov.uk/open-data/en-GB. Contains public sector information licensed under the Open Government Licence v3.0. Accessed Sept 9, 2022 and Sept 12, 2022 with the establishment settings as follows: longitude=51.5072, latitude=-0.1276, maxdistancelimit=4567, pagesize=10000, sortoptionkey=distance, pagenumber=(1,2,3,4,5,6,7,8).  
Used google for UpdateMany and pipeline order, accessed March 2025.