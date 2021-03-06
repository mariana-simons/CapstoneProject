Exploring the relationship between hotels Yelp user's stars and checkins
========================================================

### Data Science Capstone Project -  Yelp Final Presentation

author: Mariana Simons  
date: November 17, 2015


Introduction
========================================================

Question: **Do hotels with more Yelp user's stars get more checkins?** 

- *Primary objective:* To explore whether a higher Yelp user's stars rating has a profound effect on the success of hotels measured by the total number of their checkins.
- *Secondary objective:* To find out if there are additional factors confounding this relation.
- *Target audience:* Hotel owners

Methods
========================================================
right: 60%
### Exploratory Analysis 

![Figure 1](HotelsLogTotalCheckinsBoxplotStarsScatterplotReviews.png)
***
### Models Fitting 
<small> To answer our inferential question we'll build 3 models outlined below:  

1. First, a model that provides unadjusted estimate for the expected change in log(total checkins), with increase of stars as a numeric variable.   
2. Second, a model similar to 1, with stars converted to a categorical variable with 3 levels -  *low*, *medium*, *high*.    
3. Third, a model that estimates the confounding effect of number of reviews on the association between total checkin and star categories. </small>

 
Results
========================================================
<small> We have selected model 3 and its interpretation is given below: 
![Figure 2](SummaryFitModel3.png)
- Reference group: the hotels with *low* stars. P-values: significant
- -0.05 is the adjusted average totalCheckinlLog for the reference group. 
-  0.45 and 0.43 are the adjusted expected increase in mean totalCheckinlLog for hotels with *medium* and *high* stars, respectively, compared to hotels with *low* stars and reviewCountLog kept constant. 
- 1.15 is the expected increase in totalCheckinlLog in response to every one increase in reviewCountLog (i.e. 2.71(reviewCount)) and stars kept constant. 
</small> 

Discussion
========================================================
<small> 
**Implications**
- The adjustment for number of reviews in Model 3 reversed the sign and the magnitude of the intercept from 2.89 to -0.05. 
- There is decrease of 58% and 40% in the coefficients for hotels with *medium* and *high* stars compared to *low* stars, respectively, after adjusting for reviews counts.  
- Holding the number of reviews constant, hotels with *medium* compared with *high* stars appear to have marginal increase in mean totalCheckin = exp(0.45395-0.43045)=exp(0.0235)~1.  

**Conclusion:**
The answer of our question is that there is an increase in total checkins for hotels in the *medium* and *high* stars categories compared to hotels with *low* stars. The relationship between checkins and stars is non-linear and when it is adjusted for the number of reviews, the difference between checkins for hotels in the *medium* and *high* stars categories is phased out. </small>
