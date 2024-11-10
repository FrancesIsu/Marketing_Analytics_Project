# Marketing Analysis

## Project Background
ShopEasy is a global online retailer specializing in sports gear and fitness equipment. Its marketing focuses on customer engagement through social media, videos, and blogs. Despite recent marketing efforts, the company faces declining engagement and conversion rates. Leveraging data from customer reviews and campaign metrics, this project provides an in-depth analysis of 2024 data to identify actionable insights to boost customer engagement and conversion. Key areas analyzed include:

- **Conversion Rate:** Percentage of website visitors who make a purchase.

- **Customer Engagement:** Interaction level with content (clicks, likes, comments).

- **Customer Feedback:** Average ratings from customer reviews.


## Data Structure
ShopEasy’s data structure consists of five tables: customer reviews, customer journey, engagement data, customers, products, and geography. 

![ERD](https://github.com/user-attachments/assets/2d978bc0-0994-44aa-a7b9-56f4f0255520)

## Tools
- **SQL** queries used for data cleaning and preparation can be found below:
  - [Query 1](https://1drv.ms/f/c/4706fa5d979d067d/EvzirDOWlE5KnIxJwIz7UUoBb12kO4h2bKqd0oF0P60IBg?e=Ku85h7)
  - [Query 2](https://1drv.ms/f/c/4706fa5d979d067d/EvzirDOWlE5KnIxJwIz7UUoBb12kO4h2bKqd0oF0P60IBg?e=TrIJe0)
  - [Query 3](https://1drv.ms/u/c/4706fa5d979d067d/Ecikl2M6ZGlDn-EspUTu1ggBSJhi4-Xp_-DtD_ch3ma31A?e=nk7zDl)
  - [Query 4](https://1drv.ms/f/c/4706fa5d979d067d/EvzirDOWlE5KnIxJwIz7UUoBb12kO4h2bKqd0oF0P60IBg?e=nz9cRT)
  - [Query 5](https://1drv.ms/u/c/4706fa5d979d067d/EcMSzQZASapEgiOpcRJXhqMB4VCKOOkTITAkDNQJluw5yw?e=QwDmgM)

- **Python** script utilized in analysing sentiments based on customer reviews can be [downloaded here](http://localhost:8888/notebooks/Sentiment_Analysis.ipynb)
- **PowerBI** interactive dashboard can be [downloaded here](https://github.com/FrancesIsu/Marketing_Analytics_Project/blob/main/Marketing%20Analysis%20Portfolio%20Project.pbit)

## Data Analysis
Before the analysis, the data was examined to identify areas requiring cleaning and manipulation. This was achieved using SQL queries found in queries 1-5 above.
Some tables also required joining to create a more comprehensive view; the following script was used to join the tables:
``` SQL
SELECT 
	c.CustomerID, c.CustomerName, c.Email, 
	c.Gender, c.Age, 
CASE 
	WHEN Age <= 35 THEN 'Young'
	WHEN Age BETWEEN 36 AND 50 THEN 'MiddleAged'
	ELSE 'Old'
END AS AgeLabel, 
	g.Country, g.City
FROM dbo.customers c
LEFT JOIN dbo.geography g
	ON c.GeographyID = g.GeographyID;
```
The SQL queries were utilised in importing data into PowerBI to visualise the data and garner actionable insights.

## Executive Summary

### Overview of Findings
Conversion rate maintained a steady low throughout the year with peaks in January (18.5%), July(10.3%), September (15.7%), and December (10.2%). January accounted for the highest conversion rate.

Customer engagement on social media showed a steady decline in views, reaching a low of 161,251 in October. Despite an annual total of 2,982,369 views, only 15.37% converted to clicks, and 2.47% to likes. December saw slightly higher views than October but had similarly low clicks and likes, indicating a need for more engaging content to boost customer interaction.

Customer ratings averaged 3.67% which is consistently below the 4% target average, suggesting room for improvement in the level of customer satisfaction.

![Overview Page JPG](https://github.com/user-attachments/assets/dc18f403-93b3-4adf-a868-d5a80d91e808)


## Conversion Rate
- The conversion rate remained below 10% for most of the year, with January, July, September, and December as exceptions. This indicates seasonal peaks for certain products, suggesting an opportunity to boost conversion during lower-performing months through targeted marketing.
- November was the least-performing month, with no recorded conversions. The marketing team could focus on identifying products with potential appeal in the fall and develop strategies to effectively promote them during this period.
- January saw the highest conversion rate at 19.6%, driven by ski boots with a notable 150% conversion rate, likely due to seasonal demand. The marketing team could analyze and replicate the successful strategies used for ski boots across other products during their respective peak seasons. Categorizing products by seasonality and focusing marketing efforts accordingly could optimize conversion rates.
  
![Conversion Rate Table JPG](https://github.com/user-attachments/assets/51f875db-a288-4b2e-8573-90db7283ea58)


## Customer Engagement

- Views peaked in March and May, reaching 321,860 and 326,805 respectively—the highest of the year. Specific campaigns or promotions might have been run during these months. However, views declined steadily from August to December, indicating lower customer engagement in the latter months of the year. This could have resulted from a mismatch between the content posted and audience preferences in these months.
- Despite high views, clicks and likes remained low across the board. This suggests that the content lacked a strong call to action or engagement prompt, such as asking for feedback, sharing or clicking on links.
- Blog content performed best in March and May, accounting for 39.67% and 43.03% of total views in those months, while social media and videos saw steady but slightly lower engagement. This implies that video content or social media posts might not have been as effective in sparking engagement in those months.

![Monthly Views By Content Type_1 JPG](https://github.com/user-attachments/assets/a942a539-921d-403c-9a44-2ae506809482)


## Customer Feedback Analysis

- The majority of customer reviews are positive, with 140 reviews rated 4 stars and 135 rated 5 stars, reflecting overall customer satisfaction. In contrast, lower ratings (1 and 2 stars) are minimal, with only 26 and 57 reviews, respectively.
- Positive sentiments overwhelmingly surpass negative, mixed, and neutral sentiments, with 275 reviews reflecting satisfaction. Negative sentiments are present in 82 reviews, while mixed and neutral sentiments make up a smaller proportion. Although there is room for improvement, the overall sentiment is highly positive.
- Addressing concerns in mixed sentiment reviews presents an opportunity to further boost satisfaction and ratings
  
![Monthly Trend of Click, Likes and Views_1 JPG](https://github.com/user-attachments/assets/5bc8531c-c27a-4918-8319-c8b3375ab3f7)

  
## Recommendations

Based on the insights garnered from the analysis, the following recommendations are being proffered:
- **Seasonal Product Promotion:** Categorise products by seasonal demand and increase promotional efforts during peak periods to boost conversion rates. For example, promote ski boots and ice skates during winter (December - February) and golf clubs and swimming goggles in the summer (June - September).
- **Targeted Marketing Campaigns:** Focus campaigns on historically high-performing products such as ski boots, kayaks, and surfboards, particularly during their peak seasons.
- **Content Strategy:** Tailor content to the interests of the target audience and adopt more engaging formats like interactive blog posts and user-generated content to combat declining views.
- **Boost Engagement with Call-to-Actions:** Incorporate clear calls-to-action in social media, blogs, and videos, particularly during periods of lower engagement (October to December).
- **Address Mixed and Negative Feedback:** Analyze mixed and negative reviews to identify recurring issues. Implement plans to address these concerns and follow up with dissatisfied customers to resolve issues and encourage re-rating, to improve average ratings toward the 4% target.

## Limitations

- **Limited Customer Segmentation:** There’s no detailed breakdown by customer demographics (e.g., age, gender, location) or behaviour patterns. Without this segmentation, it’s challenging to understand which customer groups are engaging or converting and to tailor marketing strategies accordingly.

- **Focus on Annual Averages:** The analysis primarily considers monthly or annual trends without delving into weekly or daily variations, which may reveal short-term trends or the impact of specific events or promotions.

- The analysis does not account for any biases that may exist within the data collection or processing methods.


