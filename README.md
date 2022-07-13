# Rossmann Store Sales
This repository contains script of sales prediction with Machine Learning

![sales](https://user-images.githubusercontent.com/105643907/178740023-c03b887c-c238-480b-8408-e4e3c38a7536.jpg)

# Business Problem

The company's CFO requested a daily sales forecast for the next 6 weeks, in order to define a budget for the renovation of each store. The current sales forecast showed a lot of divergence. To solve this problem, i developed a project that uses Machine Learning to provide a more accurate forecast of store sales.

# Business Assumptions

- Days when stores were closed were dropped from the analysis.
- Stores with sales values equal to 0 were disregarded.
- For stores that did not have information on the competition distance, the value of 200000 was assigned.

# Attribute List

- Id - an Id that represents a (Store, Date) duple within the test set
- Store - a unique Id for each store
- Sales - the turnover for any given day (this is what you are predicting)
- Customers - the number of customers on a given day
- Open - an indicator for whether the store was open: 0 = closed, 1 = open
- StateHoliday - indicates a state holiday. Normally all stores, with few exceptions, are closed on state holidays. Note that all schools are closed on public holidays and weekends. a = public holiday, b = Easter holiday, c = Christmas, 0 = None
- SchoolHoliday - indicates if the (Store, Date) was affected by the closure of public schools
- StoreType - differentiates between 4 different store models: a, b, c, d
- Assortment - describes an assortment level: a = basic, b = extra, c = extended
- CompetitionDistance - distance in meters to the nearest competitor store
- CompetitionOpenSince[Month/Year] - gives the approximate year and month of the time the nearest competitor was opened
- Promo - indicates whether a store is running a promo on that day
- Promo2 - Promo2 is a continuing and consecutive promotion for some stores: 0 = store is not participating, 1 = store is participating
- Promo2Since[Year/Week] - describes the year and calendar week when the store started participating in Promo2
- PromoInterval - describes the consecutive intervals Promo2 is started, naming the months the promotion is started anew. E.g. "Feb,May,Aug,Nov" means each round starts in February, May, August, November of any given year for that store

# Solution Strategy

The management method used was CRISP-DM:

**Step 01. Data Description:** The objective is to use statistical metrics to identify outliers, change data types and fillout NA's.

**Step 02. Feature Engineering:** In this step, new attributes are derived through the original variables, in order to better describe the phenomenon to be modeled and improve learning.

**Step 03. Data Filtering:** The objective is to filter out irrelevant rows and columns because they do not contain information for modeling.

**Step 04. Exploratory Data Analysis:** The objective is to understand the behavior of the business, find insights and measure the impact of variables on learning the model.

**Step 05. Data Preparation:** The objective is to improve model learning through data at the same scale.

**Step 06. Selection of resources:** The objective is to select the variables that best describe the model and eliminate redundant variables that do not have information for learning. The algorithm chosen was Boruta.

**Step 07. Machine Learning Modeling:** Machine Learning model training

**Step 08. Hyperparameter Fine Tunning:** The objective is choose the best values for each of the parameters of the model selected in the previous step.

**Step 09. Convert model performance to business values:** Convert model performance to a business result.

**Step 10. Deploy Model to Production:** Publish the model to a cloud environment so that other people or services can use the results to improve the business decision. The cloud application platform choosed was Heroku.

**Step 11. Telegram Bot:** Creation of a Telegram bot to facilitate forecast consultation and make decision-making faster.
