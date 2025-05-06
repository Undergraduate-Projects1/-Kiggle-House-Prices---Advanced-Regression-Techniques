# -Kiggle-House-Prices---Advanced-Regression-Techniques

[House Prices - Advanced Regression Techniques](https://www.kaggle.com/competitions/house-prices-advanced-regression-techniques)

##### 💡Getting Started Notebook
To get started quickly, feel free to take advantage of this [starter notebook](https://www.kaggle.com/code/gusthema/house-prices-prediction-using-tfdf/notebook).

## Competition Description
![image1](https://storage.googleapis.com/kaggle-media/competitions/House%20Prices/kaggle_5407_media_housesbanner.png)
-Ask a home buyer to describe their dream house, and they probably won't begin with the height of the basement ceiling or the proximity to an east-west railroad. But this playground competition's dataset proves that much more influences price negotiations than the number of bedrooms or a white-picket fence.
- With **79 explanatory variables** describing (almost) every aspect of residential homes in Ames, Iowa, this competition challenges you to **predict the final price of each home**.

## Practice Skills
- Creative feature engineering 
- Advanced regression techniques like random forest and gradient boosting

## Evaluation
### Goal
It is your job to **predict the sales price for each house**. For each Id in the test set, you must predict the value of **the SalePrice variable**.

### Metric
Submissions are **evaluated on Root-Mean-Squared-Error (RMSE)** between the logarithm of the predicted value and the logarithm of the observed sales price. (Taking logs means that errors in predicting expensive houses and cheap houses will affect the result equally.)

### Submission File Format
The file should **contain a header** and have the following format:

```
Id,SalePrice
1461,169000.1
1462,187724.1233
1463,175221
etc.
```
You can download an example submission file (sample_submission.csv) on the [Data page](https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data).









