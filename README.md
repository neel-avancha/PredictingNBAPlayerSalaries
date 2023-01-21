# PredictingNBAPlayerSalaries


                                                                             Abstract

In the NBA, salaries are determined by several factors, 
including the player's experience, their performance on the 
court, and the demand for their services. As a result, the 
salaries of players can vary widely, with some players earning 
millions of dollars per year, while others earn significantly 
less. The salaries of players also have a direct impact on the 
overall economics of the league. The NBA operates on a 
system of a "soft" salary cap, which means that teams are 
allowed to exceed the salary cap in order to sign players. This 
means that the salaries of the players have a direct impact on 
the amount of money that teams can spend on player salaries.
Additionally, the salaries of players in the NBA are important 
for the overall health of the league. The higher the salaries of 
players, the more competitive the league will be, as teams will 
be able to attract and retain the best talent. This in turn leads 
to a more exciting and competitive league, which is beneficial 
for both players and fans. Overall, the salaries of players in 
the NBA are an important part of the league, providing players 
with financial security and helping to create a competitive and 
exciting league for fans.

                          Introduction

                  Defining the Problem & Our Motivation

The issue of NBA players being both overpaid and underpaid is a 
complex one, and there are several reasons why it can be 
a problem. First and foremost, there is a significant amount of 
money involved in the NBA. The average player salary is over $7 
million per year, and the top players can earn well over $30 
million per year. This means that even a small difference in salary 
can represent a significant amount of money, and this can create a 
significant imbalance in the league.
Furthermore, the issue of overpaid and underpaid players is not 
just a problem for the players themselves. It can also have an 
impact on the teams and the league. For example, if a team has 
several overpaid players on its roster, it may be difficult for them 
to compete with other teams because they have less money 
available to sign other players. This can create a competitive 
imbalance in the league, which can be detrimental to the overall 
quality of the game.
Additionally, the issue of overpaid and underpaid players can also 
create problems within teams. If a team has several overpaid 
players, it can create resentment among the other players who may 
feel that they are not being fairly compensated for their 
contributions. This can lead to conflicts and division within teams, 
which can affect their performance on the court. 
General managers are the ones responsible for offering contracts 
to these players and must do their best job to correctly pay 
someone based on their worth, to avoid the problems mentioned 
above.
Overall, the problem of determining an accurate salary for NBA 
players, and it is important for teams and the league to address 
it to maintain a fair and competitive environment


                          Methodology

                        Data Acquisition

We obtained two datasets from two different sources for this 
project. We edited and compiled these two data sets into a single 
data frame, which we proceeded to use for our models.
1. Our first data set was from Basketball Reference and contained 
statistical data for every player during the 2021-2022 NBA season. 
Basketball Reference has been tracking almost every single 
statistical category for the NBA for decades.
2. Our second data set was from Hoops Hype and contained data 
on NBA players’ salaries for the 2021-2022 NBA season. 

                          Data Preparation

We performed many data preparation steps on each dataset. First, we 
deleted unwanted columns from each dataframe, and renamed some 
of the other remaining columns to be more descriptive. We deleted 
rows where there were more than 4 null values, and imputed certain 
stats to the mean for the rest of the null values. In the player stats 
dataframe, there were multiple rows representing players who have 
been traded, so we had to delete all excess rows and only keep the 
row representing their total averages for the season. After both data 
sets were cleaned, we merged them by adding a salary to every player 
if it exists in our salary dataframe. We deleted players that we didn’t 
have salary information on. Lastly, we created our own column 
representing salary brackets of size $5,000,000 which spanned from 
$0 to $50,000,000 and filled this in using each player’s salary.

                          Data Visualization

After cleaning and preparing all the data, we were able to create many different visualizations for our data. 
![image](https://user-images.githubusercontent.com/123276734/213894411-d0569759-60b3-4f0c-972a-b5aea87e8547.png)
![image](https://user-images.githubusercontent.com/123276734/213894414-6de4f5f8-cc06-4d78-a678-5b47934b5324.png)

                          Identifying Features

To identify features to use for our model, we began looking at the correlations between variables and Salary Bracket. We decided on using variables which had a correlation of 0.25 or greater with Salary Bracket in our model. There were quite a few features, including Age, Points, Rebounds, Assists, and many more.
![image](https://user-images.githubusercontent.com/123276734/213894437-ad36255f-c23d-477a-aa4a-e0d2efe6dbbe.png)
A heatmap visualizing the correlations between features is shown to the left. Some have much greater correlation than others, but all of them were used in the model.


                          Results and Evaluation

                          Model Selection

The three models that we created were a K-NN Classification Model, Random Forest Classification Model, and a Support Vector Machine. For each of them, we tuned the hyperparameters and found the accuracy based on the best hyperparameters. The accuracy was reported as a decimal which represented the percentage of players who were placed into the correct salary bracket. The hyperparameters that we tuned and corresponding accuracies are in the table below. 

![image](https://user-images.githubusercontent.com/123276734/213894455-2415848b-5887-4161-afce-ae2db5280863.png)

As we can see in the table above, all 3 models had relatively similar performance. The Random Forest Classifier did have the highest accuracy, with 0.72. Both the Random Forest Classifier and K-NN Classification saw increases in accuracy after tuning hyperparameters, but the Support Vector Machine remained at 0.67 with regardless of the hyperparameters. Within our Random Forest Classifier Model, the most important features for predicting the salary bracket for an NBA player were Age, Points, and Minutes Played. Other important NBA stats such as assists, and rebounds didn’t have as large of an impact as expected for predicting salary.




