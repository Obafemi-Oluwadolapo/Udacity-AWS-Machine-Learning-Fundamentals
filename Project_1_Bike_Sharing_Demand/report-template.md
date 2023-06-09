# **Report: Predict Bike Sharing Demand with AutoGluon Solution**

**OBAFEMI OLUWADOLAPO SUCCESS**

## **Initial Training**

### **What did you realize when you tried to submit your predictions? What changes were needed to the output of the predictor to submit your results?**

I had to change the dtype of the datetime column to a dtype **of
datetime64\[ns\]** column using the *.to_datetime()*. Nothing much
happened when I tried to submit the predictions. I checked for negative
values in the results and there was none.

### **What was the top ranked model that performed?**

The top ranked model was the **KNeighborsUnif_BAG_L1** with a model
score of **-101.546199** and with a score validation of **0.044973**
which was the lowest out of the Models that trained in 10 minutes. The
prediction time was also the lowest making it a very fast model for
making the right predictions with a time of **0.039932.**

## **Exploratory data analysis and feature creation**

### **What did the exploratory analysis find and how did you add additional features?**

It was noticed that the Count column is left skewed using the.hist()
function. The hour column was plotted against each characteristic. As
categorical columns, the season and weather columns could not be
plotted. The following were discovered:

-   From 2:00 p.m. to 4:00 p.m., the day\'s highest temperature and
    > absolute temperature are reached.

-   The early morning hours between 6 and 7 in the morning are also when
    > the humidity is at its highest.

> ![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image4.png){width="6.5in"
> height="2.0833333333333335in"}
>
> ![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image2.png){width="5.4375in"
> height="2.875in"}

-   Around 4 o\'clock in the afternoon is also when the wind speed is
    > highest.

-   The second-highest surge in bike demand, as seen in the Count
    > against Hour graph, occurs in the morning, when demand is at its
    > lowest. This demonstrates the health-consciousness of some, who
    > exercise first thing in the morning.The highest peak is at roughly
    > 5:00 p.m.

> ![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image6.png){width="6.5in"
> height="1.6666666666666667in"}

In order to update the categorical datas \[\"season\" and \"weather\"\]
using the.get_dummies() function, I developed a new feature utilizing
feature engineering. This used integers of 0s and 1s to categorize the
season and weather into different groups. Below is the heatmap of count
against the time of the day.

![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image5.png){width="4.27841426071741in"
height="3.182292213473316in"}

### **How much better did your model perform after adding additional features and why do you think that is?**

Following the addition of the new function, it performed poorly. I
don\'t know the cause, and it surprises me. I\'m looking forward to the
review. From a score of 1.98, it received a kaggle score of roughly 2.7.
I\'m not sure if the score is a measuring tool, but I was genuinely
shocked. I was able to later add more features from the humidity,
temperature and windspeed table. More feature were added and with
Hyperparameter tuning, I got a Kaggle score of 1.677 which was my
performance.

Below is the picture of the heatmap after more features were added.

![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image8.png){width="5.8268744531933505in"
height="4.932292213473316in"}

## **Hyper parameter tuning**

### **How much better did your model perform after trying different hyper parameters?**

After each hyperparameter tweaking, they improved greatly. However,
applying the hyperparameter **\"NN\"** caused the model to perform the
poorest, proving that employing the neural technique will lead to subpar
outcomes. However, the remaining hyperparameters improved the model\'s
performance. The **XGBoost** was the best method so far in terms of
prediction. The model performed even better when more features was added
and trained using the XGBoost which gave a more precise answer and
better performance

### **If you were given more time with this dataset, where do you think you would spend more time?**

Enhancing the model, particularly using XGBoost, KNN and RF models.
Without using AutoGluon, I will conduct additional exploratory data
analysis and test out other machine learning models like the
RandomForest() and SVM Models to see how each one interprets the input
data.

### **Create a table with the models you ran, the hyperparameters modified, and the kaggle score.**

![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image1.png){width="6.5in"
height="1.625in"}

### **Create a line plot showing the top model score for the three (or more) training runs during the project.**

![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image3.png){width="6.5in"
height="4.972222222222222in"}

### **Create a line plot showing the top kaggle score for the three (or more) prediction submissions during the project.**

![](vertopal_a3b0f1e3677d4fcc9a5bc6b02bd0618f/media/image7.png){width="4.119792213473316in"
height="3.215181539807524in"}
