# Amazon_Vine_Analysis
## Overview
The purpose of this project is to analyze Amazon reviews writen by the paid Amazon Vine Program members, which is a service used by manufacturers and publishers to receive reviews of their products. We then use this data to determine if there is bias between the paid Vine Members and the non-paid Vine members reviews. 
This program allows companies to pay a fee to Amazon who then distribute the companies products to Amazon's Vine Members and these members are required to write a review, so we need to analyze the percentage of 5 star reviews between Vine Members and non-members compared to total ratings. As part of the challenge, we were asked to choose from a list of 50 datasets then extract, tranform, and load this data into a dataframe for analysis. Of the 50 datasets, I chose the Electronics Category. For this analysis we utilized Pyspark to extract and transform the data, connect to an AWS RDS instance, then load the transformed data into pgadmin. In order to utilize PySpark and its libraries we used Google Colab and connected this to Postgres in order to create tables in SQL and export the results.
## Results
The datset I chose had over 3 million reviews, so in order to focus on reviews that would be considered more helpful I needed to filter the dataset by;
- Count of total votes equal or greater than 20
- Percent of helpful votes to total votes equal or greater than 50%
![This is an image](https://github.com/weise142/Amazon_Vine_Analysis/blob/main/images/DataGreater20-50.png)
As we can see, by using these filters the results were reduced from 3 million to 50,700. By filtering these results we are able to answer the following questions;
- How many reviews were there for Vine members and non-Vine members? Vine members made up a small percentage of 2.1% or 1,080, where the remaining 97.9% or 49,659 were from non-Vine members.
![This is an image](https://github.com/weise142/Amazon_Vine_Analysis/blob/main/images/VineNonVineTotal.png)
![This is an image](https://github.com/weise142/Amazon_Vine_Analysis/blob/main/images/Vinetable.png)
![This is an image](https://github.com/weise142/Amazon_Vine_Analysis/blob/main/images/NonVinetable.png)
- How many 5 star reviews were made by Vine members and non-Vine members? As we can see, Vine members gave 454 5 star reviews out of their 1,080 reviews and non-Vine members gave 23,034 5 star reviews out of their 49,649 reviews.
  - Vine members rate 42% of their reviews at 5 stars, while non-Vine members rated 46.4% of their reviews at 5 stars.
## Summary
Based on the above results, members of the paid Vine service did not show a bias when rating these products as compared to the Non-Vine members. Based on the percentages of 42% versus 46.4% of 5 star reviews between Vine and non-Vine members means Vine members may be more critical of the products they receive than the non-Vine members, but to confirm this assumption we should include all of the data not just the filtered data. 
![This is an image](https://github.com/weise142/Amazon_Vine_Analysis/blob/main/images/un-filteredtotal.png)
Based on these unfiltered results we can see that Vine members give far less 5 star reviews than non-Vine members and are more critical of the products they receive. To further support the conclusion here, we should include all of the data from the 50 datasets to determine if there is a bias for Vine members compared to non-Vine members.
