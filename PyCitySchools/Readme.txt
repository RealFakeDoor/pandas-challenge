Combine the data into a single dataset:
The data is combined on 'school_name', meaning there will be repeat values for all values within the school_data added to school_data_complete. 
i.e. (school_name, School ID, type, size, budget).

# Calculate the Totals (Schools and Students)

# Total number of unique schools:
    # Use nunique() as there is many repeat values for school_name in the school_data_complete.

# Total number of students, unlikely but some students may have the same name:

# Calculate the Total Budget:
# The budget column value, refers to the budget for each school. Assuming We know the budget for two schools are not the same.
# Therefore the total budget: create Pandas data Series for the budget column, grab each unique value, sum those values.

# Average maths score:  create Pandas data for the 'maths_score' Column, find the mean of all values in that series.

# Average reading score: create Pandas data for the 'reading_score' Column, find the mean of all values in that series.

# Calculate the Percentage Pass Rates:
    # 1. Count how many students passed maths and reading and both, 
        # Return a slice of the dataframe with rows that satisfy the condition(s) then, 
        # count the number non-null values in the "student_name" column.

    # 2. Calculate percentages of the total students.

#  Calculate the Percentage Pass Rates
# 1.Count how many students passed maths, reading and both for each school.   
    # Groups the DataFrame by "school_name" column,
    # select column, counts non-null values of student name columns in each group.
# 2. Calculates the percentage from the school size and number of students passing.
# Note: This could be done in one line of code, but for ease of readability, 
#       the steps have been broken into two lines.

