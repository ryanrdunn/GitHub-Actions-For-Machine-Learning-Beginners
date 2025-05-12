# GitHub-Actions-For-Machine-Learning-Beginners
GitHub-Actions-For-Machine-Learning-Beginners
url: https://www.kdnuggets.com/github-actions-for-machine-learning-beginners


## Setting Up
Create repo 
Create requirements.txt file and place python libraries required
$ pip install -r requirements.txt


The dataset is big, so we have to install GitLFS into our repository and track the train CSV file.  
$ git lfs install
$ git lfs track train.csv

## Training and Evaluating Code
 Create a `train.py` file and copy and paste the following code.
The code uses ColumnTransformer and Pipeline for preprocessing the data and the Pipeline for feature selection and model training. 
After evaluating the model performance, both metrics and the confusion matrix are saved in the main folder. These metrics will be used later by the CML action.
In the end, the scikit-learn final pipeline is saved for model inference. 