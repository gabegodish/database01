# Olist Brazil E-Commerce Database Project
Hi! This is my repo for a database project. I'll explain where I acquired the dataset, how I built the database, and more.

## Dataset
For this database project, I acquired the dataset on Kaggle. I'll link it here: [Brazilian E-Commerce Public Dataset](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce?select=olist_customers_dataset.csv).

I wanted to utilize a dataset that had multiple files to create a relational database. 
This was a great dataset to work with, it was very easy to understand and it is by default in a snowflake schema.
The dataset has nine .csv's, which can be visualized into tables (used draw.io and is accessible in the repo). 
One of the .csv files is a geolocation file containing useful information if you wanted to map out where orders are being distributed to and from.

## Postgres
I wanted to use Postgres as my DBMS, as it is fairly straight forward and something I've utilized before in other projects. 
I chose to create the database on my local machine as it was free and easy to access using psql on WSL.

## Python & SQL
The only python packages I ended up using were **pandas**, **jupyter** (notebooks), **psycopg2** (psycopg2-binary specifically!). In my pyproject.toml file, you'll see more packages, however they were not needed in this case.
After creating a function to initialize the database, I just read in all the .csv files with pandas and did some data cleaning as needed. 
Re-ordering columns, setting a default timestamp for incomplete orders, and filling in missing values were some changes needed to make the database fully functioning.
Once all my data was successfully cleaned and ready to go, I wrote the table creation queries which would execute immediately, and then I created the insertion queries for each table.
I utilized for statements to read the data into the tables, which could then be queried through psql.
