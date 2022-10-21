# Neural_Network_Charity_Analysis

# Purpose of the project:
The purpose of the project is to use neural netwrok machine learning model to help the foundation, Alphabet Soup, to predict where the foundation should invest with its funding, based on the data provided from the foundation's business team. The data has the foundation's funding record from over the years, containing more than 34,000 organizations that received the funding from Alphabet Soup. And it included the metadata of each column:  
- EIN and NAME—Identification columns
- APPLICATION_TYPE—Alphabet Soup application type
- AFFILIATION—Affiliated sector of industry
- CLASSIFICATION—Government organization classification
- USE_CASE—Use case for funding
- ORGANIZATION—Organization type
- STATUS—Active status
- INCOME_AMT—Income classification
- SPECIAL_CONSIDERATIONS—Special consideration for application
- ASK_AMT—Funding amount requested
- IS_SUCCESSFUL—Was the money used effectively


# Results
- **What variable(s) are considered the target(s) for your model?**  
The goal of the project is to help the foundation better use its funding, with the metadata provided along with the data, I considered the "IS_SUCCESSFUL" column as the target for the model, since it contains the data of if the funding by the Alphabet Soup was used effectively.

- **What variable(s) are considered to be the features for your model?**  
I considered "APPLICATION_TYPE", "AFFILIATION", "CLASSIFICATION", "USE_CASE", "ORGANIZATION", "STATUS", "INCOME_AMT", "SPECIAL_CONSIDERATIONS", "ASK_AMT" as the features for the model.

When I tried to imporve the accuracy of the model, I also removed the "STATUS" columns, reason being the data was from over the years of funding records, and over the year some organizations could be closed, merged, renamed or other possible reasons for the company in the list no longer active. The purpose is to help the foundation predict where its funding should go and could be used effectively, it could some cases of the organization was used the funding effectively but no longer active, so I decided to removed this column to reduce noise for the model. And I also removed the "SPECIAL_CONSIDERATION" column for the same reason.

- **What variable(s) are neither targets nor features, and should be removed from the input data?**  
The "EIN" and "NAME" columns should be removed since it only provided the identification of the organizations received the funding, which isn't helpful for our model determine and predict if the funding was used or would be used effectively, so I the two columns removed from the input data.

- **How many neurons, layers, and activation functions did you select for your neural network model, and why?**  
![Model 1 summary](Images/model_1_summary.png)  
![Model 1 result](Images/model_1_result.png)  
First, I set 2 hidden layers and one output layer, with 80 neurons for the first layer, and 30 neurons for the second layers, both layer used relu activation, and output layer has one neurons with sigmoid activation. The input data has 44 features, so I set the neurons for the first layers roughly 2 times the number of the input layers, and set epoch to 50. the accuracy for this model is about 72%.

![Model 2 summary](Images/model_2_summary.png)  
![Model 2 result](Images/model_2_result.png)  
Starting from the second attempt, I also drop the "STATUS" and "SPECIAL_CONSIDERATION" column.
Second attempt, I increased the neurons for the first layer to 120, which is three times of the input features, activation set as relu. Second layer has 50 neurons, activation set as leaky_relu, output layer is the same as the first one. Epoch for this model is set to 80. The accuracy for this model is close to 73%.

![Model 3 summary](Images/model_3_summary.png)  
![Model 3 result](Images/model_3_result.png). 
Third attempt, I  keep the neuron numbers for the first two layers, changed the activation fucntion on the second layer to relu, and add a third layer which has 30 neurons and activation function set as tanh, output layer stay the same. Epoch is set to 100, the accuracy for this model is 72%.

![Model 4 summary](Images/model_4_summary.png). 
![Model 4 result](Images/model_4_result.png)  
The fourth attempt, I have first layer with 120 neurons, activation as relu. Second layer with 80 neurons, activation as sigmoid. Third layer with 50 neurons, activation as sigmoid. And add the fourth layer with 30 neurons, activation as sigmoid. Output layer stay the same. Epoch for this model is set to 100. The accuracy for this model is 72%.

With different models adding layers and changing neuron numbers and activation as a trail and error process to see if changuing those parameters will help with the performance of the models.

- **Were you able to achieve the target model performance?**  
I wasn't able to achieve with the performance of 75% with the models above.

- **What steps did you take to try and increase model performance?**  
After the initial model, I tried to removed the "STATUS" and "SPECIAL_CONSIDERATION" columns. Adding neurons, layers and changing the activation function for the models to try to increase model performance.

# Summary
The overall accuracy for the models I used is around 72%, the performance of the models didn't have much imporvement with adding neurons, layers. Different activation functions will also have different impact, so one method could be keep trying to find the optimal activation function for the dataset, adding more neurons and layers to have a more complex model to see if it could help with improving the model's performance.

The other direction we can take is to work on the input data, find out further information about the columns to determine if we should drop it, binned the variables or other methods if needed.

Since I've tried adding more neurons and layers but still not seeing any significant performance improvement, turn out focus on the input featuers might be have a good direction regarding improving the models' performance.
