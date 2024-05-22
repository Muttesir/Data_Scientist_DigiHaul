# Data Scientist DigiHaul Tasks

# Delivery Timeliness Analysis

This project presents a comprehensive analysis of delivery timeliness, combining GPS data and shipment bookings to evaluate performance. The project is divided into three main tasks:
1. Analyzing delivery timeliness.
2. Notifying and analyzing late deliveries.
3. Predicting and analyzing late deliveries using machine learning.

Each task provides insights into different aspects of delivery performance, highlighting areas for improvement and showcasing the effectiveness of predictive models in anticipating delays.

## Task 1: Analyzing Delivery Timeliness

### Objective
To determine how often deliveries are made on time by analyzing GPS data and shipment bookings.

### Process
1. **Data Collection**:
   - GPS data: Records of delivery vehicle locations over time.
   - Shipment bookings data: Details about each shipment, including the latest scheduled delivery time.

2. **Data Preparation**:
   - Convert date and time information in both datasets into a standard format for easier comparison.

3. **Filtering Data**:
   - Focus on GPS data within a specific date range provided by the user.

4. **Analyzing Deliveries**:
   - Match the latest GPS data for each shipment with the corresponding booking information.
   - Determine if each delivery was on time by checking if the last recorded GPS timestamp was within 30 minutes of the scheduled delivery time.

5. **Results**:
   - Calculate the percentage of on-time deliveries.
   - Create a pie chart to visually represent the percentage of on-time vs. late deliveries.

### Findings
- On-Time Delivery Percentage: 62.7%
- Late Delivery Percentage: 37.3%

### Conclusion
The analysis provides a clear picture of delivery performance, showing areas where improvements might be necessary to increase the percentage of on-time deliveries.

## Task 2: Notifying and Analyzing Late Deliveries

### Objective
Identify late deliveries and notify the relevant parties while also calculating the total number and duration of these delays.

### Process
1. **Data Collection**:
   - GPS data: Records of delivery vehicle locations over time.
   - Shipment bookings data: Details about each shipment, including the latest scheduled delivery time.

2. **Data Preparation**:
   - Convert date and time information in both datasets into a standard format for easier comparison.

3. **Filtering Data**:
   - Focus on GPS data within a specific date range (from October 1, 2023, to December 31, 2023).

4. **Merging Data**:
   - Match the latest GPS data for each shipment with the corresponding booking information.
   - Determine if each delivery was late by checking if the last recorded GPS timestamp was more than 30 minutes past the scheduled delivery time.

5. **Notifications**:
   - Generate notifications for each late shipment, indicating the shipment number and the timestamp when it was recorded as late.

6. **Calculating Delays**:
   - Count the total number of delays.
   - Calculate the total delay time in seconds for all late shipments.

7. **Saving Results**:
   - Save the details of delayed deliveries to a CSV file for further reference.

### Findings
- Total Number of Delays: 1,212
- Total Delay Time in Seconds: 13,422,135 seconds

### Conclusion
This process provided a detailed overview of late deliveries, helping to identify problem areas in the delivery process. The notifications and saved data offer actionable insights to improve on-time delivery performance.

## Task 3: Predicting and Analyzing Late Deliveries Using Machine Learning

### Objective
Predict which deliveries might be late using machine learning models and analyze the effectiveness of these predictions.

### Process
1. **Data Collection and Preprocessing**:
   - Load shipment data and convert date columns into a standard format.
   - Create a target column indicating whether a delivery was late (more than 30 minutes past the scheduled time).

2. **Data Visualization**:
   - Visualize the data to understand the distribution of features and the target variable.
   - Use pair plots and count plots to see how different features relate to the lateness of deliveries.

3. **Data Balancing**:
   - Balance the dataset using oversampling to ensure that there were equal numbers of on-time and late deliveries.
   - This step helps the model learn better by having a balanced representation of both classes.

4. **Preparing Data for Training**:
   - Split the data into training and testing sets.
   - Apply preprocessing steps, including scaling numerical features and encoding categorical features.

5. **Training and Selecting the Best Model**:
   - Train several machine learning models, including Random Forest, Gradient Boosting, AdaBoost, and Logistic Regression.
   - Evaluate their performance using cross-validation and select the best model based on accuracy.

6. **Model Evaluation**:
   - Evaluate the selected model using the test set and generate a classification report, ROC curve, and confusion matrix.
   - These metrics help understand the model's performance in terms of precision, recall, and overall accuracy.

7. **Predicting New Deliveries**:
   - Use the trained model to predict the probability of delays on new booking data.
   - Compare the predicted late deliveries with the actual late deliveries to assess the model's accuracy.

8. **Visualization of Predictions**:
   - Visualize the distribution of predicted probabilities for delays.
   - Compare actual vs. predicted late deliveries to see how well the model performed.

9. **Threshold Comparison**:
   - Plot the comparison of predicted vs. actual late deliveries at various probability thresholds.
   - This helps understand how changing the threshold affects the number of predicted late deliveries.

### Findings
- The best model achieved a cross-validation accuracy of 95.95%.
- The evaluation metrics showed that the model could predict late deliveries with high precision and recall.
- Visualizations indicated that the model was effective in predicting late deliveries.

### Conclusion
This machine learning approach allows accurate prediction of late deliveries, helping improve logistics by anticipating delays and taking proactive measures. The analysis and visualizations provide valuable insights into the factors contributing to late deliveries and the model's performance.

## Additional Notes
- Enhancing the model with weather data and other external factors could further improve prediction accuracy. The API integration for weather data was not tested in this project, but it can be implemented in the future depending on business requirements
- The process included setting up a Flask app for serving the model, enabling real-time predictions.
- Data would be run on local files. Please check the file paths in the code to ensure they are correct. The dataset has not been uploaded due to its large size.

## Instructions
1. Clone this repository.
2. Run the code for Task 1 to generate the pie chart and save it.
3. Run the code for Task 2 to generate the notifications and save the screenshot.
4. Run the code for Task 3 to generate the pair plot, ROC curve, confusion matrix, and other graphs, and save them.

