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
  
  5. defined and passed a function to format currency fields
  
  6. format date fields (release date)
  
  7. format the movie running time
  
  8. define fields for the Kaggle metadata
    
  9. format the timestamp in the ratings file
  
  10. merge the wikipedia data with the kaggle metadata on the IMDB ID and removing unwanted columns
  
  11. looked for missing kaggle data and filled it in
  
  12. renamed columns in a merged table to make them more recognizable.
  
  13. grouped the records on the ratings (number of times a movie received a specific rating)
  
  14. established a connection to the postgresSQL database and imported the newly cleaned and merged datafile (movies) into the database, first checking to see if it already exisited, and if so, replacing it with the new one.
  
  ## Assumptions
  
  1.  I'm assuming that there is a dedicated web source for the data that I can work into my automation to make this truly automated.
  As is, I was given some of the files to store and load from my local machine.  This isn't 'automated' since the data are not updated on the local machine.
  
  2.  Assuming also that the data will be in the expected format each time I access it.  If it were to change I would need to modify the code.
  
  3.  Assuming the websites where I'm getting the data are actually updating the data or I would get the same output each time.
  
  4.  Assuming the movies website continues to rate its movies in the same way with the same metrics.
  
  5.  Assuming my access to the movie data is always valid (via the password).

    
