# Box-Office-Movie-Prediction-with-Univariate-Linear-Regression
# Introduction
We have a budget of $30 million for a movie. How much can we make in total revenue using data from movies produced from 1915 - 2022?

# Getting and storing the data
Here, we use selenium web driver which is a web framework that allows for automating and controlling web browsers.
I set up a script in a python function to loop through the 62 pages and extract the table containing the data.
This was the most challenging part of the whole process. There are 100 movies on each page.
Each of the data from 62 pages was saved in a 2-dimensional python array with column index 0 and row index 0 to 61. 
For instance, the first page was saved in array[0][0], second page in array[1][0] etc.
Each of the pages is stored in a .csv file and merged

# Cleaning the data
The dollar ($) and comma (,) symbols were removed and the figures were formatted as numeric values both in power BI and jupyter notebook.
Release Date, Movie, and Domestic Gross columns were removed to simplify the linear regression analysis
Movies with $0 for worldwide gross were removed from the data as well.
The domestic Gross column was also removed since it wasn't needed for both the regression analysis and the visualization

# Regression analysis
The slope coefficient is 3.17 which means there is a positive relationship between budget and revenue and for each dollar we spend on a movie, we should get about $3.17 in return. 
The intercept is -$8.38 million which tells us that a movie with a budget of $0 will lose about $8 million which is unrealistic.
With our $30 million budget, we can now predict how much we can make off of our movie which is -8384779 + (3.1730714 x 30000000) which is approximately $95 million which is not a bad investment.
R squared is 0.54 which is the amount of variation in movie revenue that is explained by the movie budget. Simply put, our univariate linear regression model with a single feature which is the production model can explain around 54% of the variation in the movie revenue.

# Conclusion
Our model is an oversimplification of the real world and should be taken with a grain of salt. Care should be taken reading too much into this model. There are a lot of unexplained factors. For example, how will our model perform if we had more features like how long it took to make the movie and the number of top stars in the movie? Will it make our model better and make our predictions more accurate?
