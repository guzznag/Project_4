# Pesticide Use on Cancer Rates
Note: Exploratory data on other branches was conducted, but ultimately left out in final pushes.

## Background Information
We stop by our local grocery stores once a week, or every other day even to fill up on our household food necessities. However, how frequently do we consider where it really comes from and how the food we have in our homes affects those living around where they’re produced? Our goal is to evaluate if the effects of agricultural food production correlate to health conditions of nearby residents of these areas, specifically incidences of cancer.

The geographical scope of our research was established at the county level within the United States. We made this decision because it provided an appropriate mid-level geographic area that the effects of pesticide use could be constrained to. The data also includes historical data of pesticide use between the years 2013-2019 and pesticides broken down by category (i.e herbicide, insecticide, and fungicide). Data on cancer rates per 100k and specific cancer incidence types over an average of 5 years (2016-2020).

<img width="1075" alt="Screenshot 2024-04-10 at 3 55 34 PM" src="https://github.com/guzznag/Project_4/assets/147587443/074da0b3-b44b-46f4-8461-a83066ce7c85">
<img width="1325" alt="Screenshot 2024-04-10 at 3 56 52 PM" src="https://github.com/guzznag/Project_4/assets/147587443/5c8a1dcf-479a-4e03-9020-61f6d86a085b">

## Definitions and Data Cleaning
The data needed to be preprocessed before any numerical and statistical evaluations could be conducted. This included removing columns that were not necessary, formatting data types, and removing null values and symbols that represented a null value.

A table for historical pesticide use by year was compiled, with 2019 being the ending point. Additionally, another table was compiled that contained data on specifically 2019 pesticide rates since that was the most recently available data as well as the peak of pesticide use in the data. Other columns within the table included total cancer incidence rates, specific cancer incidence rates, and fungicide, herbicide, and pesticide use in kilograms. 

An outlier was identified and removed from the dataset which was Union County, Florida.

<img width="472" alt="Screenshot 2024-04-10 at 3 57 40 PM" src="https://github.com/guzznag/Project_4/assets/147587443/6759bf0b-bf0e-4a66-80b6-b8987d90dc56">

We explored an assortment of 18 different correlations between the variables in order to find the strongest correlations between the data collected. The strongest correlation we were able to find was between total cancer incidence rates and herbicide use, granted not a strong correlation but the strongest we could work with.

## Machine Learning Model Implementation
The first machine learning model we implemented was linear regression. This is the easiest and most simple model to perform and was our first option. We supplemented this with a user GUI where users can input a value for herbicide usage, and the given output will be the predicted cancer incidence rate according to the model. Given the beginning correlation with the data, the model performs the best that it can with the following results.

<img width="215" alt="lin_regress_results" src="https://github.com/guzznag/Project_4/assets/147587443/2189f9a2-db08-4963-90cf-a464eb8169b4">
<img width="890" alt="project_gui" src="https://github.com/guzznag/Project_4/assets/147587443/3617d72f-d080-4ba5-a2ff-9b11690a2dba">

Next, a random forest regression was created considering the same two variables. Using multiple decision trees, we trained our Random Forest model to output the mean prediction of those trees for regression results. Again, performance was limited due to existing low correlation between variables in source datasets. We were unable to lower variance and prediction error to rates of linear regression model with use of increased number of decision trees and the results are as follows.

<img width="275" alt="random_forest_results" src="https://github.com/guzznag/Project_4/assets/147587443/4e7b9b55-0b42-4d6f-9c12-a3cbc9082f5f">

## Conclusion and Limitations
In attempts to optimize the data, the linear regression model appears to be better than the random forest regression model given the circumstances of the data. The linear regression model has a lower MSE than the random forest regression which implies better model performance. This could be because the random forest regression accommodates to not "overfit" the model but given the variability of the base data, overfitting may be more appropriate.

In terms of data allocation, pesticide use rate was based on a survey so there are states and counties that are excluded from the data. For example, California conducts its own specific process of pesticide evaluation and research.

Our study was very limited due to data availability, time, and the fact that cancer is a very long term developing illness that has many factors that come into play other than exposure to agricultural chemicals. In further studies, pesticide exposure could be an aspect to consider when evaluating the effects of cancer rates as a feature, but not a holistic correlating factor.

## Links to Sources
Tableau: https://public.tableau.com/app/profile/lori.bradshaw/vizzes


Cancer Data: https://www.statecancerprofiles.cancer.gov/incidencerates/index.php?stateFIPS=00&areatype=county&cancer=001&race=00&sex=0&age=001&type=incd&sortVariableName=rate&sortOrder=default&output=0#results


Pesticide Data: https://www.sciencebase.gov/catalog/item/6081a924d34e8564d68661a1


User GUI Github: https://github.com/varunsly/Linear_Regression_GUI.git
