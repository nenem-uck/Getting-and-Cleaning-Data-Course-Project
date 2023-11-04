---
title: "Code Book"
---
The `run_analysis.R` script downloads and reads the data set, then performs the five steps mentioned in the project outline. 

For information about the original Human Activity Recognition Using Smartphones dataset, please refer to the following link.

[Human Activity Recognition Using Smartphones](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)

1. **Download the data set from the given url.**
    * Download and extract the data set under the folder `UCI HAR Dataset`.

2. **Store the data in each columns by assigning variables accordingly**
    * `features` <- `features.txt`: 561 rows and 2 columns; List of all features, come from the accelerometer and gyroscope 3-axial raw signals tAcc-XYZ and tGyro-XYZ.
    * `activities` <- `activity_labels.txt`: 6 rows and 2 columns; Link the class labels with their activity name.
    * `x_test` <- `test/X_test.txt`: 2947 rows and 561 columns; Test set.
    * `y_test` <- `test/y_test.txt`: 2947 rows and 1 column; Test labels.    
    * `x_train` <- `test/X_train.txt`: 7532 rows and 561 columns; Training set.
    * `y_train` <- `test/y_train.txt`: 7532 rows and 1 column; Training labels.
    * `subject_test` <- `test/subject_test.txt`: 2947 rows and 1 column; test data from 9 out of 30 volunteers being observed.
    * `subject_train` <- `train/subject_train.txt`: 7352 rows and 1 column; each row identifies the subject who performed the activity for each window sample; range from 1 to 30.
    
3. **Merges the training and the test sets to create one data set.**
    * `X`: 10299 rows and 561 columns; created by merging `x_test` and `x_train` using **rbind()**
    * `Y`: 10299 rows and 1 column; created by merging `y_test` and `y_train` using **rbind()**
    * `subject`: 10299 rows and 1 column; created by merging `subject_test` and `subject_train` using **rbind()**
    * `merged_data`: 10299 rows and 563 columns; created by merging `subject`, `X` and `Y` using **cbind()**
    
4. **Extracts only the measurements on the mean and standard deviation for each measurement.**
    * `tidy_data`: 10299 rows and 88 columns; created by subsetting `merged_data`, selecting the columns `subject` & `code` and the mean `mean` and standard deviation `std` for each measurement
    
5. **Uses descriptive activity names to name the activities in the data set**
    * each numbers in the `code` column of `tidy_data` are replaced with related activity taken from the 2nd column of the `activities` columns.
    
6. **Appropriately labels the data set with descriptive variable names.**
    * the `code` column from `tidy_data` is named as `activities`.
    * Replace `Acc` in all columns' name by `Accelerometer`.
    * Replace `Gyro` in all columns' name by `Gyroscope`.
    * Replace `BodyBody` in all columns' name by `Body`.
    * Replace `Mag` in all columns' name by `Magnitude`.
    * Replace all column names started with character `f` by `Frequency`.
    * Replace all column names started with character `t` by `Time`.
    
7. **From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.**
    * `tidy_data2`: 180 rows and 88 columns; created by summarizing `tidy_data` (groupping by subject and activity, taking means of each variables for each activity and each subject); exported to `tidy_data2.txt`.
