## ABOUT THE DATA 
The Dataset is about the bike purchase of people. It contains 100k records in it. This dataset captures detailed sales transactions for a bike store chain, featuring 100,000 unique records of bike sales. Each row represents a single sales transaction and includes information about the customer, bike model, sales details, and store location. The dataset can be used for various analyses, including sales trends, customer demographics, and performance evaluation of stores and sales personnel.

## DATA CLEARNING 
- CHECK FOR MISSING DATA 

    - identify missing values : 
        ```py 
        df.isnull().sum() # that is how we do it 
        ```
    - handle missing values : 
        - drop rows or columsn with missing values 
            ```py 
            df.dropna()
            ```
        - fill missing values with a specific value , mean , or median : 
            df.fillna(value)
            df['column_name'].fillna(['colmn_name'].mean())

- CHECK FOR DUPLICATES 
    - find duplate rows : 
        ```py 
        df.duplicated().sum()
        ```
    - drop duplicates : 
        ```py 
        df.drop_duplicates(inplace=True)
        ```

- CHECK FOR INCONSISTENT DATA 
    - ensure consistendy in categoreis or strings : 
        - user str.lower(),str.strip() to standardize string formattting . 
        ```py 
        df['column_name'] = df['column_name'].str.lower().str.strip()
        ```

- HANDLE OUTLIERS 
    -detect outliesr usng summary statistics: 
    ```py 
    df.describe()
    ```
    - remove or cap outliear based on business rules : 
    ```py 
    df = df[df['column_name'] < threashold_value]
    ```


- CONVERT DATA TYPES 
    -ensure columns have the correct data types: 
        df.dtypes 
    - convert data types if necessary : 
        ```py 
        df['column_name'] = df['column_name'].astype('int')
    

- CHECK FOR INCONSISTENT OR INVALID VALUES 
    - look for invalid or negative lues in numeric columns . 
    df[df['column_name'] < 0]
     - replace or remove invalid values : 
     ```py 
     df['column_name'] = df['column_name'].replace(invalid_value, np.nan)
     ```


- CHECK COLUMN NAMES 
    -stanardizze column names ( removing spaces or special charaters ): 
    ```py 
    df.columns = df.columns.str.replace(' ', '_').str.lower()
    ```

- NORMALIZE OR SCALE DATA ( IF NEEDED)
    - scale or normaize your numeric data for cerntin analyses especally in machine learning 
    ```py 
        from sklearn.preprocessing import StandardScaler

        scaler = StandardScaler()
        df[['column1', 'column2']] = scaler.fit_transform(df[['column1', 'column2']])
    ```

- HANDLE CATEGORICAL DATA 
    - convert categorical valiables to numeric (if needed)
    ```py 
    df = pd.get_dummies(df, columns=['categorical_column'])
    ```

    




