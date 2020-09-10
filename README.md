# Project Summary:
In this project we created a database for Sparkify and created the fact and dimension tables in a way to later retrieve the data with analytic focus.
We created a star schema with the following tables:

**Fact table:**
- songplays (song_play_id as PRIMARY KEY and contains columns of all Dimension table PRIMARY KEYS. This Star schema makes it easy to query data)

**Dimension table:**
- users    (user_id as PRIMARY KEY)
- songs    (song_id as PRIMARY KEY)
- artists  (artist_id as PRIMARY KEY)
- time     (start_time as PRIMARY KEY)

# Explanation of Files in the Repository:
- **data** folder contains JSON files for songs metadata and user log activity of listening to songs
- **create_tables.py** is a python scripts which creates and connects to Sparkify data base and then executes the CREATE and DROP table queries for all the tables in our Sparkify database. These tables are defined in the **sql_queries.py** script
- **sql_queries.py** is a python script which executes all the SQL statemnts such as DROP TABLES , CREATE TABLES and INSERT INTO TABLES. This script contains all the fact and dimensions table defined above and sets up all the column names, their data types and PRIMARY KEYS
- **etl.ipynb** is the Jupyter notebook for the project. The first line of code in this file runs the **create_tables.py** script which creates Sparkify database and executes the queries defined in **sql_queries.py**. Then we define the ETL process, by reading in JSON data with the help of python pandas library and then extracting the useful columns while ignoring the unwanted ones. The data is then loaded into each tables row by row by executing INSERT INTO sql statements which were defined in **sql_queries.py** earlier on. Once this process is established with data loading for first records, the process is repeated for the entire collection of JSON files using a for loop, this is done through **etl.py** python script
- **test.ipynb** is Jupyter notebook to test if the the data loading is done correctly and it includes SELECT statements to query the tables created

# Running Scripts:
All the python scripts could be run from Jupyter notebooks by running the following command
- %run -i **scriptname**.py.Simply replace the **scriptname** with **etl** to run the etl.py script to perform the entire ETL process. This has already been done in the last cell block of the **etl.ipynb** notebook



