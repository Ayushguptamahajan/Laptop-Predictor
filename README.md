# Laptop-Predictor
Laptop price prediction end to end project (Regression problem)
The summary of the steps executed in above ML model are:

1. Data collection and overview of the dataframe:
    - The data was extracted from the csv file downloaded from kaggle.
    - Data contains 1303 rows and 12 feature.
    - Target feature is price (Prediction feature of ML model).
    - Data contains 9 categorical features and 3 Numerical features.
    - No duplicated rows and null(*nan*) values were found in the given data set.
    - Post above overview categorical feature count of unique values were viewed (Memory, Cpu and Gpu were having various information in combination form which need to be extracted in feature engineering stage).

2. Check for Missing and outliers:
    - There were no missing values in the given dataframe.
    - Outliers were present in Inches and Price features. Considering that they might help in training model, the same was not removed from the dataset.
    
3.Exploratory Data Analysis:
- Univariate Analysis:
    - Dist and QQ plot was ploted for numerical columns which depicted none of the numerical columns are normally distributed. Reason being presence of outliers.
    - Count plot was plotted for categorical columns depicting various categories present in each categorical column.

- Bivariate and Multivariate Analysis:
    - Numerical feature barplot was ploted against the targeted feature (price).
    - Categorical feature scatterplot was ploted against the targeted feature (price).
    - Heatmap was ploted for the numerical features to inference the relation of targeted feature (price).
4.Feature Engineering:
- Feature extraction and construction:
    - Ram and Weight column numerical value was extracted by dropping the units and finally datatype of the column was converted to int/float. Further countplot and barplot was plotted for ram feature for inferencing the trend and relation with price. Distplot was also plotted for weight feature against the targeted feature (price).
    - Screenresolution feature was having data like touchscreen, IPS and resolution. Extracting these information seperately will increase the efficeincy of the model. So the same was extracted from screen resolution feature. Also on extraction the ResX and ResY was having equal corelation with the targeted column. So i decided to combine the feature ResX, ResY and inches and construct a new feature ppi (pixel per inch) which will decrease the size of dataset and increase the effieciny of final model.
    - CPU feature contains the information of processing unit along with GHZ. Since presence of GHZ will not effect much on the final model. Self decided to reduce the categories of cpu feature to intel i3, intel i5,intel i7, other intel and AMD processors which will definately provide good r2 score to the final model. Countplot and barplot was plotted to visualize the CPU features.
    - Feature extraction and construction was done on os column to catogries the all os in categories like window, mac and others which will generalise our result and give better efficiency to model. 
    - Feature extraction and construction was done on os column to catogries the all gpu in categories like nivedia, AMD, ARM and intel which will generalise our result and give better efficiency to model.
    - Further feature extraction and construction was done on memory column to extract the memory space of each SSD, HDD, Flash_storage and Hybrid with help of string functions. On extraction it was found that the correlation of Flash_storage and Hybrid was least with targeted feature (price), so the same was dropped out.
    - Feature scaling on all features and OHE on categorical feature was runned in view of getting best model results. 
    
5. Model construction:

Model used for the above final featured dataframe was :
- LinearRegression.
- RandomForestRegressor.
- Lasso.
- KNeighborsRegressor.
- Decision_tree.

Performance parameter used are accuracy, r2_score since the problem was regression problem.

All above model was runned with various parameter to get the best model with best hypertunned parameters. 

6. Conclusion:

- Randon forest comes out to be the best model for prediction of price of laptop with given features having an accuracy of result upto **~89%.**     
