# Amazon_Vine_Analysis

## Overview
This project showcased an ability to use Amazon RDS and PySpark to examine a dataset and determine any bias. The database contained a list of reviews of video games. It also listed whether the reviewer was a Vine subscriber or a guest user. For this project, I chose to examine whether any patterns existed between a Vine reviewer and a guest reviewer. 

The dataset was accessed from the following URL:

https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz

## Results
### Vine reviews vs. non-Vine reviews
![Vine_Total_Reviews](https://user-images.githubusercontent.com/85756203/137772019-7a5cf395-2b6a-489a-83f1-19e5d2341d60.png)

- 94 reviews came from Vine
- 40,471 came from non-Vine reviews
### Number of 5-star reviews
![Vine_5stars](https://user-images.githubusercontent.com/85756203/137772034-7bb73fe8-77a7-4e7b-9c2f-c8ba2ca8552d.png)

- 48 Vine reviews gave 5-stars
- 15,663 non-Vine gave 5-stars
### Percentage of 5-star reviews
![Vine_5star%](https://user-images.githubusercontent.com/85756203/137772054-66cde5d2-ae2d-4a18-8c89-6924c6bd654f.png)

- 51.06 percent of Vine reviewers gave 5-stars
- 38.70 percent of non_Vine reviewers gave 5-stars

## Summary
The results do indicate a slight positivity bias among Vine reviewers. Vine reviewers gave 5-star ratings to video games 12% more than non-Vine reviewers.
That 12 percent difference may not be reliable given the difference in sample sizes (94 Vine reviewers to 40,471 non-Vine reviewers).

I want to test whether a Vine reviewer is more likely to have higher percentages of helpful_votes on their reviews. This test would help determine if the reviews were showing a positivity bias. I believe people would be more likely to find honest reviews helpful as opposed to overly complimentary reviews.

This test could be completed using much of the same process from the orignial test.

The difference would be creating a new threshold for the percent of reviews found helpful. Instead of reviews that had a 50% cutoff, I would use a 75% cutoff and create a new table called very_helpful_reviews. Then I would separate the reviews into Vine and non-Vine, and retrieve the count of each group. Like the 5-star reviews, we divide those numbers by the total number of very_helpful_reviews to get the final results.
