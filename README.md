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

Step 6: 


