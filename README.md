# Predicting Tweet Sentiment

## Overview

This repository contains the code and data used to analyze tweet sentiment. The primary goal of this project is to create machine learning models that can predict the sentiment of tweets, determining if they are positive, negative, or neutral. 

## Business Problem

The project aims to predict tweet sentiment to help companies understand public opinion about their brand or products. By accurately classifying tweets, companies can gain valuable insights into customer feedback and respond appropriately.

## Table of Contents

- Overview
- Business Problem
- Data Sources
- Installation
- Analysis and Results
  - Model Creation
  - Evaluation
- Conclusion
- Recommendations
- Future Steps
- Contact

## Data Sources

This [dataset](https://data.world/crowdflower/brands-and-product-emotions) contains over 9,000 tweets with the following attributes:
- **Targeted Company**: The company or brand mentioned in the tweet.
- **Sentiment**: The sentiment expressed in the tweet, categorized as positive, neutral, or negative.

  
## Installation

To run the project, follow these steps:

1. Clone the repository: 
    ```bash
    git clone https://github.com/yourusername/tweet-sentiment-analysis.git
    ```
2. Navigate to the project directory:
    ```bash
    cd tweet-sentiment-analysis
    ```

## Analysis and Results


### Sentiment Distribution
Below is a scatterplot of each targeted company, along with the sum of all sentiments for each specific company. As seen, there are no companies or products that have negative values, indicating that this dataset is heavily biased towards positive sentiment. This was addressed using random minority class oversampling, which artificially boosted the negative sentiment to make the model differentiate positive and negative sentiment with greater precision.

![image](https://github.com/user-attachments/assets/a4a5bdaf-e103-44eb-be86-a4243a167877)


### Model Creation

Multiple machine learning models were developed using the tweet dataset. The models include:

- Multinomial Naive Bayes (MultinomialNB)
- Logistic Regression
- Random Forest

### Evaluation

Models were evaluated based on various metrics such as accuracy, confusion matrices, and ROC-AUC scores. Cross-validation and hyperparameter tuning techniques were employed to optimize model performance.

**Multi-Class MultinomialNB Model**:
- Good at predicting negative tweets.
- Struggled with distinguishing between positive and neutral tweets.

 ![image](https://github.com/user-attachments/assets/e8be6374-52fa-4b3c-aa26-26f04824093b)
 
 ![image](https://github.com/user-attachments/assets/cc9e4cb4-6236-40bf-9e02-1dbd28113fcc)



**Binary MultinomialNB Classifier**:
- Outperformed the multi-class classifier.
- Better at differentiating between positive and negative tweets.

 ![image](https://github.com/user-attachments/assets/eb89038d-1dd6-4b6a-ba07-4435f9f0a023)
 
 ![image](https://github.com/user-attachments/assets/21c7f897-6b51-44b0-84b0-6ded8bdac230)




## Conclusion

The multi-output model is very good at predicting negative tweets; however, it struggles with differentiating positive and neutral tweets. While this model is able to encapsulate all three possible sentiment values, it performs worse than the binary classifier. This is most likely due to there being less contrast between the three when compared to the high contrast of the positive and negative binary models. We recommend using the binary classifier, as neutral tweets do not bring anything useful to the model, and it is more useful to be able to differentiate positive and negative tweets.

## Recommendations

For companies looking to analyze tweet sentiment related to their brand, it is advisable to use the binary MultinomialNB model. This model can be employed to determine sentiment after gathering data for relevant mentions. The binary classification approach will provide more useful insights into positive versus negative sentiments, which are crucial for understanding public perception and tailoring communication strategies. By focusing on these two sentiment classes, companies can better assess and respond to feedback, enhancing their engagement with customers and stakeholders.

## Future Steps

- **Data Expansion**: Utilize larger and more balanced datasets to improve model accuracy.
- **Human Rating**: Address potential issues with human-rated sentiment by incorporating more robust validation methods.
- **Advanced Techniques**: Explore additional preprocessing and feature engineering techniques to enhance model performance.

## Contact

For any questions or further information, please contact:


Greg Fatouras

   - https://github.com/Gfatouras
   - https://www.linkedin.com/in/gfatouras/
   - fatourasg@gmail.com

