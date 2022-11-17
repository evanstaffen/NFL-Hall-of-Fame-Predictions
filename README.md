# NFL Hall of Fame Classification with Career Statistics

### John Harrigan and Evan Staffen

# Business Understanding

**Stakeholder:** Marketing teams for large corporations, NFL teams.

The ultimate recognition for an NFL player is to be inducted into the Hall of Fame. Only 1.2% of NFL players can call themselves Hall of Famers. While the avid football fan knows more than just this small fraction of players, Hall of Famers are the household names. They have influence way beyond their playing days and way outside the sphere of football.

Michael Strahan, former defensive back for the New York Giants is a host on the talk-show 'Live with Michael and Kelly'. Troy Polamalu, one of the all-time great safeties for the Pittsburgh Steelers, is still seen in Head & Shoulder's ads because of his famous, curly hair. Peyton Manning may be one of the prime examples of this. He was just the host of the Country Music Awards, acted in the animated movie 'Ferdinand' and has endorsement deals with various companies. 


We set out to create a model that can determine whether or not a player will make it to the Hall of Fame based on their career statistics.

> What are the most important metrics for determining whether a player will make it into the hall of fame?
    
> Who is near the the hall of fame status that is not up for nomination yet that should be targeted for brand partnerships?

# Datasets

Multiple datasets from different sources were used for this analysis. All of the datasets can be accessed from the data folder located within this repository.

Two datasets from __[Kaggle](https://www.kaggle.com/datasets/zynicide/nfl-football-player-stats)__ were used. One had basic demographics for 25K+ NFL players from 1950-2017. The other had indvidual game data for each player in the former dataset, with just above 1 million rows. 

7 separate datasets were taken from __[Profootballreference's database](https://www.pro-football-reference.com/)__ so we could add the individual accolades for each player. 6 of these datasets were used to compile the MVP, DPOY, DROY, OPOY, OROY, Superbowl MVPs of each year into a new column which was the sum of everyone of those awards a player won in their career. The last dataset allowed us to create a column for our target, whether a player made the hall of fame as 1 or they didn't make the hall of fame as 0. 

* FIGURE OUT HOW TO CITE PROPERLY *

**JACK POSSIBLY DOING MORE WEB SCRAPING**

# Data Understanding and Visualization

* Visual of disparity between HOF and not *

* HOF by position *

* HOF by games played *

* HOF by awards *

* HOF by team *


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
