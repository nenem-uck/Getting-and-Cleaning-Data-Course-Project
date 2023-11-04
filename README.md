---
title: "Peer-graded Assignment: Getting and Cleaning Data Course Project"
---

## Dataset
[Human Activity Recognition Using Smartphones](https://archive.ics.uci.edu/dataset/240/human+activity+recognition+using+smartphones)

The data linked to from the course website represent data collected from the accelerometers from the Samsung Galaxy S smartphone. 

## Files
* `CodeBook.md`: the code book that describes the variables, the data, and any transformations or work that you performed to clean up the data 
* `tidy_data2.txt`: the tidy dataset exported by running 'r run_analysis.R'
* `run_analysis.R`: the R script that downloads and read the data set, then performs the following 5 steps 
    1. Merges the training and the test sets to create one data set.
    2. Extracts only the measurements on the mean and standard deviation for each measurement. 
    3. Uses descriptive activity names to name the activities in the data set
    4. Appropriately labels the data set with descriptive variable names. 
    5. From the data set in step 4, creates a second, independent tidy data set with the average of each variable for each activity and each subject.
