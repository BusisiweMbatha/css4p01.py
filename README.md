# css4p01.py
CSS Project - Option 1: IMDB Data
#-*- coding: utf-8 -*-
"""
Created on Sun Feb  4 16:43:29 2024

@author: themb

"""
import pandas as pd

df= pd.read_csv("movie_dataset.csv")

print(df.info())



X = df["Revenue (Millions)"] .mean()
df["Revenue (Millions)"]. fillna(X, inplace = True)

Y = df["Metascore"] .mean()
df["Revenue (Millions)"]. fillna(Y, inplace = True)

# 1
# Find the highest rated movie
H= df[df["Rating"] == df["Rating"].max()]

print(H)

#2
#What is the average revenue of all movies in the dataset? 

average=sum(df["Revenue (Millions)"])/len(df["Revenue (Millions)"])
print (average)

#3
#What is the average revenue of movies from 2015 to 2017 in the dataset?

N= df[df["Year"]>=2015]
average=sum (N["Revenue (Millions)"])/len(N["Revenue (Millions)"])
print (average)

#4
#How many movies were released in the year 2016?
M=df[df["Year"]==2016]
print (M)

#5
#How many movies were directed by Christopher Nolan?

movies =df[df["Director"]=='Christopher Nolan']

print (movies)

#6
#How many movies in the dataset have a rating of at least 8.0?
rating=df[df["Rating"]>=8]
print( rating)

#7
chris_movies =df[df["Director"]=='Christopher Nolan']
# Calculate the median rating of Christopher Nolan's movies

median_rating_chris_movies = chris_movies['Rating'].median()

print("Median Rating of Christopher Nolan's Movies is:", median_rating_chris_movies)

#9
movies_2006 = df[df['Year'] == 2006]
movies_2016 = df[df['Year'] == 2016]

# Calculate the number of movies made in 2006 and 2016
number_movies_2006 = len(movies_2006)
number_movies_2016 = len(movies_2016)


percentage_increase = ((number_movies_2016 - number_movies_2006) / number_movies_2006) * 100


print("The percentage increase in the number of movies made between 2006 and 2016 is:", percentage_increase, "%")




#10

actors = df['Actors'].str.split(',').explode().str.strip()
actor_counts = actors.value_counts ()
most_common_actor = actor_counts.idxmax()
print("The most common actor in all the movies is:",most_common_actor)

#11
genres = df['Genre'].str.split(',').explode().str.strip()

unique_genres_count = genres.nunique()

print("The number of unique genres in the dataset is:", unique_genres_count)




average_rating_by_year =groupby('Year')[Rating*].mean()

# Find the year with the highest average rating
year_highest_average_rating = average_rating_by_year.idxmax()

highest_average_rating-average_rating_by_year.max()

print("Year with the Highest Average Rating is:", (year highest_average rating) (Average Rating: (highest_average_rating)
