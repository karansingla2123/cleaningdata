The run_analysis.R script performs the data preparation and then followed by 5 steps required as descriped in the course project's definition.

Download the dataset Dataset downloaded and extracted under the colder called UCI HAR Dataset

Assign each data to variables feature <- features.txt: 561 R, 2 C The feature selected for this database come from the acclerometer and gyroscope 3-axiel raw signals tAcc-XYZ and tGyro-XYZ

activities <- activity_labels.txt: 6 R, 2 C List of activities performed when corresponding measurements were taken and its codes(labels)

subject_test <- subject_test.txt: 2947 R, 1 C contains test data of 9/30 volunteer test subjects being observed

x_test <- X_test.txt: 2947 R, 561 C contains recorded features test data

y_test <- Y_test.txt: 2947 R, 1 C contains test data of activities' code labels

subject_train <- subject_train.txt: 7352 R, 1 C contains train data of 21/30 volunteer subjects being observed

x_train <- X_train.txt: 7352 R, 561 C contains recorded features train data

y_train <- Y_train.txt: 7352 R, 1 C contains train data of activities' code labels

Merges the training and the test sets to create one data set. X(10299 R, 561 C) is created by merging x_train and x_test using rbind() function Y(10299 R, 1 C) is created by merging y_train and y_test using rbind() function Subject(10299 R, 1 C) is created by merging subject_train and subsject_test using rbind() function Merged_data(10299 R, 563 C) is created by merging Subject, Y, X using cbind() function

Extracts only the measurements on the mean and standard deviation for each measurement. TidyData(10299 R, 88 C) is created by subsetting Merged_Data, selecting the column: subject, code, contains("mean") and contains("std") using select() function

Uses descriptive activity names to name the activities in the data set. Entire number in code column of the Tidydata replaced with corresponding activity taken from second column of the activities variable

Apprpriately labels the data set with descriptive variable names. code column in Tidydata renamed into activity All Acc in column's name replaced by accelerometer All Gyro in column's name replaced by Gyroscope All BodyBody in column's name replaced by Body All Mag in column's name replaced by Magnitude All start with character t in column's name replaced by Time All start with character f in column's name replaced by Frequency

From the data set in step 4, creates a second, independent tidy data set with average of each variable for each activity and each subject. Finaldata( 188 R, 88 C) is created by summarizing Tidydata taking the means of each variable for each activity and each subject, after groupped by subject and activity Export Finaldata into Finaldata.txt file.
