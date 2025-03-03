# Summary of Findings

## Key Insights from Notebook
### Required Assignment 5.1: Will the Customer Accept the Coupon?

**Context**

Imagine driving through town and a coupon is delivered to your cell phone for a restaurant near where you are driving. Would you accept that coupon and take a short detour to the restaurant? Would you accept the coupon but use it on a subsequent trip? Would you ignore the coupon entirely? What if the coupon was for a bar instead of a restaurant? What about a coffee house? Would you accept a bar coupon with a minor passenger in the car? What about if it was just you and your partner in the car? Would weather impact the rate of acceptance? What about the time of day?

Obviously, proximity to the business is a factor on whether the coupon is delivered to the driver or not, but what are the factors that determine whether a driver accepts the coupon once it is delivered to them? How would you determine whether a driver is likely to accept a coupon?

**Overview**

The goal of this project is to use what you know about visualizations and probability distributions to distinguish between customers who accepted a driving coupon versus those that did not.

**Data**

This data comes to us from the UCI Machine Learning repository and was collected via a survey on Amazon Mechanical Turk. The survey describes different driving scenarios including the destination, current time, weather, passenger, etc., and then ask the person whether he will accept the coupon if he is the driver. Answers that the user will drive there ‘right away’ or ‘later before the coupon expires’ are labeled as ‘Y = 1’ and answers ‘no, I do not want the coupon’ are labeled as ‘Y = 0’.  There are five different types of coupons -- less expensive restaurants (under \$20), coffee houses, carry out & take away, bar, and more expensive restaurants (\$20 - $50).

**Deliverables**

Your final product should be a brief report that highlights the differences between customers who did and did not accept the coupons.  To explore the data you will utilize your knowledge of plotting, statistical summaries, and visualization using Python. You will publish your findings in a public facing github repository as your first portfolio piece.





### Data Description
Keep in mind that these values mentioned below are average values.

The attributes of this data set include:
1. User attributes
    -  Gender: male, female
    -  Age: below 21, 21 to 25, 26 to 30, etc.
    -  Marital Status: single, married partner, unmarried partner, or widowed
    -  Number of children: 0, 1, or more than 1
    -  Education: high school, bachelors degree, associates degree, or graduate degree
    -  Occupation: architecture & engineering, business & financial, etc.
    -  Annual income: less than \\$12500, \\$12500 - \\$24999, \\$25000 - \\$37499, etc.
    -  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    -  Number of times that he/she buys takeaway food: 0, less than 1, 1 to 3, 4 to 8 or greater
    than 8
    -  Number of times that he/she goes to a coffee house: 0, less than 1, 1 to 3, 4 to 8 or
    greater than 8
    -  Number of times that he/she eats at a restaurant with average expense less than \\$20 per
    person: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    -  Number of times that he/she goes to a bar: 0, less than 1, 1 to 3, 4 to 8 or greater than 8
    

2. Contextual attributes
    - Driving destination: home, work, or no urgent destination
    - Location of user, coupon and destination: we provide a map to show the geographical
    location of the user, destination, and the venue, and we mark the distance between each
    two places with time of driving. The user can see whether the venue is in the same
    direction as the destination.
    - Weather: sunny, rainy, or snowy
    - Temperature: 30F, 55F, or 80F
    - Time: 10AM, 2PM, or 6PM
    - Passenger: alone, partner, kid(s), or friend(s)


3. Coupon attributes
    - time before it expires: 2 hours or one day

### Problems

Use the prompts below to get started with your data analysis.  

1. Read in the `coupons.csv` file.




2. Investigate the dataset for missing or problematic data.

3. Decide what to do about your missing data -- drop, replace, other...

4. What proportion of the total observations chose to accept the coupon?



5. Use a bar plot to visualize the `coupon` column.

6. Use a histogram to visualize the temperature column.

**Investigating the Bar Coupons**

Now, we will lead you through an exploration of just the bar related coupons.  

1. Create a new `DataFrame` that contains just the bar coupons.


2. What proportion of bar coupons were accepted?


3. Compare the acceptance rate between those who went to a bar 3 or fewer times a month to those who went more.


4. Compare the acceptance rate between drivers who go to a bar more than once a month and are over the age of 25 to the all others.  Is there a difference?


5. Use the same process to compare the acceptance rate between drivers who go to bars more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry.


6. Compare the acceptance rates between those drivers who:

- go to bars more than once a month, had passengers that were not a kid, and were not widowed *OR*
- go to bars more than once a month and are under the age of 30 *OR*
- go to cheap restaurants more than 4 times a month and income is less than 50K.



7.  Based on these observations, what do you hypothesize about drivers who accepted the bar coupons?

### Independent Investigation

Using the bar coupon example as motivation, you are to explore one of the other coupon groups and try to determine the characteristics of passengers who accept the coupons.  

### My choice of coupon group: Coffee House

Now, let's analyze the characteristics of passengers who accept coffee house coupons.  

1. First, let's calculate the overall acceptance rate for coffee house coupons:

2. Let's explore various factors that might influence coffee house coupon acceptance:
   
- Frequency of Coffee House Visits
- Time of Day
- Age Group
- Income Level

Step 2 Findings:

Characteristics of Likely Acceptors of the Coffee House Coupon based on the analysis:
   
- Coffee house visitors (1+ times per months) are about 65% likely to accept coffee house coupons
- Those receiving coupons in the morning (10AM) are likely to accept coupon with 64% rate
- Young adults below 21 are the most likely age group to accept coffee house coupon
- Income Level does not seem to have a strong influence on the coffee house coupon acceptance rate

3. Now I will see whether the combination of the above characteristics increases the chance of accepted coffee house coupon: 
- Group 1: Coffee house visitors (1+ times per months) and under age of 21
- Group 2: Those receiving coupons in the morning (10AM) and under age of 21 
- Group 3: Coffee house visitors (1+ times per months) and those receiving coupons in the morning (10AM)
- Group 4: Coffee house visitors (1+ times per months) and under age of 21, receiving coupons in the morning (10AM)

Step 3 findings. 

Analysis showed that group 3: Coffee house visitors (1+ times per months) and those receiving coupons in the morning (10AM) were the most likely group to accept the coffee house coupon (81.29%) and hence is be recommended for targeting on the basis of this analysis.

## Code Outputs
```
       destination  passanger weather  temperature  time  \
0  No Urgent Place      Alone   Sunny           55   2PM   
1  No Urgent Place  Friend(s)   Sunny           80  10AM   
2  No Urgent Place  Friend(s)   Sunny           80  10AM   
3  No Urgent Place  Friend(s)   Sunny           80   2PM   
4  No Urgent Place  Friend(s)   Sunny           80   2PM   

                  coupon expiration  gender age      maritalStatus  ...  \
0        Restaurant(<20)         1d  Female  21  Unmarried partner  ...   
1           Coffee House         2h  Female  21  Unmarried partner  ...   
2  Carry out & Take away         2h  Female  21  Unmarried partner  ...   
3           Coffee House         2h  Female  21  Unmarried partner  ...   
4           Coffee House         1d  Female  21  Unmarried partner  ...   

   CoffeeHouse CarryAway RestaurantLessThan20 Restaurant20To50  \
0        never       NaN                  4~8              1~3   
1        never       NaN                  4~8              1~3   
2        never       NaN                  4~8              1~3   
3        never       NaN                  4~8              1~3   
4        never       NaN                  4~8              1~3   

  toCoupon_GEQ5min toCoupon_GEQ15min toCoupon_GEQ25min direction_same  \
0                1                 0                 0              0   
1                1                 0                 0              0   
2                1                 1                 0              0   
3                1                 1                 0              0   
4                1                 1                 0              0   

  direction_opp  Y  
0             1  1  
1             1  0  
2             1  1  
3             1  0  
4             1  0  

[5 rows x 26 columns]

Missing values:
 car                     12576
Bar                       107
CoffeeHouse               217
CarryAway                 151
RestaurantLessThan20      130
Restaurant20To50          189
dtype: int64

Number of duplicate rows: 74

Data types:
destination             object
passanger               object
weather                 object
temperature              int64
time                    object
coupon                  object
expiration              object
gender                  object
age                     object
maritalStatus           object
has_children             int64
education               object
occupation              object
income                  object
car                     object
Bar                     object
CoffeeHouse             object
CarryAway               object
RestaurantLessThan20    object
Restaurant20To50        object
toCoupon_GEQ5min         int64
toCoupon_GEQ15min        int64
toCoupon_GEQ25min        int64
direction_same           int64
direction_opp            int64
Y                        int64
dtype: object


<Figure size 1000x4000 with 8 Axes>


Unique values in destination:
destination
No Urgent Place    6283
Home               3237
Work               3164
Name: count, dtype: int64

Unique values in passanger:
passanger
Alone        7305
Friend(s)    3298
Partner      1075
Kid(s)       1006
Name: count, dtype: int64

Unique values in weather:
weather
Sunny    10069
Snowy     1405
Rainy     1210
Name: count, dtype: int64

Unique values in time:
time
6PM     3230
7AM     3164
10AM    2275
2PM     2009
10PM    2006
Name: count, dtype: int64

Unique values in coupon:
coupon
Coffee House             3996
Restaurant(<20)          2786
Carry out & Take away    2393
Bar                      2017
Restaurant(20-50)        1492
Name: count, dtype: int64

Unique values in expiration:
expiration
1d    7091
2h    5593
Name: count, dtype: int64

Unique values in gender:
gender
Female    6511
Male      6173
Name: count, dtype: int64

Unique values in age:
age
21         2653
26         2559
31         2039
50plus     1788
36         1319
41         1093
46          686
below21     547
Name: count, dtype: int64

Unique values in maritalStatus:
maritalStatus
Married partner      5100
Single               4752
Unmarried partner    2186
Divorced              516
Widowed               130
Name: count, dtype: int64

Unique values in education:
education
Some college - no degree                  4351
Bachelors degree                          4335
Graduate degree (Masters or Doctorate)    1852
Associates degree                         1153
High School Graduate                       905
Some High School                            88
Name: count, dtype: int64

Unique values in occupation:
occupation
Unemployed                                   1870
Student                                      1584
Computer & Mathematical                      1408
Sales & Related                              1093
Education&Training&Library                    943
Management                                    838
Office & Administrative Support               639
Arts Design Entertainment Sports & Media      629
Business & Financial                          544
Retired                                       495
Food Preparation & Serving Related            298
Healthcare Practitioners & Technical          244
Healthcare Support                            242
Community & Social Services                   241
Legal                                         219
Transportation & Material Moving              218
Architecture & Engineering                    175
Personal Care & Service                       175
Protective Service                            175
Life Physical Social Science                  170
Construction & Extraction                     154
Installation Maintenance & Repair             133
Production Occupations                        110
Building & Grounds Cleaning & Maintenance      44
Farming Fishing & Forestry                     43
Name: count, dtype: int64

Unique values in income:
income
$25000 - $37499     2013
$12500 - $24999     1831
$37500 - $49999     1805
$100000 or More     1736
$50000 - $62499     1659
Less than $12500    1042
$87500 - $99999      895
$75000 - $87499      857
$62500 - $74999      846
Name: count, dtype: int64

Unique values in car:
car
Scooter and motorcycle                      22
Mazda5                                      22
do not drive                                22
crossover                                   21
Car that is too old to install Onstar :D    21
Name: count, dtype: int64

Unique values in Bar:
Bar
never    5197
less1    3482
1~3      2473
4~8      1076
gt8       349
Name: count, dtype: int64

Unique values in CoffeeHouse:
CoffeeHouse
less1    3385
1~3      3225
never    2962
4~8      1784
gt8      1111
Name: count, dtype: int64

Unique values in CarryAway:
CarryAway
1~3      4672
4~8      4258
less1    1856
gt8      1594
never     153
Name: count, dtype: int64

Unique values in RestaurantLessThan20:
RestaurantLessThan20
1~3      5376
4~8      3580
less1    2093
gt8      1285
never     220
Name: count, dtype: int64

Unique values in Restaurant20To50:
Restaurant20To50
less1    6077
1~3      3290
never    2136
4~8       728
gt8       264
Name: count, dtype: int64


Percentage of missing values in 'car' column: 99.15%
The 'car' column has been removed from the dataset.


Total observations: 12684
Accepted coupons: 7210
Acceptance rate: 56.84%


<Figure size 800x600 with 1 Axes>

<Figure size 1000x600 with 1 Axes>

Total bar coupons: 2017
Accepted bar coupons: 827
Acceptance rate: 41.00%


Acceptance rate for those who went to a bar 3 or fewer times a month: 37.06%
Acceptance rate for those who went to a bar more than 3 times a month: 76.88%


Acceptance rate for drivers who go to a bar more than once a month and are over 25: 69.52%
Acceptance rate for all others: 33.50%
Conclusion: Drivers who go to a bar more than once a month and are over 25 are more than twice as likely to accept the Bar coupon than other drivers


Acceptance rate for the specified group: 71.32%
Acceptance rate for all others: 33.50%
Conclusion: Drivers who go to a bar more than once a month and had passengers that were not a kid and had occupations other than farming, fishing, or forestry are more than twice as likely to accept the Bar coupon than other drivers


Acceptance rate for Group 1: 71.32%
Acceptance rate for Group 2: 73.13%
Acceptance rate for Group 3: 78.70%


All three groups are more than 70% likely to accept coupons, with Group 3 being the most likely to accept them: 78.70% chance. Hence drivers who go to cheap restaurants more than 4 times a month and income is less than 50K are reccommended to target for sending bar coupouns.


Overall coffee house coupon acceptance rate: 56.84%


<Figure size 800x600 with 1 Axes>

Acceptance rate by coffee house visit frequency:
CoffeeHouse
4~8      0.685874
gt8      0.657895
1~3      0.647793
less1    0.481860
never    0.188781
Name: Y, dtype: float64


Acceptance rate by time of day:
time
10AM    0.640712
2PM     0.547859
7AM     0.445783
10PM    0.424242
6PM     0.412626
Name: Y, dtype: float64


Acceptance rate by age group:
age
below21    0.696774
21         0.524349
26         0.514828
46         0.513636
41         0.501538
31         0.476726
36         0.467662
50plus     0.420183
Name: Y, dtype: float64


Acceptance rate by income level:
income
$87500 - $99999     0.557196
Less than $12500    0.551948
$37500 - $49999     0.542373
$12500 - $24999     0.540404
$50000 - $62499     0.503650
$100000 or More     0.494382
$25000 - $37499     0.473438
$62500 - $74999     0.436364
$75000 - $87499     0.296610
Name: Y, dtype: float64


Coffee house coupon acceptance rate for group 1: 76.27%
Increased likelihood of acceptance (compared to overall) : 152.77%


Coffee house coupon acceptance rate for group 2: 74.29%
Increased likelihood of acceptance (compared to overall) : 148.79%


Coffee house coupon acceptance rate for group 3: 81.29%
Increased likelihood of acceptance (compared to overall) : 162.83%


Coffee house coupon acceptance rate for group 4: 80.00%
Increased likelihood of acceptance (compared to overall) : 160.24%


<Figure size 640x480 with 1 Axes>
```
