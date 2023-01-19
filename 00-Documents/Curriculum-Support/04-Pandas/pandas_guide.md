
## Suggestions about Pandas HW:
  *  Do the PyCitySchools version - everything is already setup for it in the readme and its easy to understand the purpose.  

  *  In the Starter file, it shows the output of each cell so you have all the answers and it is just the case of figuring out the appropriate command.  When I do this activity, I go to the last line of each cell and split the cell so when I run the cell, it gives me results below my cell but the provided answers don't get erased.  Then I can compare the two outputs to see if I got everything correct.  

  *  Here is an outline of each section of PyCitySchools
      *  `District Summary`: Single Value from Simple Column Operations, Single Value from Column Operations with Conditionals, creating dataframe with Dictionary of lists (in this case the list is a single value in a list).  
      *  `School Summary`:  List of Values from Column Operations with Conditionals, Lots of data grouping calculations, creating dataframe with Dictionary of Lists and formatting columns.  
      *  `Top Performing Schools`:  Sorting prior df
      *  `Bottom Performing Schools`:  Sorting prior df
      *  `Math Scores by Grade`:  List of Values from Column Operations with Conditionals, more data grouping calculations
      *  `Reading Scores by Grade`:  Basically the same as above
      *  `Scores by School Spending`:  Data binning, grouping data, creating dataframe from dictionary of lists
      *  `Scores by School Size`:  Basically the same as above
      *  `Scores by School Type`:  Uses previous dataframes, grouping data, creating dataframe from dictionary of lists.  

As you can see, a lot of the calculations are the same type just used in different ways all performed on the same dataset.  When I have time I will list the key activities, but after the next class, you can probably do about 50% of the homework.  Day 2 includes grouping and sorting. Day 3 is about merging (not needed for homework, the merge is done for you in the first cell), binning and formatting.  

## Key Activities:  

*  `Single Value from Simple Column Operations`:   Day 1 Activity 11
*  `Creating Dataframe from Dictionary of Lists`:  Day 1 Activity 11  
*  `Column Operations with Conditionals`:  Day 2 Activity 02  
*  `GroupBy`:  Day 2 Activity 6 (plus other good examples similar to homework on Day2/3)
*  `Sorting`:  Day 2 Activity 8  
*  `Binning`: Day 3 Activity 3  
*  `Formatting`:  Day 3 Activity 5  

I also like the overviews found in the Supplemental Folder.


`Note About Pandas HW`:  You will see several instructions about % overall passing (the percentage of students who passed math AND reading) in the readme instructions.  Keep in mind that this instruction wants you to use the column that you already created for 'overall passing' and not doing a new calculation of taking (% pass reading + % pass math)/2.  These will be different because 'overall passing' represents the students that have both passing scores in both subject areas - this means that %overall will always be less than both individual percentages for reading and math % passing.  If this is confusing then you can see me in the office hours.