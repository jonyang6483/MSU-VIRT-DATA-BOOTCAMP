# Unit 4 Homework: Pandas, Pandas, Pandas
In this assignment, you’ll create and manipulate Pandas DataFrames to analyze school and standardized test data.


## Before You Begin

1. Create a new repository for this project called `pandas-challenge`. **Do not add this homework to an existing repository**.

2. Clone the new repository to your computer.

3. Inside your local Git repository, create a folder for this homework assignment and name the folder `PyCitySchools`.

4. Add your Jupyter notebook to this folder. This will be the main script to run for analysis.

5. Push these changes to GitHub or GitLab.



## Background

Having spent years analyzing financial records for big banks, you've finally scratched your idealistic itch and joined the education sector. Your latest role is Chief Data Scientist for your city's school district. In this capacity, you'll be helping the school board and mayor make strategic decisions regarding future school budgets and priorities.

As a first task, you've been asked to analyze the district-wide standardized test results. You'll be given access to every student's math and reading scores, as well as various information on the schools they attend. Your task is to aggregate the data to showcase obvious trends in school performance.

## Instructions

Using Pandas and Jupyter Notebook, create a report that includes the following data. Your report must include a written description of at least two observable trends based on the data.

**Hint:** Check out a [sample solution](Instructions/Starter_Code/PyCitySchools/PyCitySchools_starter.ipynb) to review the desired format for this assignment.

### District Summary

Create a high-level snapshot, in a DataFrame, of the district's key metrics, including the following:

* Total schools
* Total students
* Total budget
* Average math score
* Average reading score
* % passing math (the percentage of students who passed math)
* % passing reading (the percentage of students who passed reading)
* % overall passing (the percentage of students who passed math AND reading)

### School Summary

Create a DataFrame that summarizes key metrics about each school, including the following:

* School name
* School type
* Total students
* Total school budget
* Per student budget
* Average math score
* Average reading score
* % passing math (the percentage of students who passed math)
* % passing reading (the percentage of students who passed reading)
* % overall passing (the percentage of students who passed math AND reading)

### Highest-Performing Schools (by % Overall Passing)

Sort the schools by `% Overall Passing` in descending order and display the top 5 rows.

Save the results in a DataFrame called "top_schools".

### Lowest-Performing Schools (by % Overall Passing)
Sort the schools by `% Overall Passing` in ascending order and display the top 5 rows.

Save the results in a DataFrame called "bottom_schools".

### Math Scores by Grade
Perform the necessary calculations to create a DataFrame that lists the average math score for students of each grade level (9th, 10th, 11th, 12th) at each school.

### Reading Scores by Grade
Create a DataFrame that lists the average reading score for students of each grade level (9th, 10th, 11th, 12th) at each school.

### Scores by School Spending
Create a table that breaks down school performance based on average spending ranges (per student).

Use the code provided below to create four bins with reasonable cutoff values to group school spending.

    spending_bins = [0, 585, 630, 645, 680]
    labels = ["<$585", "$585-630", "$630-645", "$645-680"]

Use `pd.cut` to categorize spending based on the bins.

Use the following code to then calculate mean scores per spending range.

    spending_math_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["Average Math Score"]
    spending_reading_scores = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["Average Reading Score"]
    spending_passing_math = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Passing Math"]
    spending_passing_reading = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Passing Reading"]
    overall_passing_spending = school_spending_df.groupby(["Spending Ranges (Per Student)"]).mean()["% Overall Passing"]

Use the scores above to create a DataFrame called `spending_summary`.

Include the following metrics in the table:

Average math score

Average reading score

% passing math (the percentage of students who passed math)

% passing reading (the percentage of students who passed reading)

% overall passing (the percentage of students who passed math AND reading)

### Scores by School Size

Use the following code to bin the per_school_summary.

    size_bins = [0, 1000, 2000, 5000]
    labels = ["Small (<1000)", "Medium (1000-2000)", "Large (2000-5000)"]

Use `pd.cut` on the "Total Students" column of the `per_school_summary` DataFrame.

Create a DataFrame called `size_summary` that breaks down school performance based on school size (small, medium, or large).

### Scores by School Type

Use the `per_school_summary` DataFrame from the previous step to create a new DataFrame called `type_summary`.

This new DataFrame should show school performance based on the "School Type".

### Submission
On [Bootcamp Spot](https://bootcampspot-v2.com), submit a link to the `pandas-challenge` repo that you created for this assignment. Be sure to include a `README.md` file in addition to the Jupyter Notebook that contains your report.


## References

Data generated by Mockaroo, LLC. (2022) Realistic Data Generator. [https://www.mockaroo.com/](https://mockaroo.com/). Modified by Trilogy Education Services, LLC.

- - -

© 2023 Trilogy Education Services, a 2U, Inc. brand. All Rights Reserved.
