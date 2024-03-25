The Goal of the script is to:
Analyse the area-wide standardised test results to aggregate 
the data and showcase obvious trends in school performance.

Raw Data includes every student's information on:
Student ID, name, gender, year,	school,	reading score, maths score, 
School ID, school type, school size (No. students) and school budget.

Data Files: The script uses two CSV files, schools_complete.csv and students_complete.csv, located in the Resources folder.

The script uses the following dependencies:
	pandas: For data manipulation and analysis.
	pathlib: For handling file paths.




LOGIC:
Data Loading and Merging:

Reads school and student data from CSV files using pandas.
	Merges all data into a complete dataframe, combined on 'school_name', 
	meaning there will be repeat values for all values within the school_data added to school_data_complete. 
i.e. (school_name, School ID, type, size, budget).

Calculates total schools,
Total number of unique schools:
    Use nunique() as there is many repeat values for school_name in the school_data_complete.

total students;
Total number of students, unlikely but some students may have the same name:
	Use .count() to count the student names.

Total budget;
The budget column value, refers to the budget for each school. Assuming We know the budget for two schools are not the same.
Therefore the total budget: create Pandas data Series for the budget column, grab each unique value, sum those values.
 
Average scores; 
Create Pandas data for the 'maths_score' and 'reading_score' Column, find the mean of all values in that series.

and passing rates:
 Calculate the Percentage Pass Rates:
    1. Count how many students passed maths and reading and both, 
        Return a slice of the dataframe with rows that satisfy the condition(s) then, 
        count the number non-null values in the "student_name" column.

    2. Calculate percentages of the total students.

Calculate the Percentage Pass Rates
    1.Count how many students passed maths, reading and both for each school.   
       Groups the DataFrame by "school_name" column,
       select column, counts non-null values of student name columns in each group.
    
    2. Calculates the percentage from the school size and number of students passing.
Note: This could be done in one line of code, but for ease of readability, the steps have been broken into two lines.

Creates a summary DataFrame for the entire district.

Per School Summary:
	Extracts school types, sizes, budgets, and calculates per capita spending.
	Calculates average scores and passing rates for each school.
	Creates a summary DataFrame for each school.
	Top and Bottom Performing Schools:

Identifies the top and bottom performing schools based on passing rates.
Generates DataFrames with the top 5 and bottom 5 schools.

Calculates average math and reading scores for students in different school years.
Creates DataFrames for math and reading scores by year.

Categorizes schools based on spending per student into different spending ranges.
Creates a DataFrame with spending ranges.
