## Course Project - Getting and Cleaning Data Project

Description on prerequisites and how to run run_analysis.R to get clean tidy data set

##Note1: 

To run this project run_analyis.R available in your current working directory 
and data should be available under 'data' folder in you current working directory.......

Follow two steps below to get the clean tidy dataset..............

Step1:  Download the data from link https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip 
        Once download is complete, unzip the folder getdata-projectfiles-UCI HAR Dataset.zip
        You will get one more folder inside this named "UCI HAR Dataset"
        copy the contents of "UCI HAR Dataset" folder, make a separate directory called data in your current 
        working directory and paste copied contents.

Step2: Run R Command > source(run_analysis.R) at command prompt

## The cleanup script (run_analysis.R) does the following:

1. Merges the training and the test sets to create one data set.
2. Extracts only the measurements on the mean and standard deviation for each measurement. 
3. Uses descriptive activity names to name the activities in the data set
4. Appropriately labels the data set with descriptive activity names. 
5. Creates a second, independent tidy data set with the average of each variable for each activity and each subject. 

## Process followed by run_analysis.R script

1. For both the test and train datasets, produce an interim dataset:
    1. Extract the mean and standard deviation features (listed in CodeBook.md, section 'Extracted Features'). This is the `values` table.
    2. Get the list of activities.
    3. Put the activity *labels* (not numbers) into the `values` table.
    4. Get the list of subjects.
    5. Put the subject IDs into the `values` table.
2. Join the test and train interim datasets.
3. Put each variable on its own row.
4. Rejoin the entire table, keying on subject/acitivity pairs, applying the mean function to each vector of values in each subject/activity pair. This is the clean dataset.
5. Write the clean dataset to disk.

## Cleaned Data

The resulting clean dataset is in this repository at: `data/cleaned.txt`. It contains one row for each subject/activity pair and columns for subject, activity, and each feature that was a mean or standard deviation from the original dataset.

## Note2

X_* - feature values (one row of 561 features for a single activity)
Y_* - activity identifiers (for each row in X_*)
subject_* - subject identifiers for rows in X_*
