# Football-Match-Outcome-Prediction
This repository is about the "Football Match Outcome Prediction". Here, I have used a football dataset named "LaLiga" and predicted different outcomes. For training the model, I have simply use the ANN model. The dataset has been provided in "Dataset" folder.

Initially the dataset has 10 features/column and 9662 rows. The detailed view of the dataset is given below- 

![image](https://user-images.githubusercontent.com/60071360/119144985-0995a080-ba6b-11eb-940e-5e76496674fa.png)

The name of the columns of the dataset are-

•	Season
•	Date
•	Home Team
•	Away Team
•	HTR - Half Time Result
•	FTR - Full Time Result
•	HTHG - Half Time Home Goals
•	HTAG - Half Time Away Goals
•	FTHG - Full Time Home Goals
•	FTAG - Full Time Away Goals

**Cleaning and representation of the dataset**

First, the dataset needs to be clean and finalizing with required and supported data types to begin the work with the dataset. Also, the dataset should not include any empty or null values, which can make our model perform poorly. To analyze the data types of values containing each column, the following code need to be run on the coding environment.
 
![image](https://user-images.githubusercontent.com/60071360/119145592-9d676c80-ba6b-11eb-982c-27fcf57e66e1.png)

Fig. 1 shows that the shape of the dataset is (9662, 10) where 9662 represents the rows and 10 represents the columns. The next segment of the code showing the output of the data type of values of each column. The output shows that among the 10 features six (6) have object data types and four (4) have int64 data types. 
For this project, the targeted value/column which needs to be predicted is the FTR (Full Time Result) column. In the CSV file, this column has contains three (3) values- H (Home Team Win), A (Away Team Win), and D (Draw). So, these values are string types. To train the model, this value should be converted to numerical values. To do so, I have employed the find and replacing techniques of pandas which will reform the values of the FTR column into numerical values. Then, those values need to be replaced in the dataset. Similarly, the HTR column contains the same values, so, this column also needs to be converted. Fig. 4 shows the coding examples of the implementation of converting to numerical values.
 
![image](https://user-images.githubusercontent.com/60071360/119145665-afe1a600-ba6b-11eb-9a68-3ded49eb3d77.png)

Fig. 2 showing the implementation of the converting and replacing the converted value to the main dataset. The ‘H’ value converted as 1, ‘D’ value converted as 0, and the ‘A’ value converted as 2. The same procedure has been followed in the HTR column also. 
From fig. 1, there are also two columns named- HomeTeam and AwayTeam, these two columns are the object data types. These are categorical variables. So, these two columns need to be converted to the numerical value. For this, at first, the values need to be converted as the category data types. Then, the Label Encoder needs to be employed to encode these values. By doing so, each value of these two columns will contains a unique number. As this column contains the team names, so, each team will have different numerical numbers. The fig. 3 and 4 show the coding representation of the label encoder.
![image](https://user-images.githubusercontent.com/60071360/119145800-cdaf0b00-ba6b-11eb-8b70-8fe5cd25797d.png)
![image](https://user-images.githubusercontent.com/60071360/119145817-d30c5580-ba6b-11eb-82f8-9f5b08a784fe.png)

From fig. 3, the values of HomeTeam column is changed from string to integer type and each values are unique, as the team names are unique. Fig. 4 shows the all the unique numbers of the HomeTeam and AwayTeam column.

![image](https://user-images.githubusercontent.com/60071360/119146036-0b139880-ba6c-11eb-9874-697c95c44c97.png)

Now, in the dataset, there are two columns which are not important to predict the match outcome which are Date and Season column. So, these two columns need to be removed from the dataset. To do that, the fig. 5 shows the coding example of removing. Also, the fig. contains the updated and final representation of the dataset. 
![image](https://user-images.githubusercontent.com/60071360/119146097-1bc40e80-ba6c-11eb-933c-4e52037b4e86.png)

Now, the dataset are fully ready for further operation. Let’s have a look to the updated shape of the dataset and statistics. 

![image](https://user-images.githubusercontent.com/60071360/119146144-2aaac100-ba6c-11eb-8afb-263cdf9b4271.png)


Before doing any further approach, let’s check the dataset, if there any null values in any column. Fig. 6 shows the code examples of checking null values.
![image](https://user-images.githubusercontent.com/60071360/119146178-34ccbf80-ba6c-11eb-9013-faaf8a809bfa.png)

So, from the figure, we can observe that there are no missing values in any column of the dataset. Now, the dataset are ready for training and testing purpose.
Explore the Dataset
Before moving to the training, let’s have a look at the target column (FTR) and HTR column by observing the pie chart. Fig. 7 and 8 show the pie chart of the HTR and FTR columns respectively.
![image](https://user-images.githubusercontent.com/60071360/119146311-50d06100-ba6c-11eb-8980-da1d1ce517a7.png)
![image](https://user-images.githubusercontent.com/60071360/119146324-54fc7e80-ba6c-11eb-96bc-9652ca13e707.png)

From these figures, in the HTR column, the winning percentage of the Home team is 42.3% and in the FTR column is 47.7%. Where the winning percentage of the HTR and FTR column of the Away team is 35.6% and 26.9% respectively. So, the winning percentage of the Home team is much higher than the Away team. Also, to mention the draw percentage of these two columns is 22.1% in HTR and 25.4% in FTR columns.
