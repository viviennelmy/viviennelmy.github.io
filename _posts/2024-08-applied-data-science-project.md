---
Author: Vivienne
Title: "Applied Data Science Project Documentation"
Categories: ITD214
---

## Project Background

The aim of our project is to improve the business of British Airways (BA), mainly based on reviews given by customers and the ratings they had given for different aspects of the airline. The dataset was based on  customer reviews of British Airways scrapped from airlinequality.com from 2015 to 2023, so the reviews are still recent, relevant and also provided a long enough runway which spanned 8 years.

Topic Modelling was used to extract relevant topics in review texts in order to examine negative and positive reivews. We had 4 business objectives: 
1. To reduce response time by 10% by identifying significant areas of concern through topic modelling and association rule mining for automation of replies.
2. To analyse review topics for the four different seat types for a more targeted marketing approach, improving business by 10%.
3. To identify areas of customer satisfaction for marketing purposes, to improve business by 10%.
4. To reduce negative review sentiments by 10% to improve customer satisfaction and demand.

I worked on business objective no. 4.

## Work Accomplished

As we were using the same dataset as a group, we did the cleaning and pre-processing together. For Business goal 4, in addition to the data preparation done as a group, I further pre-processed the data in KNIME as well as Python to meet the needs of answering the business objective  which was contigent on reviewing topics from negative customer reviews.

### Data Preparation

Group data preparation and cleaning:
![image](https://github.com/user-attachments/assets/3f50447d-f3a0-4baf-b678-6327cecae69b)
![image](https://github.com/user-attachments/assets/9ff612dd-75de-4967-a8d8-9a126822be99)


Individual data cleaning and text-preprocessing (filtered from negative and verified reviews and dropped columns):
![image](https://github.com/user-attachments/assets/1d7dee5a-c6c3-4086-af47-f722e14fb0c6)
![image](https://github.com/user-attachments/assets/e283dd91-7ef3-4629-a5f0-dc45efeeee25)

### Modelling
For business objective 4 topic modelling, I utilised 2 models. The first was a LDA model, and the second was a NMF model. 

1st Model: Latent Dirichlet Allocation (LDA)
Code and results for LDA: 
<img width="637" alt="Screenshot 2024-08-25 at 6 41 32 PM" src="https://github.com/user-attachments/assets/5e9186ad-443c-489c-b8fa-e366a989ca00">

2nd Model: Non-negative Matrix Factorisation (NMF)
Code and results for NMF:
<img width="604" alt="Screenshot 2024-08-25 at 6 45 45 PM" src="https://github.com/user-attachments/assets/07372924-01dc-4773-a9ee-e8df0f78aee7">

### Evaluation

The NMF performed better than the LDA Model, with a higher coherence score (0.44 vs 0.41) and more interpretable results. Please see below:

<img width="810" alt="Screenshot 2024-08-25 at 9 27 01 PM" src="https://github.com/user-attachments/assets/b8629115-2c20-4277-81ba-ebd384b34ad9">

I could not base it just on the coherence score of the models alone. I also had to look through the topics and their groupings, to figure out which model was better able to suit the needs of answering the business objective as well as the grouping of topics could be quite random. In the end, of the 2, the NMF model, which also had the higher coherence score, was selected. 

Topics identified by the LDA Model: 
1. Disatisfaction with communication between passengers and staff.
2. Disatisfaction with Business class food and service.
3. Diverted flights during pandemic.
4. Disatisfaction with Business class service, especially for London flights.
5. Delayed London flights and arrogant staff.

Topics identified by the NMF Model: 
1. Disatisfaction with poor service by Cabin crew and in-flight food and meals, especially for London flights.
2. Disatisfaction with business class and economy seats, as well as the lounge in first class.
3. Disatisfaction with refund policies, likely from cancelled flights.
4. Disatisfaction with delayed boarding and flights that were late.
5. Disatisfaction with legroom in premium economy seats.

## Recommendation and Analysis

With business objective 4 which was based on only negative reviews (customer ratings of =<4), these topics gave a broad overview of what the BA airlines should improve on. 
There are a few aspects, for example, in terms of service standards, the crew needs to improve their services provided onboard the plane as well as for communication with passengers, and some were cited to be 'arrogant'. 
Next, food and meals were also highlighted in reviews of unsatisfactory customer experience. 
Furthermore, the refund policy also appears to be a pain point for cancelled flights. 
Finally, there appears to be many complaints with regards to the business class and London flights. Hence, British Airways should look into and address these areas in their airline business to improve customer satisfaction and demand. 

<img width="452" alt="Topic 1" src="https://github.com/user-attachments/assets/d1dd1bc3-bd94-469c-9f35-272a7b5b49c7">
<img width="452" alt="Topic 2" src="https://github.com/user-attachments/assets/d0b708e1-8cb8-4187-8edd-9f2a7fd68a09">

pyLDAvis was used to visualise topics and relationships to inspect how the topics are distributed and related. This helps to understand model’s performance and tuning . For topic 1, ‘service’, ’London’ and ‘hours’ were the most common terms for negative reviews, whereas for topic 2, ‘seats’, and ‘business’ class were the most common terms for complaints. Even though these 2 topics appear close on the Intertopic map, they still appear reasonably distributed and defined. 

## AI Ethics

The BA ariline review dataset contained just one column for customer identifcation.: It was the 'Name' column. Apart from it, there were no other customer identifiers, such as customer's ID or flight ticket no., age, address, etc. 
To address this issue of privacy, and since the name of the customer was not important to dataset modelling and predictions, we removed the 'Name' column during data preparation.

Even though there were columns namely 'route type' and 'date flown' which carry a slight risk of compromise to customer's privacy, none of the members had utilised this data. After removing the names of the airlines' customers, there was no longer information in the dataset as to which customer had taken which route.

Furthermore, ariline reviews are not not particularly sensitive, as opposed to health-related datasets or customers' finances that could pose a higher risk to customers' privacy if the data was not processed properly. 

The Models the group used for text analytics and topic modelling were models that could be explained and interpreted - they were not blackbox machine learning or deep learning models such as neural networks that could be very complex and unfathomable. Hence, the models used provided a basis for accountability, transparency and interpretability. 

## Source Codes and Datasets
Upload your model files and dataset into a GitHub repo and add the link here. 
https://github.com/viviennelmy/viviennelmy.github.io/blob/master/Topic%20Modelling%20with%20LDA%20and%20NMF.ipynb
https://github.com/viviennelmy/viviennelmy.github.io/blob/master/filtered_negreviews.csv
