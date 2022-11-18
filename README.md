# NFL Hall of Fame Classification with Career Statistics

### John Harrigan and Evan Staffen

# 1. Business Understanding

**Stakeholder:** Agents of recently retired NFL players.

The ultimate recognition for an NFL player is to be inducted into the Hall of Fame. An NFL player is eligible for nomination five years after retirement. Only 1.2% of NFL players can call themselves Hall of Famers. While the avid football fan knows more than just this small fraction of players, Hall of Famers are the household names. They have influence beyond their playing days and way outside the sphere of football.  

Michael Strahan, former defensive back for the New York Giants is a host on the talk-show 'Live with Michael and Kelly'. Troy Polamalu, one of the all-time great safeties for the Pittsburgh Steelers, is still seen in Head & Shoulder's ads because of his famous, curly hair. Peyton Manning may be one of the prime examples of this. He was just the host of the Country Music Awards, acted in the animated movie 'Ferdinand' and has endorsement deals with various companies. 

Ultimately, if NFL player agents could use our model to predict the likelihood of going to the hall of fame, then they could maximize the value of the players they have signed. We set out to create a model that can determine whether or not a player will make it to the Hall of Fame based on their career statistics. 

> What are the most important metrics for determining whether a player will make it into the hall of fame?
    
> Who is near the the hall of fame status that is not up for nomination yet that should be targeted?

# 2. Datasets

Multiple datasets from different sources were used for this analysis. All of the datasets can be accessed from the data folder located within this repository.

Two datasets from __[Kaggle](https://www.kaggle.com/datasets/zynicide/nfl-football-player-stats)__ were used. One had basic demographics for 25K+ NFL players from 1950-2017. The other had indvidual game data for each player in the former dataset, with just above 1 million rows. 

7 separate datasets were taken from __[Profootballreference's database](https://www.pro-football-reference.com/)__ so we could add the individual accolades for each player. 6 of these datasets were used to compile the MVP, DPOY, DROY, OPOY, OROY, Superbowl MVPs of each year into a new column which was the sum of everyone of those awards a player won in their career. The last dataset allowed us to create a column for our target, whether a player made the hall of fame as 1 or they didn't make the hall of fame as 0. 

* FIGURE OUT HOW TO CITE PROPERLY *

**JACK POSSIBLY DOING MORE WEB SCRAPING**


# Data Understanding and Visualization

> ![HOFbyTeam](https://user-images.githubusercontent.com/113449546/202628147-2ce3b61f-e509-4a7b-91d7-07cd54e8264d.png)

As mentioned above, only 1.2% of players make it to the hall of fame. Above the team with the highest percentage of hall of famers is the Cleveland Browns with 1.74%. 

> ![HOFWin%](https://user-images.githubusercontent.com/113449546/202628174-e306f2aa-aaea-4f13-a076-0cac885017d3.png)

Although hall of famers tend to have an average win percentage approximately 10 points higher than the non-hall of famers, there is clearly a significant overlap in their win percentages. 

> ![PosHOF%](https://user-images.githubusercontent.com/113449546/202628093-9a14acf4-e766-4767-8bb5-c30a7ebc54fd.png)

It is not surpirsing that quarterbacks and playmakers (runningbacks, wide receivers and tight ends) all have the highest percentage of players going into the hall of fame. While it is surprising that defensive players make up approximately 1/3 of the hall of famers, they also clearly get inducted at a much lower rate.

> ![AwardsPerPlayer](https://user-images.githubusercontent.com/113449546/202628228-204a3cd3-42a0-46fa-b2c3-3de90052a66b.png)

The career accolades gathered such as MVPs, Offensive and Defensive player of the year etc. all undoubtedly play an important role in hall of fame determination. While players with one career award are unlikely to make it into the hall of fame, after one award the odds seem to swing in the players' favor. 

# Modeling

Since the hall of fame players only make up 1.2% of the dataset, we knew we would be having to acconut for this class imbalance in our models. As well, that inherently means that we want a model that does better than picking a player to not go to the hall of fame 98.8% of the time. All the models created utilized imblearn's SMOTE in order to help account for the severe imbalance. As well, every model used GridSearchCV with a 5-fold cross-validation to find the best parameters that were then run on the test set.

We decided to focus on maximizing recall with our models, whick is a measure that tries to minimize the number of false negative results we obtain. A false negative in this case would be players who the model predicts to not go to the hall of fame, even though they do. Ultimately, the cost of missing out on a hall of fame caliber player is much worse than taking a chance on one that does not pan out. 

1. Baseline Logistic Regression
2. Basic Logistic Regression with SMOTE
3. Logistic Regression with Best Parameters
4. Random Forest Classifier
5. XGBoost Classifier
6. C-SVC
7. KNN (K-Nearest Neighbors)

# Evaluation


# Conclusions & Recommendations

*Model Performance:*

*Model Limitations:*

*Recommendations:*

# Next Steps

#### 1. We recommend trying to compile more data on College Football statistics to incorporate into the model.
#### 2. Incorporate data on player characteristics/popularity.
#### 3. Create different metrics and models to evaluate players by position.
