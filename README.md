# Python_Skills

Following are my Python Skills:

Libraries: lxml, html5lib, beautifulsoup4, openpyxl, pickle

1. **Basics Python:**
   
(A) **Basics Python:**

  (i) Syntax and Semantics
  
  (ii) Single and Multi Line Commands

(B). **Variables:**
   (i) Declaring and Assigning Variables
   
   (ii) Naming Conventions
   
   (iii) Variable Types
   
   (iv) Type Checking and Conversion
   
   (v) Dynamic Typing

(C) . **Data Types:**

   (i) Basic Data Types: int, float, boolean, str
   
   (ii) Type Conversion

(D) . **Operators:**

   (i) Arithmetic Operators - Addition, Multiplication, Division, Floor Divison, Modulus, Exponential
   
   (ii) Comparison Operators - Equal to, Not equal to, Greater than, Lesser than, Greater than or equal to, Lesser than or equal to
   
   (iii) Logical Operators - AND, OR, NOT

(E). **Conditional Statements:**

   (i) if statement
   
   (ii) else statement
   
   (iii) elif statement
   
   (iv) Nested Conditional Statements

(F). **Loops:**
   (i) for Loop: Iterating over a string, Iterating over a range
   
   (ii) while Loop
   
   (iii) Loop Control Statements: break, continue, pass
   
   (iv) Nested Loops

2. **File Handling**:

   (i) File Operation - With Open (r-Read, w-Write,a-Append,wb-WriteBytes,w+ - Read and Write); file.write,file.writelines, file.seek(0) - Takes the cursor to the beginning while read and write.
   
   (ii) Working with File Paths - mkdir - Make Directory, listdir - List Directory, getcwd - Current Working Directory, path.exists - Check if path exists, .isfile - Check if it is a file, .isdir - Check if it is a directory, path.abspath - Gives Absolute path

3. **Exception Handling**:

  (i) Try, Except Block
  
  (ii) Try, Except, Else Block
  
  (iii) Try, Except, Else, Finally Block


48. **Python for Data Analysis:**

   (i) NumPy - (np.array), arr.reshape(1,5) - 2D will be in [[]], np.arrange(0,10,2).reshape(5,1) , np.ones ((3,1)), np.eye(3), 
   
   Universal Operations - arr1+arr2, arr1-arr2, arr1*arr2, np.sqrt(arr1), np.sin(arr1), np.log(arr), np.exp(arr)

   Array Slicing and Indexing - arr[0][0], arr[1:,2:], a[0][0]=100

   Statistical Concepts: Standardization and Normalization; np.mean(), np.median(), np.mode(), np.std(), np.var()

   Logical operation: data=np.array([1,2,3,4,5,6,7,8,9,10]); data[(data>=5) & (data<=8)]

   (ii) Pandas (DataFrame (2D) and Series (1D)) - pd.Series(data,index=index), pd.DataFrame(data), type(df['Name']) - Series, df.loc, df.iloc, df.at[1,'Age'], df.iat[2,2], df.drop('Salary',axis=1,inplace-True), df['Age']=df['Age']+1

   (iii) Data Analysis and Manipulation: Renaming Columns - df.rename(columns={'Date':'Sales Date'}); Change Datatypes - df[value_new]=df[value].astype(float); Lambda Function - df['Value_New']=df['Value'].apply(lambda x:x*2)

   Data Aggregattion and Grouping - grouped_mean=df.groupby('Product')['Value'].mean()  
                                    grouped_sum=df.groupby(['Product','Region'])['Value'].sum()
                                    groudped_agg=df.groupby('Region')['Value'].agg(['mean','sum','count'])

   Merging DataFrames: pd.merge(df1,df2,on="Key",how="inner")

   49. Read Data from Various Sources:

df=pd.read_json(StringIO(Data)), df.to_json(orient='index'), df=pd.read_csv(),df.to_csv(), df=pd.read_html(url) (Need 3 Libraries - 'lxml, html5lib, beautifulsoup4'), pd.read_html(url,match="Country",header=0)[0], pd.read_excel  (Need openpyxl), df_excel.to_pickle(), pd.read_pickle(), 
