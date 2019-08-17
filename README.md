# DataScienceTutorial
Data Science Tutorial from Data Con LA 2019

Deep Learning - Supervised and Unserpervised 

Predicting Customer Churn by using Hands on practices and Machine Learning

-------------------------------------


Standard Data Science Process
    Business Objective
        Data Acquisition
            Data Analysis and preparation
                Model   
                    Evaluation
                        Implementation

If you find yourself with a high error rate (eg: 20-30%) You need more Data.
    If youre unable to get more data then go outside your organization and bring in outside data (public data)
        Repeat process
            If your error rate is still on the high side (eg: 15%) at this point try and tweak the model or parameters. (10% error rate is usually about the highest you should have).

https://www.thedevmasters.com/dataconla <-- Where we are getting the Data to work with (Customer Telecom Churn)



Using Cocalc/Jupityr NoteBook IDE

---- https://cocalc.com/projects/c7753a73-1e2f-42a9-99e0-1a6762f1e9fa/files/2019-08-17-150313.ipynb?session=default ----


Step 1: Import Libraries 
    import pandas as pd
    import matplotlib.pyplot as plt
    %matplotlib inline

Step 2: Allow cocalc to read the data from Excel file *data = pd.read_excel('Customer_Telecom_Churn.xls')*

Step 3: Data.head()

Step 4: Pull Down Column Names *Data.info()*

Step 5: *data['State'].nunique()* 51

Step 6: Descriptive Statistics Summary *Data.Describe()*

Step 7: Correlation between different columns *data.corr()*

Step 8: Filter to show just churn *data.corr()['Churn'].sort_values()*

Step 9: *plt.hist(data['Account Length'], bins=50);*

Step 10: Look at churn rate based on Account Length *plt.scatter(data['Account Length'], data['Churn'])*

Step 11: Look at churn rate based on Customer Service Calls *plt.scatter(data['CustServ Calls'], data['Churn'])*

Step 12: Look at churn rate based on phone call usage during times of the day *data.groupby('Churn').mean()[['Day Mins', 'Eve Mins', 'Night Mins']].plot(kind='bar')*

Step 13: 3D graphs *from mpl_toolkits import mplot3d

fig = plt.figure()
ax = plt.axes(projection='3d')*

Step 14:*y = data.Churn*
        *x = data[['CustServ Calls', 'Account Length','Day Mins']]*
        *x.info()*

Step 15: Set Up/Train Algorithm
         *from sklearn.tree import DecisionTreeClassifier*
         *t = DecisionTreeClassifier()*
         *t.fit(x,y)*

Step 16: t.predict([[1,90,100]]) (Number of CustServ calls, Account Length, Num of Mins) Have algorithm predict if they will churn
            -Algorithm Predicts the customer wont leave-

Step 17: Test/Evaluate algorithm against previous cases

(Predict on X data frame) then compare with originals

Step 18: *t.feature_importances_* will show you importance of different features

Step 19: *x.columns*
    Index(['CustServ Calls', 'Account Length', 'Day Mins'], dtype='object')

Step 20: *list(t.predict(x))* Allow algorithm to predict whether customers will leave

Step 21: check accuracy 
        Import Accuracy *from sklearn.metrics import accuracy_score*
        Check Accuracy *accuracy_score(y,t.predict(x))*

Step 22: Create Test Database
        *from sklearn.model_selection import train_test_split
        x_train, x_test, y_train, y_test = train_test_split(x,y, test_size=.25, random_state=0)*

Step 23: How many Rows vs. Columns 
        *x_train.shape, y_train.shape, x_test.shape, y_test.shape*

Step 24: Run Algorithm and test it
            Modeling
        *t_r = DecisionTreeClassifier()
         t_r.fit(x_train,y_train)*

Step 25: 