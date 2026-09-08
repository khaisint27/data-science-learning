#Machine Learning Notes
Machine Learning is a branch of Artificial Intelligence that allows computers to learn from data and make decisions without explicit programming

##Data Pre-processing
First step in any data analysis work or ML pipeline. Involves cleaning, transforming, and organising raw data to ensure its accurate , consistent and ready for modelling.

- Import libraries and load dataset

pandas, numpy, scikit learn, matplotlib, seaborn
df = pd.read_csv('name.csv')
df.head() #quick check if correct data is loaded

- Inspect data structure and Check for missing values

df.info() #Summary including count of null and non-null values & data type in each column
df.isnull().sum() #Returns number of missing values per column

- Statistical summary and Visualising outliers

df.describe() #Computes count, mean, standard dev, min/max, and quartiles
Then use box plots to visualise numerical data and detect outliters plt.boxplot()

- Remove Outliers using Interquartile Range

Values below Q1-1.5IQR or above Q3+1.5IQR can be considered outliers
Calculate lower and upper bounds for each column 
Then filter 

- Correlation Analysis

df.corr() #computes pairwise corrleation coefficients between columns
sns.heatmap(df.corr) visualises correlation matrix
Sorting correlations with corr['Outcome'].sort_values() highlights features most correlated with target

- Visualise Target Variable Distribution

Its important to check if target classes are balanced as they affect model training and evaluation
plt.pie

- Seperate Features and Target Variable

Seperate independent variables from depended Variable
x = df.drop(columns=[''])
y = df['']

- Normalisation and Standardisation
1. Normalisation (Min-Max Scaling)
Rescales to 0 -- 1. Good for algos like k-Nearest Neighbours and NN
MinMaxScaler from scikit learn
.fit_transform(): Learns min/max from data and applies Scaling
2. Standardisation
Transforms deatures to have mean=0 and SD=1
Useful for normally distributed values
StandardScaler from scikit learn

#Supervised vs Unsupervised ML

##Supervised
Type of ML in which the model learns from labelled data (i.e. correct output). It continuously compares with actual results and improve over time
- Classification
Output is categorical (yes or no, 0 or 1)
- Regression 
Output is continuous (e.g. stock prices)

