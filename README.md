# Math475 Final Project
link to the repository: https://github.com/GustavoTadokoro/Math475FP

1. Introduction
In this project, I worked with a dataset containing information about superheroes: their intelligence, strength, speed, durability, power, combat skills, and alignment (good, neutral, or bad). The task was to predict the outcome of a random battle between a hero/Neutral and a Villain. A Random Forest Classifier was chosen to build the predictive model due to its robustness, ability to handle complex, non-linear data, and ability to avoid overfitting. The goal was to develop a model that could predict the winner of a random duel between a Hero/Neutral character versus a Villain Character.

2. Data Exploration & Preprocessing
The initial dataset was examined for its structure, and the following steps were taken to prepare it for modeling:
  - Missing Values: We checked for missing values and handled them by replacing missing entries with zeros where appropriate.
  - Duplicate Rows: Duplicates were removed to ensure that our data did not have redundant entries.
  - Feature Selection: We retained the most relevant columns, including attributes like intelligence, strength, speed, durability, power, and combat. Unnecessary columns were discarded.
  - Feature Engineering: We created a new feature, "total power," which summed up the numeric attributes (intelligence, strength, speed, etc.), as this provided a consolidated measure of a superhero's overall capabilities.
  - One-Hot Encoding: The alignment feature was one-hot encoded to convert categorical data into a numerical format, making it suitable for machine learning algorithms.
  - Visualization: A count plot was used to examine the distribution of hero alignments, and a bar chart was plotted after one-hot encoding to show the distribution of good, bad, and neutral alignments.
The preprocessed dataset was cleaned and formatted, providing a structured input for building the model.

3. Model Selection & Training
I chose a Random Forest Classifier for this project due to a couple of reasons:
  - Random Forests are effective for classification and prediction tasks, especially when there are many features and complex relationships.
  - This model is capable of handling both numerical and categorical data and can provide insights into feature importance.
For training the model and creating the battle scenarios, the following was done:
  - Battle Simulation: Battles were simulated between characters from three groups: heroes, villains, and neutrals. Each battle involved comparing two characters (one hero or neutral vs. one villain), and the character        with the higher "total power" was considered the winner.
  - Feature Creation for Battles: For each simulated battle, we created a training sample by combining the features of both characters involved (including their total power, strength, and other attributes). The target         variable was the winner of the battle.
  - Model Training: The dataset of simulated battles was split into a training set (80%) and a test set (20%). The Random Forest Classifier was then trained on this data.
The end goal of the model was to predict the winner of each battle based on the attributes of the two competing characters.

4. Performance Evaluation
The performance of the Random Forest Classifier was evaluated using several metrics:
  - Accuracy: The model achieved an accuracy of approximately 95%, meaning it correctly predicted the outcome of the battles 95% of the time.
  - Precision: The model had a precision of 0.95, indicating that when the model predicted a win for a character, it was correct 95% of the time.
  - Recall: The recall was also 0.95, meaning the model was able to identify winners (and losers) with high accuracy.
  - Confusion Matrix: The confusion matrix showed a relatively even distribution of true positives, true negatives, false positives, and false negatives, indicating that the model did not have a strong bias toward             predicting one character as the winner.
  - Classification Report: The detailed classification report revealed that the model performed well in predicting both heroes' and villains' outcomes, achieving balanced precision and recall across categories.
    These evaluation metrics suggest that the Random Forest model was effective in predicting the outcome of battles based on the superheroes' attributes.

5. Challenges & Future Work
- Throughout the project, I had to face many challenges. They varied from manipulating the dataset to where I kept all important features to having to check if the results of my model were true positives/negatives or        false positives/negatives.
- The first challenge I faced was making a proper selection of features as well as deciding the proper way to separate my set to where I would be able to achieve my goal. To address this specific challenge I looked at the   available features and considered which ones would be more relevant to my desired goal. Nex,t I analyzed the different factors within each character to find a proper split for the dataset, and that is where I landed on    the Hero/Villain/Neutral split.
- Another challenge I faced was deciding who gets to fight who. Upon further analysis, I realized that perhaps people of the same alignment should not be fighting their companions (for example Hero vs Hero), which was       easily overcome by having the model pick between a hero and a neutral to fight a villain. Following that challenge I faced another one which would have me questioning how many battles should be simulated to avoid          overcomputing or undercomputing. This was addressed by several different tests which involved trying different numbers of simulated battles, as well as finding a sweet spot where I would not get diminishing returns due    to overcomputing.
- For checking for true/false positives/negatives I implemented a confusion matrix to illustrate where each prediction was going. 
- The last challenge was choosing a model that would be robust enough to predict the outcomes based on my data. For that, I chose a RandomForestClassifier as it is robust enough to handle classification/prediction tasks,    as well as get its result based on a variety of different trees that the model uses during evaluation. Lastly, it was because the model can handle both linear and non-linear relationships between features.
- Overall, the challenges faced allowed me to find new approaches to achieve my goal. For future work, I could improve on having it pick a random stat rather than the combined value of all stats as well as implementing a    way for neutrals to be able to fight heroes.
