
# HDB exploratory data analysis and modeling

This is a first project for exploratory data analysis (EDA). Repository to find what factors
affect HDB price and which flat can be purchase at a good price.

## Libraries used

To run this project, the following libraries are needed

`numpy` `pandas` `matplotlib` `seaborn` 


## EDA process

Data taken from Singapore government data website:

[![data.gov](https://www.singstat.gov.sg/-/media/images/home-carousel-logos/logo-data.ashx)](https://data.gov.sg/dataset/resale-flat-prices)

Data consist of 11 attributes, 880371 records as of 27 Aug 2022. Data is first combined into
one dataframe. 

Remaining lease is re-calculated as there are missing values in there.

"flat_type" column has all strings changed to start with big caps and the rest all small 
caps.

"storey_range" column has dropped some rows as storey_range used are not used by most data.

"price_per_sqm" column is added by taking price divide by sqm for better comparison

Lastly, duplicates are removed.

## Models created
![Price per sqm for each flat type](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/flat%20types%20per%20sqm.png?raw=true)
Price per sqm for each flat type over the years shows that larger flat are cheaper in terms 
of per sqm before 2005. After 2005, 1 room and 2 room tend to have higher price in terms of 
per sqm.

![Price per sqm flat type](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/flat%20types%20per%20sqm%20violin.png?raw=true)
Price per sqm for each flat type over the years. Not much info can be drawn from here as data
looks skewed with outliers.

![Price per sqm per 10 year](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/flat%20types%20per%20sqm%20violin%20different%20year%20period.png?raw=true)
Price per sqm for each flat type after grouping into 10 years. From 2011 onwards, 1 room
have a huge increase in price per sqm on average. 2 to 5 rooms flats on average does not increase
by that much but have outliers which reach around 7 times of what was previously.

![Floor area, resale and per sqm](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/floor%20area%20price.png?raw=true)
Comparing resale price and price per sqm show that as floor area increase, price per sqm goes
lower and resale price goes up. The cross intersection at around 120sqm shows a good sqm 
floor are to look at.

![town increase price](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/town%20price.png?raw=true)
Recent 10 years data is focus on as that is when the price increased the most. Most expensive
and least expensive can be oberved.

![town increase percentage](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/town%20price%20increase.png?raw=true)
Which town increased the most or top few will be ideal to be looked at.

![Remaining lease](https://github.com/MikoPoh/HDB-EDA-data-analysis/blob/main/Charts/remaining%20lease.png?raw=true)
Even price is incresing, remaining lease will affect the price. Flats price tend to drop till
remaining lease of around 80 years and will increase afterwards.
## Conclusions
- Prices increased sharply only in recent 11 years
- Higher room number flat types which have larger floor areas have a positive correlation to resale price but no correlation to price per sqm
- Since there is no correlation between remaining lease and resale price and price per sqm, remaining lease possibly does not affect price directly
- However, certain flat types and models have higher price per sqm despite same room numbers.
    - Such as 1/2 room(s), DBSS and terrace.
- Towns that are over-priced in terms of price and sqm are
    - Bukit Timah
    - Bukit Merah
    - Queenstown
    - Marine Parade
- Towns that are best worth in terms of price and sqm are Woodlands and Jurong West
- In terms of ROI, Yishun town is the better choice as it has one of the lowest average resale price at average of S$376500 price and one the highest increase percentage of 3.64%
- If budget is not a factor, Queenstown and Kallang/Whampoa will be ideal for investment at 5.07% and 4.96% respectively
