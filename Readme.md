<p align=center><img src="src/logo-henry.png"><p>

# <h1 align=center> MLops Project - HENRY DATA SCIENCE <h/>
## <h2 align=center> Movie Recommendation System <h/>
### <h3 align=center> By Angel Bello Merlo <h/>
<p align="center">
<img src="src/Recomendation.jpg"  height=300>
</p>

## Topic

You started working as **`Data Scientist`** in a start-up that provides aggregation services for streaming platforms. The world is beautiful and you are going to create your first ML model that solves a business problem: a recommendation system that has not been launched yet!

You go to their data and you realize that their maturity is low. Nested data, without transformation, there are no automated processes for updating new movies or series, among other things(making your job impossible).

## ETL process
Extract, Transform and load process was carried out following these steps.

Original Dataset:
[Original Dataset ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

### Required Transformations
+ Some fields, like **`belongs_to_collection`**, **`production_companies`** and others (see data dictionary) are nested, that is, they either have a dictionary or a list as values ​​in each row, you will need to un-nest them to join them to the dataset again do some of the API queries! Or find a way to access that data without un-nesting.

+ Null values ​​of the **`revenue`**, **`budget`** fields must be filled with the number **`0`**.
  
+ Null values ​​in the **`release date`** field should be removed.

+ If there are dates, they must have the format **`YYYY-mm-dd`**, they must also create the **`release_year`** column where they will extract the year of the release date.

+ Create the column with the return on investment, called **`return`** with the fields **`revenue`** and **`budget`**, dividing the last two **`revenue / budget`**, when there is no data available to calculate it, it should take the value **`0`**.

+ Remove columns that will not be used, **`video`**,**`imdb_id`**,**`adult`**,**`original_title`**,**`vote_count`**,**`poster_path`** and **`homepage`**.

This process can be seen there:
[ETL MLops Movie Recommendation System ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)
Dataset after ETL:
[ETL Dataset ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

## EDA 
Exploratory Data Analysis was carried out following these steps.
+ Cleaning datased done.
+ Use libraries like pandas_profiling, missingno, pandas, matplotlib.
+ Investigate the relationships between the variables of the datasets.
+ The EDA should include interesting graphs to extract data, such as a word cloud with the most frequent words in movie titles.
+ Check if there are outliers or anomalies.

<p align=center><img src="src/EDA3.png"><p>

This process can be seen there:
[EDA MLops Movie Recommendation System ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)
Dataset after EDA:
[EDA Dataset ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

## Functions for the API Development
Six functions for the endpoints that will be consumed in the API.
Dataset for functions:
[Function Datasets](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)
1. The month is given and the function returns the number of movies that were released that month.
2. The day is given and the function returns the number of movies that were released that day.
3. The franchise is given, returning the number of movies, total and average profit.
4. Give a country, returning the number of films produced there.
5. Give a production company, returning the total profit and the number of movies they produced
6. Give the movie, returning the investment, the profit, the return and the year in which it was released.

This process can be seen there:
[Functions API MLops Movie Recommendation System ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

## Function ML Movie Recommendation System for the API Development

+ This consists of recommending movies to users based on similar movies, so the score similarity between that movie and the rest of the movies must be found, they will be ordered according to the similarity score and it will return a list with 5 values

Based on research articules, features and ML text-analysis model were chosen.
1. Features: genres, overview(sample based on Popularity due to an excesive computational cost if whole dataset is used).
2. TF-IDF (Term Frequency–Inverse Document Frequency) for Natural Language Proccesing ML model using Scikit-learn.

<p align=center><img src="src/EDA2.png"><p>

This process can be seen there:
[Model MLops Movie Recommendation System ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

## Deployment
+ Making the company data available using the FastAPI framework.
+ Render is an unified cloud to build and run all your apps and websites.
<p align=center><img src="src/Render.png"><p>

Deployed API can be seen there:
[Render API Movie Recommendation System ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

## Video Tutorial
This video can be seen there:
[MLops Movie Recommendation System ](https://github.com/Marcostamal/PI_MASA_DE/blob/main/Data_Cleaning_Plataformas.ipynb)

