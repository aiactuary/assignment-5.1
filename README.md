#Required Assignment 5.1: Will the Customer Accept the Coupon?

**Link to the Jupyter notebook:**
https://github.com/aiactuary/assignment-5.1/blob/2378af20ba71cd24118c75cf53c883904d71518e/PracticalApplication1_OlenaKirzhner.ipynb

##**Context**

We were given a dataset that contains information about the drivers and whether they accepted a coupon offered to them or not. We were asked to anlayse the dataset and distinguish between customers who accepted a coupon versus those that did not. We were also asked to summarize our findings and recommend actionable items.


##**Executive Summary of the findings**

Based on the analysis perfromed, we were able to indetify the groups that were most likely to accept coupons sent to them: 
 - Bar coupons: The most likely group to accept those coupons is the drivers who go to cheap restaurants more than 4 times a month and income is less than 50K, hence they are most reccommended to target for sending bar coupouns. 
 - Coffee house coupons: Coffee house visitors (1+ times per months) and those receiving coupons in the morning (10AM) were the most likely group to accept the coffee house coupon (81.29%) and hence they are most reccommended to target for sending bar coupouns.

Should these recommendations be implemented, the overall acceptance rate of coupons should increase significantly.

##**Additional details of the analysis performed**

###1. Data investigation: 
Dataset was investigated for missing or problematic data. It was identified that the 'car' column had 99.15% of the values missing. Such large portion of missing values would deem this column not suitable to be included in analysis, so the 'car' column has been removed from the dataset.

###2. Analyzing starting point of the analysis: 
The data set showed an overall acceptance rate of 56.84% (Total observations: 12684; Accepted coupons: 7210). For the analysis to be useful, we needed to determine which characteristics (or combinations of thereof) will significantly increase acceptance rate relative to that benchmark.

###3. Zooming in on Bar coupouns:
Acceptance rate: 41.00% shows that Bar coupons were accepted less than others (41% < 56.84%).
    - Acceptance rate for those who went to a bar 3 or fewer times a month was 37.06%: less than half of the Acceptance rate for those who went to a bar more than 3 times a month: 76.88%.
    - 
