Machine Learning Models for Student Exam Scores Predictions

Name: Saul Evora
Date: 4/13/2026

Description: Machine learning models for student performances predictions contains three different models that are used to predict student exam performances. Those three models are Logistic Regression, Random Forest and Neural Network. This program is designed to run on a Python programming software called “Google Colab.”

Usability:
	
NOTE: Before even starting the program, make sure you have a dataset titled 	“student_habits_performance.csv”, which can be acquired from Kaggle. Ideally, the program works 	on that specific dataset. Copy and paste the following link to a web browser search engine to 	access and download the dataset from Kaggle:

	**************************************LINK #1***************************************************
	
	https://www.kaggle.com/datasets/nasasiratomowen/student-habits-performance-csv?resource=download

	**************************************LINK #1***************************************************

      STEPS:
	
      	 NOTE: Once you've prepared your dataset, there are configurations that must be made before          	 executing the program.
	
	 1. Enter your values for test size, epoch and batch size. Such entries are accepted in codes 	 	    that should look like this:

	 *******************************EXAMPLE #1***************************************************

	 # ****************************
	 # Main method
	 # ****************************

	 	test_size_value = 0.3
    	 	epochs_value = 50
   	 	batch_size_value = 10

	 *******************************EXAMPLE #1***************************************************
	 
	 What are the codes supposed to mean? 
		
	 As shown in the examples, the test size is entered as a decimal value, which represents the 	 	 percentage of how much of the dataset the models will be tested on. If a user enters “0.3”, 	 	 then 30 percent of the dataset will be used to test the models’ predictions and the remaining 70 	 percent of the data are what the models are going to train on. As for epochs and batch size 	 	 values, 50 for epochs value means Neural Network model will train on the entire dataset 50 times 	 while the batch size value of 10 means the model will train on 10 observations from the dataset 	 at a time.

	 NOTE: Run the program as many time as necessary to monitor optimal results of the models after
	 making several configurations on those three inputs.

	 2. At this point, the program is ready for execution, but there are two different alternatives 	 on how to import the dataset and users must choose ONLY ONE method.

	 ***************************************
	 ALTERNATIVE #1 (MANUAL dataset upload):
	 ***************************************
	
	 This method allows users to browse through file explorer on their computers to locate the 	 	 dataset to import. The following codes are responsible for this action:

	 *******************************EXAMPLE #2***************************************************

	 # ***********************
	 # Loading dataset
	 # ***********************

	 def load_dataset_man():
    		from google.colab import files
    		uploaded = files.upload()
    		file_name = list(uploaded.keys())[0]
    		df = pd.read_csv(file_name)
    		return df

	 # ****************************
	 # Main method
	 # ****************************

		# Uncomment the following code if you want to MANUALLY select the file
    		# in your computer.

	 	df = load_dataset_man()

	 *******************************EXAMPLE #2***************************************************

	 NOTE: In order to make this method operational, users must ensure that the calling method 	 	 located in the main method section is uncommented and the other calling method (covered in 	 	 ALTERNATIVE #2) is commented to prevent complications.

	 1. Execute the program.
	 
	 2. Click "choose files" button located at the bottom of the program.

	 3. Locate and select the dataset in your file explorer.

	 At this point, the program is processing the dataset and then outputs the results of the models' 	 performances in the form of accuracy scores, training time and confusion matrix. After all the 
	 models displays their results, there will be a bar graph at the very end of the output showing		 the accuracy scores of the models. Further details of the results is covered in the EXPECTED 	 	 OUTPUT OF THE PROGRAM section of this document.

	 If you want to switch from using this method to the one from ALTERNATIVE #2:
	
		1. Click on "Runtime" tab.
	
		2. Click "Disconnect and delete runtime."

	 The program will reset to its default setting as if users opened the program file for the first 	 time and a new method can be selected. Not doing this and then executing the program will make 	 the program think that you're still using the previous method.


	 ******************************************
	 ALTERNATIVE #2 (AUTOMATIC dataset upload):
	 ******************************************
	
	 This method requires users to have the file of the program and the dataset in the SAME 	 	 folder to allow the program to easily access the dataset without the need of long file 	 	 directories. The following codes are responsible for this action:

	 *******************************EXAMPLE #3***************************************************

	 # ***********************
	 # Loading dataset
	 # ***********************

	 def load_dataset_auto():
         	from google.colab import drive
                drive.mount('/content/drive')

        	df = pd.read_csv('/content/drive/Data Mining ML Project/student_habits_performance.csv')

	 # ****************************
	 # Main method
	 # ****************************

    	 	# Uncomment the following code if you want to ALLOW Google have
    	 	# FULL ACCESS to your Google Drive by simply entering the file directory.

   	 	df = load_dataset_auto()

	 *******************************EXAMPLE #3***************************************************

	 Notice that the name of the folder where the program was originally located is named “Data 	 	 Mining ML Project.” The name of the folder can be named something else, but users MUST ensure 	 	 that however the folder is named is in the same position where “Data Mining ML Project” is 	 	 placed in the directory as shown in the example. Which means if a user chooses to name the 	 	 folder “ML Project”, then the directory would need to be “/content/drive/ ML Project 	 	 	 /student_habits_performance.csv'”

	 NOTE: In order to make this method operational, users must ensure that the calling method 	 	 located in the main method section is uncommented and the other calling method (covered in 	 	 ALTERNATIVE #1) is commented to prevent complications.

	 1. Execute the program.

	 2. There will be a pop-up box that will ask for permission for the program to have full 	 	 access to your Google Drive files. If you choose this method, click "connect to Google Drive" 		 and it'll access the dataset based on the provided directory.

	 At this point, the program is processing the dataset and then outputs the results of the models' 	 performances in the form of accuracy scores, training time and confusion matrix. After all the
	 models displays their results, there will be a bar graph at the very end of the output showing		 the accuracy scores of the models. Further details of the results is covered in the EXPECTED 	 	 OUTPUT OF THE PROGRAM section of this document.

	 If you want to switch from using this method to the one from ALTERNATIVE #1:
		
		1. Click on "Runtime" tab.
	
		2. Click "Disconnect and delete runtime."

	 The program will reset to its default setting as if users opened the program file for the first 	 time and a new method can be selected. Not doing this and then executing the program will make 	 the program think that you're still using the previous method.

	 ******************************
	 EXPECTED OUTPUT OF THE PROGRAM
	 ******************************

	 At this point, the program has successfully finished its execution. The output of the program 	 	 should look like this:

	 *******************************EXAMPLE #4***************************************************

	 Total dataset size: 1000
	 Training data size: 700
	 Testing data size: 300

	 ********************************
    	     Experiment Configuration
	 ********************************

	 Test Size: 30%
	 Epochs: 50
	 Batch Size: 10

	 *************************
   	    Logistic Regression
	 *************************

	 Training time (s): 0.016
	 Accuracy: 0.79
	 Confusion matrix:

 	 [[117  30]
 	 [ 33 120]]

	 *************************
	       Random Forest
	 *************************

	 Training time (s): 1.216
	 Accuracy: 0.7567
	 Confusion matrix:

 	 [[115  32]
 	 [ 41 112]]

	 *************************
	      Neural Network
	 *************************

	 Training time (s): 14.757
	 Accuracy: 0.7967
	 Confusion matrix:

 	 [[117  30]
 	 [ 31 122]]

	 ***********************
	 Bar graph shown here!!!
	 ***********************

	 *******************************EXAMPLE #4***************************************************

	 Training time represents how long did the models trained on the dataset, accuracy represents the 	 models' test accuracies of their predictions, and the confusion matrix summarizes the models' 
	 true or false negatives and positives in a table. The confusion is structured as “[[TN, FP],[FN, 	 TP]]” and they represent:

	 TN -> “true negative” shows the model accurately predicted an item was labeled incorrectly
	 FP -> “false positive” shows the model inaccurately predicted an item was labeled correctly
	 FN -> “false negative” shows the model inaccurately predicted an item was labeled incorrectly
	 TP -> “true positive” shows the model accurately predicted an item was labeled correctly

	 Record the results.

******************************
END OF README TEXT DOCUMENT!!!
******************************

