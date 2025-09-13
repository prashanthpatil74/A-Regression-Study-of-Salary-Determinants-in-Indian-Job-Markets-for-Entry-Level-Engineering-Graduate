PROBLEM STATEMENT:
* A study of salary determinants in Indian job markets for entry level engineering graduates.

The dataset was released by Aspiring Minds from the Aspiring Mind Employment Outcome 2015 (AMEO). 
The study is primarily limited only to students with engineering disciplines. 
The dataset contains the employment outcomes of engineering graduates as dependent variables (Salary, Job Titles, and Job Locations) along with the standardized scores from three different areas – cognitive skills, technical skills and personality skills. The dataset also contains demographic features. 
The dataset contains around 40 independent variables and 3998 data points. 
The independent variables are continuous, categorical and Date in nature. The dataset contains a unique identifier for each candidate.

DATA PREPROCESSING AND FEATURE ENGINEERING:

Here are a few important pre-processing operations done in this project: 
* There were many redundant independent features in this dataset that don’t contribute to the Prediction of Salary of the candidates, therefore such columns have been removed from the data such as ID of Student, College-City Tier, College ID. 
* As Domain feature was creating noise in the data, and already had the branch wise marks distribution so, dropping the Domain feature seems to be an optimal approach. 
* Missing values indicated by -1 in some columns like Computer Programming, ElectronicsAndSemicon, Computer Science, MechanicalEngg, ElectricalEngg, TelecomEngg, CivilEngg was replaced with 0.
* Changed the scale of CollegeGPA feature to bring it at the same scale i.e. converted from 10 point scale to 0-100 point scale. 
* Grouped 41 different specializations into core disciplines i.e. Specialization column data was mapped to 3 groups (‘CS’,’EC’ and ‘other’) 
* Removed outliers: rows with Salary > 6,55,000 is less than 3% of the data, so these rows were removed as they were creating noise in the dataset. 
* Only year from the DOB column was retained and named that column as DOByear. 
* New columns: GradAge and 12thAge were introduced indicating the age of person during graduation and 12thgraduation. 
* In 12thAge feature, neglected students with 12thAge>22 and 12thAge<15 by logic. 
* There was a missing value in graduation year, so imputed by median value of graduation year i.e 2013. 
* In GradAge feature, neglected student with GradAge<19 and GradAge>29 by logic. 
* Imputed missing values in 12board and 10board features with cbse as most of the students were appearing from cbse board.
* There were 340 unique boards in 12board and 275 unique boards in 10board available, but the most frequent boards were “cbse”, “state” and “icse”, so converted 12board and 10board into 3 groups which are : “cbse”, “state” and “icse” boards.
* As records of students having MCA, Mtech, Msc degree were less so combined them under one category as 'PG' and B.Tech/B.E. under ‘UG’ degree. 
* Divided 25 different CollegeStates feature into 3 zones : 'North_Zone.', 'South_Zone.', 'Other_Zone.' 
* Created 3 bins based on collegeGPA , 12percentage and '10percentage' features as 0, 1 and 2 [0- low marks (33 to 59), 1-medium marks (60 to 74) and 2-High marks (75 to 100)] 
* Created dummy data for categorical variables such as Specialization, CollegeState, Gender, Degree, 12board, 10board, CollegeTier, CollegeCityTier.(One Hot Encoding)
* Applied linear,ensemble and  tree based modelling : Logistic Regression, Descision Tree Classifier, Random forest Classifier, Adaboost Classifier, XGBoost Classifier,
Voting Classifier(Soft Voting) etc.
* Gradient Boosting Classifier gave the best score !

BUSINESS IMPACT:
* The business use case was to come up with a Machine Learning model which could predict the salary of an engineering graduate joining in the near future, using the list of features mentioned in the dataset such as degree, specialization, gender, college tier etc.

Thanks!!
