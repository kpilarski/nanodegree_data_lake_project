# Data Lake Project - Udacity Data Engineer Nanodegree

## Project: Data Lake

### Context 

A music streaming startup, Sparkify, has grown their user base and song database even more and want to move their data warehouse to a data lake. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

As their data engineer, you are tasked with building an ETL pipeline that extracts their data from S3, processes them using Spark, and loads the data back into S3 as a set of dimensional tables. This will allow their analytics team to continue finding insights in what songs their users are listening to.

You'll be able to test your database and ETL pipeline by running queries given to you by the analytics team from Sparkify and compare your results with their expected results.

### Project Description
In this project, you'll apply what you've learned on Spark and data lakes to build an ETL pipeline for a data lake hosted on S3. To complete the project, you will need to load data from S3, process the data into analytics tables using Spark, and load them back into S3. You'll deploy this Spark process on a cluster using AWS.

### Schema for implemented tables:
#### Fact tables:
- ___songplays___ - records in log data associated with song plays i.e. records with page NextSong
    - songplay_id 
    - start_time 
    - user_id 
    - level 
    - song_id 
    - artist_id 
    - session_id 
    - location 
    - user_agent 
    
#### Dimension tables:
- ___users___ - users in the app
    - user_id
    - firstname
    - lastname 
    - gender
    - level 
    
    
- ___songs___ - songs in music database
    - song_id
    - title
    - artist_id 
    - year
    - duration  
    
    
- ___artists___ - artists in music database
    - artist_id
    - name 
    - location 
    - latitude 
    - longitude
    
- ___time___ - timestamps of records in songplays broken down into specific units
    - start_time 
    - hour 
    - day
    - week
    - month 
    - year
    - weekday 

### ETL Pipeline

Datasets are stored in JSON format are retrieved from S3 bucket - log_data and song_data. Song data is a subset of Million Song Dataset. There is a script in main file 'etl.py' - and once executed it retrieves the song and log data from S3 bucket, then transforms the data into fact and dimension tables and finally loads output data to the S3. Whole ETL process in located in the etl.py file.

__Steps in ETL:__
1. __Loading AWS credentials__
2. __Reading data from S3 bucket__
3. __Transforming data with Spark__
4. __Loading data to S3 bucket__

    
    
### Project structure:

1. ___data___ - folder that contains data files
2. ___dl.cfg___ - config file with AWS KEYS
3. ___etl.py___ - ETL script (retrieving from S3, transforming and finally loading into S3)
4. ___README.md___ - project description



### How to start project?

1) Firstly you need to create S3 bucket and complete your credentials in dl.cfg file


2) then ETL script can be started with following command:

`python etl.py`




