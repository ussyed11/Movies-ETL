# Movies-ETL
## Overview:
Britta from Amazing Prime needs to gather data from both Wikipedia and Kaggle, combine them, and save them into a SQL database so that the hackathon participants have a nice, clean dataset to use. To do this, she will follow the ETL process: extract the Wikipedia and Kaggle data from their respective files, transform the datasets by cleaning them up and joining them together, and load the cleaned dataset into a SQL database. After the lengthy process of ETL, Amazing Prime loves the dataset and wants to keep it updated on a daily basis. Britta needs our help to create an automated pipeline that takes in new data, performs the appropriate transformations, and loads the data into existing tables. We’ll need to refactor the code from the module to create one function that takes in the three files—Wikipedia data, Kaggle metadata, and the MovieLens rating data—and performs the ETL process by adding the data to a PostgreSQL database.


## Procedure and Results:

The ETL process is broken down into four jupyter notebook files:

##### 1. ETL_function_test.ipynb
* Data is extracted from the website in JSON and CSV formats.
* Data is transformed into Pandas data frames.
* JSON file requires extra step – loading file first and then transforming into data frame.

Some images from our code are below:

![Screen Shot 2022-04-11 at 8 01 36 PM](https://user-images.githubusercontent.com/98566486/162852218-290dd32b-dac7-4884-867d-408ab3b9c242.png)


![Screen Shot 2022-04-11 at 8 02 40 PM](https://user-images.githubusercontent.com/98566486/162852303-19561320-a855-49b0-b047-b3f05b57fabf.png)

##### 2. ETL_clean_wiki_movies.ipynb

* Function clean_movie combines scattered data of alternative languages into one column alt_titles.

* Its subfunction change_column_name organizes column names into consistent pattern.

* In the function extract_transform_load the transformation process of wiki movies data begins and includes:
- Python list comprehensions.
- apply() and map() methods in combination with lambda functions.
- regular expressions or RegEx.

![Screen Shot 2022-04-11 at 8 06 13 PM](https://user-images.githubusercontent.com/98566486/162852637-b6e88671-3b14-4de5-9c83-4ea5dd3335d3.png)

![Screen Shot 2022-04-11 at 8 06 30 PM](https://user-images.githubusercontent.com/98566486/162852650-14fd6516-cba4-4d57-98b4-27d7e49eb643.png)

##### 3. ETL_clean_kaggle_data.ipynb
Function extract_transform_load gets new tasks for cleaning Kaggle data and includes:
- Changing datatypes, using methods pd.to_numeric, astype() and python comparison operators for Boolean types.
- Filling missing values and filtering unwanted columns.
- Merging data frames using pd_merge method.

##### 4.  ETL_create_database.ipynb
The function in its final step connects to the database by sqlalchemy library and to_sql method.
Complete ETL process can be executed with a single function extract_transform_load call.


![Screen Shot 2022-04-11 at 8 09 05 PM](https://user-images.githubusercontent.com/98566486/162852837-3fe32ea5-d7d7-4103-a9be-2326155bdc7a.png)


![movies_query](https://user-images.githubusercontent.com/98566486/162852883-0580bfaf-97e7-4cf9-97bb-87a416118927.png)

## Summary:

Three files were extracted in forms of JSON and csv files from Wikipedia and Kaggle data sources. Then transformed and joined. A movies and ratings file were loaded into a database for the hack-a-thon event so querries can run.


