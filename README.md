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

# Continous Machine Learning (CML)
## GitHub Actions
 It's time for the main part. We will develop a machine learning workflow for training and evaluating our model. This workflow will be activated whenever we push our code to the main branch or when someone submits a pull request to the main branch.

To create our first workflow, navigate to the “Actions” tab on the repository and click on the blue text “set up a workflow yourself.” It will create a YML file in the .github/workflows directory and provide us with the interactive code editor for adding the code. 

### Add the following code to the workflow file. In this code, we are:
1. Naming our workflow.
2. Setting the triggers on push and pull request using `on` keyworks. 
3. Providing the actions with written permission so that the CML action can create the message under the commit.
4. Use Ubuntu Linux runner.
5. Use `actions/checkout@v3` action to access all the repository files, including the dataset. 
6. Using `iterative/setup-cml@v2` action to install the CML package. 
7. Create the run for installing all of the Python packages.
8. Create the run for formatting the Python files.
9. Create the run for training and evaluating the model.
10. Create the run with GITHUB_TOKEN for moving the model metrics and confusion matrix plot to report.md file. Then, use the CML command to create the report under the commit comment. 