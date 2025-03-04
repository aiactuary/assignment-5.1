# Required Assignment 5.1: Will the Customer Accept the Coupon?

**Link to the Jupyter notebook:**
https://github.com/aiactuary/assignment-5.1/blob/27d008254d9c037fd0ddd45655644d576435e30d/PracticalApplication1_OlenaKirzhner.ipynb

## **Context**

We were given a dataset that contains information about the drivers and whether they accepted a coupon offered to them or not. We were asked to anlayse the dataset and distinguish between customers who accepted a coupon versus those that did not. We were also asked to summarize our findings and recommend actionable items.


## **Executive Summary of the findings**

Based on the analysis perfromed, we were able to indetify the groups that were most likely to accept coupons sent to them: 
 - Bar coupons: The most likely group to accept those coupons is the drivers who go to cheap restaurants more than 4 times a month and income is less than 50K, hence they are most reccommended to target for sending bar coupouns. 
 - Coffee house coupons: Coffee house visitors (1+ times per months) and those receiving coupons in the morning (10AM) were the most likely group to accept the coffee house coupon (81.29%) and hence they are most reccommended to target for sending bar coupouns.

Should these recommendations be implemented, the overall acceptance rate of coupons should increase significantly.

## **Additional details of the analysis performed**

### 1. Data investigation: 
Dataset was investigated for missing or problematic data. It was identified that the 'car' column had 99.15% of the values missing. Such large portion of missing values would deem this column not suitable to be included in analysis, so the 'car' column has been removed from the dataset.

### 2. Overall Acceptance Rate: 
The data set showed an overall acceptance rate of 56.84% (Total observations: 12684; Accepted coupons: 7210). For the analysis to be useful, we needed to determine which characteristics (or combinations of thereof) will significantly increase acceptance rate relative to that benchmark.

### 3. Bar coupouns:
Various characteristics of the drivers were analysed to identify those that increase the likelihood of coupon acceptance:
    - Acceptance rate for those who went to a bar 3 or fewer times a month was 37.06%: less than half of the Acceptance rate for those who went to a bar more than 3 times a month: 76.88%.
    - Drivers who go to a bar more than once a month and are over 25 are more than twice as likely to accept the Bar coupon than other drivers: Acceptance rate for drivers who go to a bar more than once a month and are over 25: 69.52%; while Acceptance rate for all others: 33.50%
    - A number or groups with various driver characteristics were analysed. The most likely group to accept Bar coupons was the drivers who go to cheap restaurants more than 4 times a month and have income of less than 50K (78.70%) and hence this group is reccomended for targeting bar coupons.

### 4. Coffee House Coupons:
Various characteristics of the drivers were analysed to identify those that increase the likelihood of coupon acceptance. The analysis showed that:
 - Coffee house visitors (1+ times per months) are about 65% likely to accept coffee house coupons
 - Those receiving coupons in the morning (10AM) are likely to accept coupon with 64% rate
 - Young adults below 21 are the most likely age group to accept coffee house coupon
When above characteristics were combined, analysis showed that Coffee house visitors (1+ times per months) who are receiving coupons in the morning (10AM) were the most likely group to accept the coffee house coupon (81.29%). Hence this group is recommended for coffee house coupons targeting.

