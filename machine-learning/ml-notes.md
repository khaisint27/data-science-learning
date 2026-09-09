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

###Key Steps
1. Collect labelled data
Each input must have a correct output/label
2. Split the dataset 
Training data ~80% Testing data ~20%
3. Train the model
Feed training data (inputs and labels) into supervised learning algorithm
4. Validate and Test model
Evaluate model with testing data
Model prediction on testing data is compared to calculate accuracy and error
5. Deploy and Predict on New data
Once model performs well, novel data can be inputted

###Examples of Supervised ML Algorithms
1. Linear Regression
2. Logistic Regression
3. Decision Trees
4. Random Forests
5. k-Nearest Neighbours

###Advantages
- Easy to implement as it learns from labelled data
- High accuracy when enough labelled data is provided
- Can generalise well to unseen data with proper training and diverse dataset
- Widely used in applications like speech recognistion, medical diagnoses, and fraud detection
###Disadvantages
- Requires large amounts of labelled data -> expensive and time consuming to gather
- Can be biased if training data is unbalanced
- May overfit training data instead of learning general patterns
- Performance may dropif applied to data that is very diff to training data
- Not easily scalable for problems w/ v large number of labels

##Unsupervised
Type of ML in which the model works without labelled data. Patterns are learned by its own
Used for tasks like clustering, dimensionality reduction an Association Rule Learning
Helps identify patterns in data 
Useful for grouping, compression, and anomaly detection

###Steps
1. Collect unlabelled data
2. Select Algoirthm
3. Train model on raw data
4. Group or Transform data
Algo will organise data into groups, rules or lower dimensional form
5. Interpret and Use Results 
Analyse the discovered groups to gain insight e.g visualisation, anomaly detection

###Main Types
1. Clustering algos
Groups data into clusters based on similarity
Goal: To discover patterns or relationships without prior knowledge

2. Association Rule Learning
Used to discover interesting relationships between variables in large datasets
Identifies patterns in form of if-then rules

3. Dimensionality reduction
Decreases the number of features or variables while keeping as much of the original info as possible
Hleps simplify comples data for analysis or visualisation

###Advantages
- Works with raw unlabelled, saving time and effort required for annotation
- Finds hidden patterns 
- Handles large and complex datasets efficiently, including high dimensional data
- Help detects anomalies with unusual data points without needing prior examples

###Challenges
- Noisy data and outliers can distort patterns and reduce model effectiveness
- Model may capture noise instead of meaningful patterns -> leads to overfitting
- Lack of labelled data makes it difficult to guid algo towards specific outcome
- Results (e.g clusters) may be difficult to interpret or may not clearly match real-world categories

#scikit-learn
Open source ML library that supports supervised or unsupervised learning. Also provides various tools for model fitting, data processing, model selection, evaluation and others.