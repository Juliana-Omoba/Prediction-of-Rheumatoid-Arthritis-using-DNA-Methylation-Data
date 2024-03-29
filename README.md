## Machine Learning Project: Prediction of Rheumatoid Arthritis using DNA Methylation Data


## Project Oveview

Our project aims to predict Rheumatoid Arthritis (RA) by analyzing DNA methylation datasets using advanced machine learning techniques. RA, a complex autoimmune disease, affects millions globally with chronic inflammation and joint damage. Leveraging cutting-edge algorithms, we'll uncover intricate patterns in DNA methylation, a key epigenetic factor in RA.

We'll explore high-dimensional genomic data, focusing on epigenetic changes linked to RA onset and progression. Using techniques like support vector machines and decision tree, we'll develop predictive models to detect subtle molecular signatures indicative of RA severity and susceptibility.

Our approach includes feature selection to identify informative DNA methylation markers, deepening our understanding of RA's biological mechanisms. Through rigorous cross-validation, we'll build robust models for accurate RA onset and progression forecasts.


### Data Sources
Genome-wide DNA methylation data extracted from peripheral blood leukocytes (PBLs). Samples, categorized as Rheumatoid arthritis patients or normal controls, provide the basis for analysis [Download here](https://www.ncbi.nlm.nih.gov/geo/query/acc.cgi?acc=gse428610. 


### Tools

- Machine Learning Algorithms:
    - Support Vector Machine (SVM)
    - Decision Tree (DT)
  
- Programming Language:
   - Python [Download here](https://www.python.org/)
 
### Data Cleaning/Preparation

During the preliminary stages of data preparation, the following tasks are executed:
- Data Loading and Inspection.
- Data Exploration / Analysis / Visualization
    - Explore Missing Values
    - Exploration of Individual Attributes: Verify the distribution of each attribute.
    - Outlier Identification
    - Explore Feature Correlation
 
### Data Preprocessing

The following preprocessing steps were performed:

- Data Loading: The dataset was loaded from a a pickle file by importing pickle using !pip3 install pickle5.
- Drop Unwanted Features: Those features that appeared twice and unwanted features were deleted.
- Renaming and Type Conversion: Attribute columns were renamed, and data types were converted to facilitate subsequent analysis.
- Missing Value Handling: Missing values were addressed using mean imputation, median imputation, and data interpolation techniques.
- Label Encoding: This was done to convert the categorical labels into numerical form.
- Capping Outliers: This was done to bound extreme values in a dataset to a specified threshold.
- Normalization using MinMaxScaler
- Data Splitting: Data spliting ratio of 70% for training and 30% for testing was employed. 


After conducting exploratory data analysis and feature importance assessments, we identified four distinct subsets of data for further analysis. Each subset is characterized by specific features and preprocessing steps:

    - Subset 1:
        * Features: This subset includes most of all the available features.
        * Preprocessing: No outlier capping or normalization was performed.
        
    - Subset 2:
        * Features: Same as Subset 1.
        * Preprocessing: Outlier capping was applied to mitigate the influence of extreme values.
        
    - Subset 3:
        * Features: Similar to Subset 1.
        * Preprocessing: No outlier capping, but the data was normalized to enhance comparability between features.
        
    - Subset 4:
        * Features: Consistent with Subset 1.
        * Preprocessing: Outlier capping was performed, and the data was normalized to ensure consistent scaling across features.

    
### Perform a comparative analysis of various machine learning model performances
- Two machine learning algorithms were used: decision tree and svm
- Implement feature selection using chi2
- Implementing cross validation with hypertuning to find best parameter for each model


### Result

The table presented below illustrates a comparative analysis of accuracy results across four subsets of data applied to two machine learning algorithms: Support Vector Machine (SVM) and Decision Tree (DT). Across all subsets, SVM consistently outperforms DT in terms of accuracy. Notably, Subset 4 exhibits the highest overall performance, underscoring the substantial impact of outlier capping and dataset normalization. These findings underscore the effectiveness of preprocessing techniques in enhancing model performance and highlight SVM as a preferred algorithm for predictive tasks on this dataset.


<img src = "ResultsComparison.png">

Furthermore, the table provided below presents the classification report and confusion matrix of the optimal data subset, Subset 4, for the Support Vector Machine (SVM) algorithm. The confusion matrix indicates that 84.5% of the data are accurately classified as True Positive and True Negative.

<img src = "SVMresult.png">

### Summary of Findings
- This research commenced with the loading of two patient data files containing DNA methylation data, disease status, gender, age, and smoking status features.

- Through Exploratory Data Analysis (EDA), we meticulously examined data balance, null values, outliers, data types, and distributions. Visualizations were crafted to unravel insights and comprehend the data better.

- During the initial phase of feature selection, redundant features such as dataset, GEO accession, and duplicate age & gender columns were logically eliminated.

- Preprocessing methods were diligently applied to handle null values, outliers, and normalization. To identify the most effective data handling approach, we split the data into four stages for training/testing.

- The dataset was partitioned into training and testing sets, allocating 70% for training and reserving 30% for testing/evaluation purposes.

- Subsequently, in the second feature selection stage, we utilized chi-squared scores with scikit-learn's feature selection and selectKbest to select the most relevant features.

- Two algorithms, namely Decision Tree and Support Vector Classifier (SVC), were chosen for evaluation. Grid-search with cross-validation was conducted to determine the optimal parameters for each algorithm.

- Training was carried out using the best parameters obtained from the grid-search process. The models were then evaluated on the test data using accuracy scores and confusion matrices. Additionally, the top five features of importance for each of the four data subsets were analyzed. This analysis revealed that the preprocessing method significantly influences which features have the most impact on predictions, particularly normalization.

- Through our evaluations, we found that the SVC algorithm generally outperforms the Decision Tree algorithm in predicting disease status. By employing outlier capping and normalization techniques, we achieved an accuracy score of 84.5% and precision & recall scores of 84%.








