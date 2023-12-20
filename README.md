# Shot-by-Shot
In the game of basketball two teams compete head to head to determine which team can successfully score more points than the other. The most important aspect of the game is a player's ability to score, which involves successfully shooting a basketball into a net. In that sense, it would be extremely informative to a player, team, and overall basketball organization if they were able to predict the outcome of a certain shot selection. The goal of this project is to utilize machine learning models to see how well we can predict the outcome of a basketball shot. This involves using various classification models, conducting hyperparameter tuning, and identifying various important features to optimize our model’s predictive accuracy in identifying whether a basketball shot is a make or a miss.  

## Data
The datasets used for this project are provided in the github repository with the folder labeled 'Desktop'. Here we have 'shot_name_dataset' which is the dataset including the playeres name and 'shot_dataset' which is the same dataset without the players name.

## Models
Since we are predicting if a basketball shot is a miss or a make, this is a classification problem therefore I used different classification models to accomplish this goal. Below are the models I used along with the hyperparameters gathered through using a randomized grid search:

Logistic Regression:{Penalty: L1, Solver: Saga, Max_iter: 10000, C: 0.001}


Decision Tree: {Max_leaf_nodes: 20, Max_features: log2, Criterion: log_loss, Ccp_alpha: 0.001}


XGBoost: {N_estimators: 500, Max_leaves: 1, Learning_rate: 0.1}

## Results
After using Logistic Regresion, Decision Trees, and an XGBoost model, I found that the XGBoost model had the best performance with an accuracy of 65.28%. Below is a shot chart with the left being a random sample of 100 of Stephen Curry's shots in the 2021 season. The visualization for Stephen Curry's actual shooting is named 'Actual Shots' while the visualization of the XGBoosted model is called 'XGBoost Predictions'.






### Variable Appendix:
SHOT_DISTANCE: Distance of player to basket


LOC_X: Players x-position on the court ranging from -25 to 25


LOC_Y: Players y-position on the court ranging from 0 to 50


MINS_LEFT: Minutes left in the quarter


SECS_LEFT: Second left in the quarter


SHOT_TYPE: Type of shot (Either 2pt or 3pt)


BASIC_ZONE: Zone on court where shot was taken


ZONE_RANGE: Distance from the basket of zone


ACTION_TYPE: Description of shot (dunk, layup, finger roll,..etc)


MP: Minutes Played


FG%: Percentage of all shots (excluding free throws) that a player has made on the given season 


3P%: Percentage of three-point shots a player has made on the given season


2P%: Percentage of two-point shots (inside the three-point line) a player has made on the given season


eFG%: A players effective field goal percentage which gives different weights to a players 3P% and 2P% as a three-point shot is intrinsically more difficult to make. 


eFG% Formula: 2P% + 1.5*3P%


SHOT_ACTION: High level description of the shot (driving finger roll shot, tip dunk shot, etc..)
