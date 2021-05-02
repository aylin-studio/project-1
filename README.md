
# Project scope: 
The analytics team is interested in understanding what songs users are listening to. 
They company wants a database schema and ETL pipline for the own analysis. 

# 1: Discuss the purpose of this database in the context of the startup, Sparkify, and their analytical goals.
# 1.1 Purpose of the database and anality goal
The analytic team of sparkiy wants a strucered database to analyze the users and theren behavior for optimize the Product. 
There for the need a easy data schema which are fast to analyize. 
The goal is to create a star schema to optimize the queries for the analyse the song play. 


# 2: State and justify your database schema design and ETL pipeline.
# 2.1 Database schema design
Why the star schema?
The star schema allows to denormalize the data in fact and dimension tabels this allows a fast analysis, aggregations and joins to analyze the dataset.

Given are two types of JASON files (multiple song Data and log Data) these datasets includes diffrent values which have to be strucerd in 5 tables one facts and 4 dimensions tabels.
The first step was to create the fact and dimension tables to incluede the datas from the jasion files int the following tables which are strctured in the following form: 

- Fact Table
 songplays - records in log data associated with song plays i.e. records with page NextSong
- Dimension Tables
users - users in the app
songs - songs in music database
artists - artists in music database
time - timestamps of records in songplays broken down into specific units


# 2.2 ETL pipline 

# Write sql_queries to create the empty tables to insert the data
1. Create the tables and assigne the data to the correct data types. It is important to contain for every table one primary key. This column uniquely identify the rows in the table. 
2. Write the insert syntax for the records. I also include the statement ON CONFLICT DO NOTHING for the Id valuse, to avoid any conflicts when some changes happend.  
3. Writhe the join to find the song_id and artist_id and join them with the song select query to insert these afterwords in the songplays fact table.

# 1 perform ETL on dataset song_data --> to create the songs and artists dimensional tables.
1. Extract Data for songs table and artist table
2. Insert Record into song and artist table

# 2 perform ETL on dataset log_data --> to create the time and users dimensional tables and songplays fact table.
## Extract, convert and insert data for time table 
1. Extract data for Time Table and convert the timstamp in the needed structure for the time table
2. Insert Records into Time Table

## Extract and insert records for Users Table
1. Extract data for user table
2. Insert records into user table

## Extract Data and insert records into songplays Table
1. Extract Data and songplays table therefor we need to geht the song id and artist id by querying the song and artist tables to find the matches based on song title, artist name, and song duration time. For that i wrote the syntax #find songs in the sql_queries. 
2. Insert recorts into songplays table

# 3 Last step is to close the connection the the sparkify database


