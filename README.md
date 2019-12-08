# coursera_getting_and_cleaning_data_project
My submission for Getting and Cleaning Data project.
This repository is my submission for Getting and Cleaning Data course's project. It has the instructions on how to run analysis on the dataset downloaded 
from the link - https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip.

Files and their description:

1. CodeBook.md - a code book that describes the variables, the data sets, and work that was performed to clean up the data

2. run_analysis.R - It performs the data preparation which is followed by the 5 steps required as described in the course project’s requirement: 
	a. Merges the training and the test sets to create one data set.
 	b. Extracts only the measurements on the mean and standard deviation for each measurement.
	c. Uses descriptive activity names to name the activities in the data set
	d. Appropriately labels the data set with descriptive variable names.
	e. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.

3. FinalTidyDataSet.txt is the exported tidy data in final format after going through all the sequential steps as mentioned in above point.
