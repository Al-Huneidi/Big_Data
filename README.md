# Big_Data
Analysis of big data using SQL, AWS, PySpark, Apache Spark, NLP, and ML.

Links to Colab Notebooks:

16_4_2
https://colab.research.google.com/drive/1522aJbAWRDXM_DlGkgPKKRv9DlcvtPEi

16.4.3
https://colab.research.google.com/drive/1IOnzRLM_f7EPCi_b5nlY6whZg-3rINxh

16.6.1
https://colab.research.google.com/drive/1bq8rUPUvOMNmYgcHNcpMHTiOQKFLvixs

16.6.2
https://colab.research.google.com/drive/1uSG34iEgEMYU_6QZQnyalVZ_OXfG2Jf4

16.6.3
https://colab.research.google.com/drive/1SpSHuGb0fB88da9xG3IHcTFDObGs6j5H

16.6.4
https://colab.research.google.com/drive/1g3bb-vSeeoO8_1jzGKkGosCiTiD2ou9V

S3_connect.ipynb
https://colab.research.google.com/drive/1TeSwJJi22aFJG8J4yjn6MLzil9Uig1OR

Resources:

user_data.csv

user_payment.csv


# Challenge - Do Vine Reviews of Mobile Apps Indicate Bias?

## Objectives
	•	Perform ETL on one of the review datasets using PySpark.
	•	Store your results on an AWS RDS database, pgAdmin.
	•	Determine if reviews are biased using PySpark with the appropriate statistical methods.
  
### Analysis Report

Do Vine Reviews of Mobile Apps Indicate Bias?

After cleaning the dataset, I created a Vine DataFrame from the dataset in order to analyze to find out if Vine reviews indicate bias with the following columns to see if there was a correlation between any of the columns indicating a bias:

review_id
star_rating
helpful_votes
total_votes
vine
verified purchase

There are a total of 5,033,238 reviews for mobile apps.  After making sure there were no null values chose to look at the mobile app reviews that had greater than or equal to 20 reviews, which came to a total of 138,941.

Then I calculated the percentage of helpful votes and kept the ones that had greater than or equal 50% helpful votes, which is 129,508.

Then I counted the ones that DO have a Vine review. I was quite surprised when I found there were ZERO reviews with a Vine review.  I still created the code to further analyze for future use should the parameters and the dataset change. 

I moved forward and counted the ones that DO NOT have a Vine review to make sure the total was the same as the total reviews to double check my process. There are 129,508 reviews.


I calculated the number of 5-star reviews. Then ran the statistics.  The reviews that DO have a Vine review came up with nothing since there are no reviews.
The reviews that DO NOT have a Vine review statistics are:
Count:  129508
Mean: 3.4707662847082807
Standard Deviation: 1.690615281507636
Min: 1
Max: 5
This tells us that the average review is approximately 3.5-stars.

I then calculated the percentage of 5-star reviews. The percentage of 5-star reviews throw an error because division by zero is undefined and there are zero reviews that DO have a Vine review.  The total number of reviews that DO NOT have a Vine review is 59,271 for a percentage of 46% (rounded) of reviews receiving 5-stars.

In conclusion, there is no evidence that reviews including Vine reviews show a bias.  I recommend further analysis of mobile apps with less than 20 reviews.  However, mobile apps with less than 20 reviews might not have enough reviews to suggest that the analysis tells the correct story. That is a decision stakeholders must make in order to determine if Vine reviews suggest bias in reviews.


Links to Colab Notebooks:

RDS file
Challenge.ipynb
https://colab.research.google.com/drive/1uPk7UZUcpC0FD0O3zZ8KG0ue_5xQS1nC

Analysis file
Vine_Analysis.ipynb
https://colab.research.google.com/drive/1o1AXd2gF__8ybeQQoTunIbgcXq8EcWsv

Resources:

Amazon Reviews: https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Mobile_Apps_v1_00.tsv.gz
