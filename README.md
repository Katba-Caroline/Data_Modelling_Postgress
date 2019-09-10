# Project Description
A startup called Sparkify wants to analyze the data they've been collecting on songs and user activity on their new music streaming app. The analytics team is particularly interested in understanding what songs users are listening to. Currently, they don't have an easy way to query their data, which resides in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.


## Sparkify would like a Data Engineer to create a Postgres database with tables designed to optimize queries on song play analysis.
    - Model the Data Using Postgress
    - Create a database Schema
    - Create an ETL Pipeline (in python)
    - Test the database and ETL pipeline against queries from the Sparkify Analytics team.    


# Schema
Given that Sparkify wants to analyze their users' daily activity and delve into song recommendations, We would recommend a STAR schema as the most efficient and appropriate approach.

## reasons for using a relational database here:
 - The data is already structured.
 - The data volume is still relatively small and therefore does not require big data solutions.
 - As data increases in its current state, it becomes very difficult to query especially when processing JSON files. 
 - Using SQL would be most appropriate to answer business questions on the fly. 
 - SQL will allow us to use JOINS and build simple ERD models designed to answer business questions faster. 
 
# shema design

*Fact Table*: songplays: attributes referencing to the dimension tables.
*Dimension Tables*: users, songs, artists and time table.

## Insert Picture of star schema here


# Steps taken to create the ETL Script

1. Wrote DROP, CREATE and INSERT query statements in sql_queries.py

2. Run  in console 
    python create_tables.py
    
3. Used test.ipynb Jupyter Notebook to interactively verify that all tables were created correctly.

4. Completed etl.ipynb Notebook to create the blueprint of the pipeline to process and insert all data into the tables.

5. Wrote etl.py based on etl.ipynb after testing in test.ipynb.

6. Run etl in console, and verify that script runs:
    python etl.py
    

# Project files:
1. *data folder* All the JSON Files needed.
2. *sql_queries.py* contains all create, drop and insert sql queries.
3. *create_tables.py* drops and creates tables. run this file to reset the tables before running the ETL scripts.
4. *test.ipynb* displays the first few rows of each table to check the database.
5. *etl.ipynb* reads and processes a single file from song_data and log_data and loads the data into the tables.
6. *etl.py* reads and processes files from song_data and log_data and loads them into the tables.