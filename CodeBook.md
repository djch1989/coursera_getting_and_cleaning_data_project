The run_analysis.R script performs the data preparation which is followed by the 5 steps required as described in the course project’s definition on Coursera's Getting and Cleaning Data course.

1. Download the dataset 

Dataset downloaded and extracted under the folder called UCI HAR Dataset

2. Assign each data to variables 
features <- features.txt : 561 rows, 2 columns 
The features selected for this database come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
activity_labels <- activity_labels.txt : 6 rows, 2 columns 
List of activities performed when the corresponding measurements were taken and its codes (labels)
subject_test <- test/subject_test.txt : 2947 rows, 1 column 
contains test data of 9/30 volunteer test subjects being observed
x_test <- test/X_test.txt : 2947 rows, 561 columns 
contains recorded features test data
y_test <- test/y_test.txt : 2947 rows, 1 columns 
contains test data of activity_labels’ code labels
subject_train <- test/subject_train.txt : 7352 rows, 1 column 
contains train data of 21/30 volunteer subjects being observed
x_train <- test/X_train.txt : 7352 rows, 561 columns 
contains recorded features train data
y_train <- test/y_train.txt : 7352 rows, 1 columns 
contains train data of activity_labels’ code labels

3. Merges the training and the test sets to create one data set 
X (10299 rows, 561 columns) is created by merging x_train and x_test using rbind() function
Y (10299 rows, 1 column) is created by merging y_train and y_test using rbind() function
Subject (10299 rows, 1 column) is created by merging subject_train and subject_test using rbind() function
Merge_Data_Sets (10299 rows, 563 column) is created by merging Subject, Y and X using cbind() function

4. Extracts only the measurements on the mean and standard deviation for each measurement 
TidyDataSet (10299 rows, 88 columns) is created by subsetting Merge_Data_Sets, selecting only following columns: subject, code and the columns containing the mean and standard deviation (std) for each measurement

5. Uses descriptive activity names to name the activities in the data set 
Entire numbers in code column of the TidyDataSet replaced with corresponding activity taken from second column of the activity_labels variable

6. Appropriately label the data set with descriptive variable names 
code column in TidyDataSet renamed into activities
All Acc in columns’ names replaced by Accelerometer
All Gyro in columns’ names replaced by Gyroscope
All BodyBody in columns’ name replaced by Body
All Mag in columns’ name replaced by Magnitude
All start with character f in columns’ name replaced by Frequency
All start with character t in columns’ name replaced by Time

7. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject 
FinalTidyDataSet (180 rows, 88 columns) is created by sumarizing TidyDataSet taking the means of each variable for each activity and each subject, after grouping by subject and activity.
Export FinalTidyDataSet into FinalTidyDataSet.txt file.