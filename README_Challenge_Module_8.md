# Challenge Module 8 Movies Database-ETL
Practice with Extract, Transform, and Load (ETL)

In this challenge I am creating an automated process to extract data from disparate sources, transform it by cleaning data, merging fields (columns), changing formats, and merging tables, and then loading it into a SQL (postgreSQL) database.

I wrote a function in a Jupyter Notebook that takes in three arguments (data sources); a json file of movie data from wikipedia, movie metadata in csv format from Kaggle, and a file with movie ratings data, also in csv and also from Kaggle.  

First I imported my dependencies (json, pandas, numpy, re, sqlalchemy, a config file with my postreSQL password, and time).

Then I did some data cleaning to remove redundant or sparce fields (such as language) and then normalized column names.

Then I wrote the function which works by: 
  1. opening the datafiles (reading in the json and csv files)
  
  2. dropping duplicate records based on the IMDB ID (using a try/except routine)
 
  3. defining the output list of columns I wanted
  
  4. use regular expressions formating the numeric data (like budget and box office fields)
  
  5. defined a and pass a function to format currency fields
  
  6. format date fields (release date)
  
  7. format the movie running time
  
  8. define fields for the Kaggle metadata
    
  9. format the timestamp in the ratings file
  
  10. merge the wikipedia data with the kaggle metadata on the IMDB ID and removing unwanted columns
  
  11. looked for missing kaggle data and filled it in
  
  12. renamed columns in a merged table to make them more recognizable.
  
  13. grouped the records on the ratings (number of times a movie received a specific rating)
  
  14. established a connection to the postgresSQL database and imported the newly cleaned and merged datafile (movies) into the database, first checking to see if it already exisited, and if so, replacing it with the new one.
  
  

    
