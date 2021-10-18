# Amazon_Vine_Analysis

## Overview
This assignment was meant to test our ability to use Amazon RDS and PySpark to examine a dataset and determine any bias. For this assignment, I chose to examine video game data from the list of reviews dataset. The dataset was accessed from the following URL:

https://s3.amazonaws.com/amazon-reviews-pds/tsv/amazon_reviews_us_Video_Games_v1_00.tsv.gz

## Results
### Vine reviews vs. non-Vine reviews
- 94 reviews came from Vine
- 40,471 came from non-Vine reviews
### Number of 5-star reviews
- 48 Vine reviews gave 5-stars
- 15,663 non-Vine gave 5-stars
### Percentage of 5-star reviews
- 51.06 percent of Vine reviewers gave 5-stars
- 38.70 percent of non_Vine reviewers gave 5-stars

## Summary
The results do indicate a slight positivity bias among Vine reviewers. Vine reviewers gave 5-star ratings to video games 12% more than non-Vine reviewers.
That 12 percent difference may not be reliable given the difference in sample sizes (94 Vine reviewers to 40,471 non-Vine reviewers).

I want to test whether a Vine reviewer is more likely to have higher percentages of helpful_votes on their reviews. This test would help determine if the reviews were showing a positivity bias. I believe people would be more likely to find honest reviews helpful as opposed to overly complimentary reviews.

This test could be completed using much of the same process from the orignial test.

The difference would be creating a new threshold for the percent of reviews found helpful. Instead of reviews that had a 50% cutoff, I would use a 75% cutoff and create a new table called very_helpful_reviews. Then I would separate the reviews into Vine and non-Vine, and retrieve the count of each group. Like the 5-star reviews, we divide those numbers by the total number of very_helpful_reviews to get the final results.
