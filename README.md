# Data-Science---Module-8-Assignment
Module 8: Introduction to Linear Regression

Question 1: Your objective is to use `years_education` to predict `salary` using a linear model, and to determine how much of the variability of the response variable is explained by the model.
Fill in the missing pieces of code that would be used to accomplish this task.
response - correct
# Predict salary based on years of education using a linear model
myModel <- lm(salary ~ years_education, data = myData)
# Calculate how much of the variability of the response variable is explained by the model
summary(myModel)$adj.r.squared

Question 2: Given the output below, what would be the predicted salary of an unmarried employee with 4 years of education, working 5 days per week, and absent 10 times?
 
•	$47,400
•	$54,500
•	$56,500
•	$54,900

45000 + 4*2000 + 5*500 – 10*100 = 45000 + 8000 + 2500 – 1000 = 54500

Correct – the employee’s years of education and working days per week will increase their predicted salary, while being absent decreases their predictions salary. The model also predicts that employees who are married will receive an additional $4000.


Question 3: Your objectives are to:
•	apply a linear model with age as the response variable and experience and income as predictor variables,
o	#Build linear model
o	age_model <- lm(age ~ experience + income, data = age_data)
•	generate predictions of age and add them to the data set as a new column, and
o	# Generate predictions
o	age_data <- age_data %>% 
mutate(predicted = predict(age_model, age_data))
•	visualize the data using a scatterplot of age and income and a line representing the predicted values, facet the plot based on experience, and apply a black and white theme.
o	#Create visualization
o	ggplot(age_data) +
geom_point(aes(x = income, y = age)) + 
geom_line(aes(x = income, y = predicted)) + 
facet_wrap(~experience) +
theme_bw()


Question 4: Given the data frame below, what is the sum of square errors based on a naïve model of age?
 

Step 1 – Build dataframe: question4 <- data.frame(age = c(20, 25, 25, 30, 35, 45), income = c(25000, 35000, 80000, 40000, 65000, 65000))

Step 2 – Build naïve model: naive_model <- lm(age ~ 1, question4)

Step 3 – Compute SSE: naive_sse <- sum(resid(naive_model)^2) = 400

Question 5: Match the lines of code with the description of the expected output.
The predictor variables used in the model, as a formula. 
  
The difference between the value of the observed response and the predicted response.  
 
The predicted value of the response variable for each row of the data frame used in the model.  
 
The change in the predicted response variable per one unit of change in the predictor variable.  


Question 6: In which of these scenarios might linear regression be used? Select all that apply.
•	Predicting the amount of money that a customer will spend based on their gender, marital status, and country of residence.
•	Predicting the amount of money that a customer will spend based on their income and the number of products they have purchased within the past year.
•	Predicting if a customer will renew a membership based on their income and the number of products they have purchased within the past year.
•	Predicting if a customer will renew a membership based on their gender, marital status, and country of residence.

Correct – linear regression can be used to make predictions about a continuous response variable. For classification problems, logistic regression may be used.


Question 7: Given the output below, what recommendations could be made about what type of advertising a company should invest in, assuming each type of advertising costs the company the same amount of investment per unit? Select all that apply.
 
•	If the client is not a media company, they should invest in print advertisements over internet advertisements.
•	Given the same number of internet advertisements, a media company should expect more sales than a non-media company.
•	If the client is a media company, they should invest in tv advertisements over print advertisements.
•	Investing in internet advertisements will be likely to increase sales more than investing in tv advertisements.


Question 8: Given the figure below, which statement(s) are true about the model being represented? Select all that apply.
![image](https://user-images.githubusercontent.com/59670247/208314024-7e354031-a11a-4454-997f-cb92b40b466e.png)
![image](https://user-images.githubusercontent.com/59670247/208314034-79bdc923-ad5e-422a-af96-d27f6293f50b.png)
1.	The model makes more accurate predictions at high values of the response variable than low values.
2.	The model suffers from heterogeneity in the residuals.
3.	The model is likely appropriate for generating predictions.
4.	The model makes more accurate predictions at low values of the response variable than high values.

Module 8: Quiz
1.Which of these independent variables could be included in a naïve linear model where the dependent variable is price? The naïve model includes only the dependent variable, price.

Which of these lines of code could be used to predict the price of a house based on the naïve model? Select all that apply.
 
 
 
 

2.How much of the variability of the response variable is explained by the model, given the output below?
 
The adjusted r squared value tells you how much of the variability is explained by the model, adjusted by the number of predictors included in the model.

3.Which line of code models sales in response to every other available variable in the data frame called myData?
 

4.Which of these models includes an interaction between predictor variables?
 
an * indicates an interaction between predictor variables.

5.What type of linear model does the following line of code represent?
 
A univariate model

6. Given the output below, which of these equations would predict the price of a house with 2 bedrooms and 1 bathroom?
 
 
30000 + (2 * 5000) + 1000 would predict the price of a house with two bedrooms and one bathroom.
![image](https://user-images.githubusercontent.com/59670247/208314067-58e31aec-d714-4a65-ac4b-963ab1be0a75.png)

