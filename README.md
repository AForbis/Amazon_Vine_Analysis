# Amazon_Vine_Analysis

# Overview

  -  The topline view was that we needed to analyze Amazon reviews written by members of the paid Amazon Vine program. We picked the major appliances dataset [one of the datasets from Amazon's S3 bucket](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt), used PySpark to perform the ETL process to extract the dataset, transformed the data, connected to an AWS RDS instance, and loaded the transformed data into pgAdmin. Then we used Pandas to determine if there was any bias toward favorable reviews from Vine members in the dataset. 

# Results for the Major Appliances Dataset


![vine_table_pic](vine_table_pic.png)


![vine_summary_pic](vine_summary_pic.png)


# Summary

  - Approximately 51% of paid members gave products a 5 star rating compared to the 40% from unpaid members. That difference suggests a slight positivity bias from paid members, though it is difficult to draw conclusions considering there were only 35 paid members compared to the 4,957 unpaid members. 
  - One way to bolster the analysis would be to break out the star_rating by each point on the 5-point scale. This would provide additional exemplars of bias across each rating. You could also rerun this current analysis but with a reduced total vote threshold (e.g., 10). When the 20 vote filter was applied it cut the dataset down from 96,901 rows to 5,364. With a lower threshold you might get a more substantial sample of paid members than the 35 this analysis returned, which would also improve the assertion of positivity bias.

# Data Sources

1. [ETL in AWS RDS, pgAdmin, Google Collab](Amazon_Reviews_ETL.ipynb)
2. [Vine Analysis in Pandas](Vine_Review_Analysis.ipynb)
3. [Major Appliances data](https://s3.amazonaws.com/amazon-reviews-pds/tsv/index.txt)
