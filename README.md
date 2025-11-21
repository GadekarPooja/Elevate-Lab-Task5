# Elevate-Lab-Task5
Exploratory Data  Analysis(EDA)

Titanic Test Dataset

This project performs Exploratory Data Analysis (EDA), data preprocessing, data cleaning, and visualization on the Titanic test.csv dataset.
The goal is to understand the data, clean it, prepare it for modeling, and visualize important patterns.

A.Importing Libraries

You imported the following libraries:

pandas → to load and handle tabular data

numpy → for numerical operations

matplotlib / seaborn → for graphs


These libraries are essential for any data analysis project.

B. Loading the Dataset

You loaded the Titanic test.csv dataset into a DataFrame:

df = pd.read_csv("test.csv")


You checked:

df.shape → 418 rows × 11 columns

df.head() → first few rows

df.columns → list of column names

df.size → total number of elements

df.index → index range

This helped you understand the basic structure of the data.

C. Exploratory Data Analysis (EDA)
1.Checked data information using df.info()

This showed:

Which columns have missing values

What data types each column has

How many non-null values exist

2.Descriptive statistics using:

df.describe() for numerical columns

df.describe(include="object") for categorical columns

df.describe(include="all") for full view

You learned:

Mean age ≈ 30

Fare range is large (0 to 512)

Name column has all unique values

Sex has two categories

Cabin has many missing values

D.Handling Missing Values

You found missing values in:

Age → 86 missing

Fare → 1 missing

Cabin → 327 missing

Then you fixed them:

1.Filled missing Age with median
df['Age'] = df['Age'].fillna(df['Age'].median())

2.Dropped Cabin column

Too many missing values, so it was removed.

3. Filled missing Fare
df['Fare'] = df['Fare'].fillna(df['Fare'].median())


After this, the dataset had no missing values.

D.Data Cleaning & Preprocessing

You cleaned and standardized the data:

1Converted Age to integer

2 Converted Fare to float

3 Cleaned Name column (removed spaces)

4 Cleaned Ticket column (uppercased and trimmed)


5 Cleaned Sex column (capitalized “Male” / “Female”)

6 Checked duplicates (found 0 duplicates)

This step made the dataset consistent and readable.

E.Feature Engineering

You created new useful columns:

1.Age_Group

Child

Young

Adult

Senior

2. Status

Added a column where every row has "Active"

These new columns help in visualization and understanding patterns in the data.

F.Visualizations 

You used seaborn and matplotlib to visualize the dataset.

1️.Pairplot

Shows relationships between:

Age

Fare

Pclass

SibSp

Parch

Status

Observations:

Higher fares usually belong to higher classes

Younger people appear more in certain groups

Pclass 1 passengers paid more

2️.Histograms (Distribution Plots)

2.1 Age Distribution

Most passengers are aged 20–40 years.

2.2Fare Distribution

Fare is right-skewed — many low fares, a few extremely high fares.

2.3Age by Sex

Shows how male and female passengers are spread across ages.

3️. Boxplots

3.1Age vs Sex

Male and female have similar age ranges.

3.2Fare vs Pclass

Pclass 1 → expensive tickets

Pclass 3 → cheap tickets

Shows clear class differences.

4️ Scatterplots

4.1 Fare vs Age

Higher fare passengers are spread across all ages.

4.2 Pclass vs Age

Shows passengers from all ages in each class.
