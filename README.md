# Data Modeling with Postgres

## Purpose
This project supports a music streaming startup, Sparkify, by developing an ETL pipeline that creates a star schema database.  This structure optimizes database performance which facilitates query development and performance for analysts.  

## Database Design
The database contains the following tables:

Fact Table:  
songplays - log information associated with song plays.  Determined through pages tagged to "Next Song."
 - columns: songplay_id, start_time, user_id, level, song_id, artist_id, session_id, location, user_agent
 
 Dimension Tables:
 users - user information
  - columns: user_id, first_name, last_name, gender, level
 
 songs - song information
  - columns: song_id, title, artist_id, year, duration
 
 artists - artist information
  - columns: artist_id, name, location, latitude, longitude
 
 time - timestamp of when the song was played 
  - columns: start_time, hour, day, week, month, year, weekday
  
 This design is ideal for Sparkify because it is in denormalized form.  Denormalized form has first passed through first, second, and third normal forms to preseve data integrity and is then denormalized to minimize the number of joins needed to process a query.  This star schema also allows for quicker aggregations and simplified queries.

## File Descriptions
- data folder: contains all .json files used in the script
- create_tables.py: production script that creates database tables
- etl.pynb: development exploration notebook for queries later used in ETL production 
- etl.py: production script for ETL pipeline
- sql_queries.py: has SQL create table and insert record statements
- test.ipynb: series of tests to ensure all code runs as expected

## Instructions to Run
1. Run create_tables.py to create database and tables
2. Run test.ipynb to confirm all tables were created as expected
3. Run etl.py to insert records into database tables
4. Run test.ipynb to confirm all records were inserted as expected
