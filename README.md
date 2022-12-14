# udacity_data_cloud_data_lake

### Purpose
A music streaming startup, Sparkify, has grown their user base and song database and want to move their processes and data onto the cloud. Their data resides in S3, in a directory of JSON logs on user activity on the app, as well as a directory with JSON metadata on the songs in their app.

In this project, I apply what I've learned on Spark and data lakes to build an ETL pipeline for a data lake hosted on S3. To complete the project, I will need to load data from S3, process the data into analytics tables using Spark, and load them back into S3. I'll deploy this Spark process on a cluster using AWS.

### Data pipeline
1. drop unneccessary tables and create staging and trasform tables
2. Load data files from s3, Song data: s3://udacity-dend/song_data and Log data: s3://udacity-dend/log_data into staging tables
3. transform staging tables into final tables
4. write final tables into s3

### How to run this?
1. Launch EMR Cluster and Notebook
2. Step 1: Configure your cluster with the following settings
3. Step 2: Wait for Cluster "Waiting" Status
4. Step 3: Import notebook from this repo
5. Step 4: Configure your notebook
6. Step 5: Wait for Notebook "Ready" Status, Then Open
7. Step 6: Run the code in the notebook

### Database diagram

##### Fact table
songplays

- songplay_id PRIMARY KEY
- start_time
- user_id FOREIGN KEY
- level
- song_id FOREIGN KEY
- artist_id FOREIGN KEY
- session_id FOREIGN KEY
- location
- user_agent

##### Dimentional table

users 
- user_id PRIMARY KEY
- first_name 
- last_name
- gender 
- level

songs
- song_id PRIMARY KEY 
- title 
- artist_id 
- year 
- duration

artists 
- artist_id PRIMARY KEY 
- name 
- location 
- lattitude 
- longitude

time 
- start_time PRIMARY KEY 
- hour 
- day 
- week 
- month 
- year 
- weekday
