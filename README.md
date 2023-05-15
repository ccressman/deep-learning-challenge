Overview: 
This project leverages SKLearn and TensorFlow Python libraries to construct and deploy a neural network (Keras Sequential Model) designed to predict the potential success of organizations applying for funding opportunities. The dataset analyzed includes data for more than 34,000 organizations across the below metrics: 


• EIN and NAME—Identification columns

• APPLICATION_TYPE—Alphabet Soup application type

• AFFILIATION—Affiliated sector of industry

• CLASSIFICATION—Government organization classification

• USE_CASE—Use case for funding

• ORGANIZATION—Organization type

• STATUS—Active status

• INCOME_AMT—Income classification

• SPECIAL_CONSIDERATIONS—Special considerations for application

• ASK_AMT—Funding amount requested

• IS_SUCCESSFUL—Was the money used effectively



Results: 


BASE MODEL

• Model's target variable:  

	• IS_SUCCESSFUL
• Features deemed ancillary and removed: 

	• EIN 
	
	• NAME
	
• Layers:
	• Input layer: 80 units / relu activation function
	
	○ Hidden layer 1: 30 units / relu activation function
	
	○ Output layer: 1 unit / sigmoid activation function
	
	
• # of Epochs used in model training:

	• 100
	
• Model Performance:

	• Loss: 55.98%
	
	• Accuracy: 73.12% (less than target of 75%)
	
	
	
OPTIMIZATION MODEL 1 

This model modified the base model to alter the features removed from inputs

• Features deemed ancillary and removed: 

	• EIN 
	
	• STATUS
	
• Model Performance:

	• Loss: 53.65%
	
	• Accuracy: 74.08%



OPTIMIZATION MODEL 2
This model modified optimization model 1 by altering the layers used

• Layers:
	• Input layer: 80 units / relu activation function
	
	○ Hidden layer 1: 60 units / relu activation function
	
	○ Hidden layer 2: 40 units / relu activation function
	
	○ Hidden layer 3: 20 units / relu activation function
	
	○ Output layer: 1 unit / sigmoid activation function
	
	
• Model Performance:

	• Loss: 54.88%
	
	• Accuracy: 74.43% (less than target of 75%)


OPTIMIZATION MODEL 3
This model modified optimization model 2 by increasing the # of bins used for the NAME feature from 9 to 31

• Layers:
	• Input layer: 80 units / relu activation function
	
	○ Hidden layer 1: 60 units / relu activation function
	
	○ Hidden layer 2: 40 units / relu activation function
	
	○ Hidden layer 3: 20 units / relu activation function
	
	○ Output layer: 1 unit / sigmoid activation function
	
	
• Model Performance:
	• Loss: 52.65%
	
	• Accuracy: 75.75% (meets/exceeds target of 75%)



Summary: Overall, the model's performance improved only slightly through data alteration and model modifications. The model's accuracy is low to moderate and has not yet reached the point of convergence (see below charts), indicating that further alterations will be required to achieve sufficient optimization. Alterations could include changes in feature selection and binning, number and type of activation function, etc. Deploying KerasTuner as a hyperparameter optimization framework could also prove useful.


![image](https://github.com/ccressman/deep-learning-challenge/assets/119253324/9eb86a92-4e78-4b40-af41-ca20d82c1430)


![image](https://github.com/ccressman/deep-learning-challenge/assets/119253324/335d0fd0-edbf-4397-9863-b35e61117d2e)



