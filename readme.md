# Information on the Dataset and where it was downloaded

Raw data downloaded from this website:
https://d396qusza40orc.cloudfront.net/getdata%2Fprojectfiles%2FUCI%20HAR%20Dataset.zip


Data Set Information:

Human Activity Recognition Using Smartphones Data Set
Davide Anguita, Alessandro Ghio, Luca Oneto, Xavier Parra and Jorge L. Reyes-Ortiz. A Public Domain Dataset for Human Activity Recognition Using Smartphones. 21th European Symposium on Artificial Neural Networks, Computational Intelligence and Machine Learning, ESANN 2013. Bruges, Belgium 24-26 April 2013.

The experiments have been carried out with a group of 30 volunteers within an age bracket of 19-48 years. Each person performed six activities (WALKING, WALKING_UPSTAIRS, WALKING_DOWNSTAIRS, SITTING, STANDING, LAYING) wearing a smartphone (Samsung Galaxy S II) on the waist. Using its embedded accelerometer and gyroscope, we captured 3-axial linear acceleration and 3-axial angular velocity at a constant rate of 50Hz. The experiments have been video-recorded to label the data manually. The obtained dataset has been randomly partitioned into two sets, where 70% of the volunteers was selected for generating the training data and 30% the test data. 

The sensor signals (accelerometer and gyroscope) were pre-processed by applying noise filters and then sampled in fixed-width sliding windows of 2.56 sec and 50% overlap (128 readings/window). The sensor acceleration signal, which has gravitational and body motion components, was separated using a Butterworth low-pass filter into body acceleration and gravity. The gravitational force is assumed to have only low frequency components, therefore a filter with 0.3 Hz cutoff frequency was used. From each window, a vector of features was obtained by calculating variables from the time and frequency domain.

Check the README.txt file for further details about this dataset. 

A video of the experiment including an example of the 6 recorded activities with one of the participants can be seen in the following link: [Web Link]

An updated version of this dataset can be found at [Web Link]. It includes labels of postural transitions between activities and also the full raw inertial signals instead of the ones pre-processed into windows.


# Steps taken to Clean the data

# Part 1

File was unzipped and folder was extracted into the working directory.

Imported the "features.txt" file which contains the column labels for the "x" datasets

Changed working directory to UCI HAR Dataset/test folder which contains the test datasets.  Ignoring the "Inertial Signals" folder.

Read each file into R with read.table().  Note that each has 2947 rows/observations.

Changed working directory to UCI HAR Dataset/train folder which contains the train datasets. Ignoring the "Inertial Signals" folder.

Read each file into R with read.table().  Note that each has 7352 rows/observations.

Used the "features" text file to label the columns in the "x" datasets

Used rbind to add rows of "x" datasets together.

Merged train and test "lables" columns to each other.

Added "labels" column to total dataframe.  

Merged train and test "subject" columns to each other.

Added "subject" column to total dataframe.



# PART 2

Used grepl to search for "mean" and "std" within the "total" dataframe. Extracted those columns.



# PART 3

First converst the y_test and y_train sets to data frames, then converts the coded activity variables to the descriptive names given by the activity_labels.txt file.

Merges these sets in the order of train then test.  

Adds new "activity" column with descriptive names to the "total" dataframe.



# PART 4

This part was mostly already conducted in Part 1.  See part one for methods.

After part 5 in the code, cleaned up the column names a little bit by removing any abbreviations.



# PART 5

Melted the dataset and recast such that there are 6 rows to the dataset, one for each activity.  The mean value for each variable was taken for each activity and displayed.



