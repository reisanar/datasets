---
title: "Exploring and Analyizing Wine Enthusiast Reviews"
output: 
  html_document:
    toc: true
    toc_float: true
    theme: united
    keep_md: true
---
# Introduction
Turning 21 is a milestone in everyone's life and usually, people celebrate it with a family dinner and glass of wine. But, how does one find the best wine considering that person has never had alcohol. 

- Do they get the best rated/most expensive bottle? (Too bad college students are poor) 
- Do they try to find the best value wine? (Ballin' on a budget)

- Or do they follow Jess from New Girl? (Obviously, the only option)

Let's take a deep dive and answer these pressing questions!

Our project investigates ~120,000 wine reviews with characteristics such as variety, vintage, winery, price, etc. This is our Final Project for Intro to Data Science (Spring 2020) class, and we thought it was a bit too easy, so we decided to expand it and take it a step further.

# Prerequisites

Loading the required packages

```r
library(tidyverse)
library(dplyr)
library(ggplot2)
library(scales)
```

# Dataset

Import processed data, which can be found [here](https://github.com/C4rbyn3m4n/wine_reviews_data_analysis/blob/master/data/processed_data/preprocessing.nb.html). Note: This file also credits our dataset curators and outlines our data cleaning pipeline.


```r
#read preprocessed data
wines <- read.csv(file = '../data/processed_data/wines.csv')
```

Get a sample of the dataset for easy testing. However, for our final report, we ran all of our code on the full wines dataset to get more accurate results.

```r
#set seed value to birthday of Ricardo Rodriguez, American wrestler and ring announcer and Dr. Reinaldo (Rei) Sanchez-Arias
set.seed(19630217)

#set percentage to test with for simplicity, if needed
percentage <- 5
wine_sample<- sample_n(wines, percentage/100*nrow(wines))
```

## Rating Classification

Wines are normally classified in categories as found on this [website](https://www.winemag.com/2010/04/09/you-asked-how-is-a-wines-score-determined/). To create a more rich dataset we added the field `rating_category` determined as:

|Category  | Rating  | Description                                            |
|----------|---------|--------------------------------------------------------|
|Classic   |	98-100 | The pinnacle of quality.                               |
|Superb    |	94-97	 | A great achievement.                                   |
|Excellent |	90-93	 | Highly recommended.                                    |
|Very Good |  87-89	 | Often good value; well recommended.                    |
|Good	     |  83-86	 | Suitable for everyday consumption; often good value.   |
|Acceptable|	80-82	 | Can be employed in casual, less-critical circumstances |

This allows to take a quantitative data and turn it into qualitative data, which can be used for data visualization later. 


```r
# function to add rating
rating_category <- function(points){
  if(points>=98){
    return("Classic")
  }
  else if (points>=94){
    return("Superb")
  }
  else if(points>=90){
    return("Excellent")
  }
  else if(points>=87){
    return("Very Good")
  }
  else if(points>=83){
    return("Good")
  }
  else{
    return("Acceptable")
  }
}

wines<- wines %>%
  rowwise() %>%
  mutate(rating_category = rating_category(points))
head(wines)
```

```
## Source: local data frame [6 x 16]
## Groups: <by row>
## 
## # A tibble: 6 x 16
##   title alcohol category vintage designation country province region subregion
##   <fct>   <dbl> <fct>      <int> <fct>       <fct>   <fct>    <fct>  <fct>    
## 1 Nico…    12.5 White       2013 "Vulkà Bia… Italy   Sicily … "Etna" ""       
## 2 Quin…    13   Red         2011 "Avidagos"  Portug… Douro    ""     ""       
## 3 Rain…    12.5 White       2013 ""          US      Oregon   "Will… "Willame…
## 4 St. …    12   White       2013 "Reserve L… US      Michigan "Lake… ""       
## 5 Swee…    13.5 Red         2012 "Vintner's… US      Oregon   "Will… "Willame…
## 6 Tand…    14   Red         2011 "Ars In Vi… Spain   Norther… "Nava… ""       
## # … with 7 more variables: variety <fct>, winery <fct>, price <int>,
## #   points <int>, taster_name <fct>, taster_twitter_handle <fct>,
## #   rating_category <chr>
```
## Create a Reviewer Profile
Each reviewer has there own bias. In order to offset that we made a "profile" for each reviewer. This profile allows us to later normalize the wine points for more robust apples to apples comparison.

### Split Taster Data
To make our dataframes more managable we split reduntant information about the tasters into a new dataframe.

```r
tasters <- wines %>%
  select(taster_name, taster_twitter_handle) %>% 
  unique()
tasters
```

```
## Source: local data frame [20 x 2]
## Groups: <by row>
## 
## # A tibble: 20 x 2
##    taster_name          taster_twitter_handle
##    <fct>                <fct>                
##  1 "Kerin O’Keefe"      "@kerinokeefe"       
##  2 "Roger Voss"         "@vossroger"         
##  3 "Paul Gregutt"       "@paulgwine "        
##  4 "Alexander Peartree" ""                   
##  5 "Michael Schachner"  "@wineschach"        
##  6 "Anna Lee C. Iijima" ""                   
##  7 "Virginie Boone"     "@vboone"            
##  8 "Matt Kettmann"      "@mattkettmann"      
##  9 ""                   ""                   
## 10 "Sean P. Sullivan"   "@wawinereport"      
## 11 "Jim Gordon"         "@gordone_cellars"   
## 12 "Joe Czerwinski"     "@JoeCz"             
## 13 "Anne Krebiehl MW"   "@AnneInVino"        
## 14 "Lauren Buzzeo"      "@laurbuzz"          
## 15 "Mike DeSimone"      "@worldwineguys"     
## 16 "Jeff Jenssen"       "@worldwineguys"     
## 17 "Susan Kostrzewa"    "@suskostrzewa"      
## 18 "Carrie Dykes"       ""                   
## 19 "Fiona Adams"        "@bkfiona"           
## 20 "Christina Pickard"  "@winewchristina"
```


Drop `taster_twitter_handle` in wines dataframe to reduce reduntant information.

```r
wines <- wines %>%
  select(-taster_twitter_handle)
head(wines)
```

```
## Source: local data frame [6 x 15]
## Groups: <by row>
## 
## # A tibble: 6 x 15
##   title alcohol category vintage designation country province region subregion
##   <fct>   <dbl> <fct>      <int> <fct>       <fct>   <fct>    <fct>  <fct>    
## 1 Nico…    12.5 White       2013 "Vulkà Bia… Italy   Sicily … "Etna" ""       
## 2 Quin…    13   Red         2011 "Avidagos"  Portug… Douro    ""     ""       
## 3 Rain…    12.5 White       2013 ""          US      Oregon   "Will… "Willame…
## 4 St. …    12   White       2013 "Reserve L… US      Michigan "Lake… ""       
## 5 Swee…    13.5 Red         2012 "Vintner's… US      Oregon   "Will… "Willame…
## 6 Tand…    14   Red         2011 "Ars In Vi… Spain   Norther… "Nava… ""       
## # … with 6 more variables: variety <fct>, winery <fct>, price <int>,
## #   points <int>, taster_name <fct>, rating_category <chr>
```

### Create Reviewer Metrics
Each reviewers profile includes the following metrics to create a profile: 

- `avg_points` which is the average of all the reviewer's scores

- `sd_points` which is the standard deviation of all the reviewer's scores

- `var_points` which is the variance of all the reviewer's scores

- `reviews` which is the number of reviews conducted


```r
taster_rating_profile <- wines %>%
  group_by(taster_name) %>%
  summarize(
    avg_points = mean(points),
    sd_points = sd(points),
    var_points = var(points),
    reviews = n()
  )
```

```
## Warning: Grouping rowwise data frame strips rowwise nature
```

```r
tasters <- inner_join(tasters, taster_rating_profile, by = "taster_name")
head(tasters)
```

```
## Source: local data frame [6 x 6]
## Groups: <by row>
## 
## # A tibble: 6 x 6
##   taster_name       taster_twitter_hand… avg_points sd_points var_points reviews
##   <fct>             <fct>                     <dbl>     <dbl>      <dbl>   <int>
## 1 Kerin O’Keefe     "@kerinokeefe"             88.9      2.49       6.22    9990
## 2 Roger Voss        "@vossroger"               88.7      3.04       9.25   23781
## 3 Paul Gregutt      "@paulgwine "              89.1      2.82       7.97    8845
## 4 Alexander Peartr… ""                         85.8      1.95       3.79     385
## 5 Michael Schachner "@wineschach"              86.9      3.03       9.17   14430
## 6 Anna Lee C. Iiji… ""                         88.4      2.57       6.63    4254
```


## Normalized Points
As mentioned, each reviewer has a different bias. To offset this, we created a normalized metric, `norm_points`, by looking at the number of standard deviations a wine is from the reviewer's `avg_points`. This gives us a more accurate representation of which wines are "better" than the rest.


```r
normalize_points <- function(data){
  left_join(data, tasters, by = "taster_name")%>%
    rowwise() %>%
    mutate(norm_points = (points-avg_points)/sd_points) %>%
    select(-avg_points, -sd_points, -var_points, -taster_twitter_handle, -reviews)
}

wines <- normalize_points(wines)
head(wines) 
```

```
## Source: local data frame [6 x 16]
## Groups: <by row>
## 
## # A tibble: 6 x 16
##   title alcohol category vintage designation country province region subregion
##   <fct>   <dbl> <fct>      <int> <fct>       <fct>   <fct>    <fct>  <fct>    
## 1 Nico…    12.5 White       2013 "Vulkà Bia… Italy   Sicily … "Etna" ""       
## 2 Quin…    13   Red         2011 "Avidagos"  Portug… Douro    ""     ""       
## 3 Rain…    12.5 White       2013 ""          US      Oregon   "Will… "Willame…
## 4 St. …    12   White       2013 "Reserve L… US      Michigan "Lake… ""       
## 5 Swee…    13.5 Red         2012 "Vintner's… US      Oregon   "Will… "Willame…
## 6 Tand…    14   Red         2011 "Ars In Vi… Spain   Norther… "Nava… ""       
## # … with 7 more variables: variety <fct>, winery <fct>, price <int>,
## #   points <int>, taster_name <fct>, rating_category <chr>, norm_points <dbl>
```

## Data Sanitation
To ensure the integrity of our data, we perform some hard checks that could have been missed during our data pre-processing.
\
\
Vintage seems to have year 7200, so we filtered all data up to 2019

```r
wines <- wines %>%
  filter(vintage<2019)
```

# Data Exploration
Before, conducting any detailed analysis of our dataset, we looked at a quick summary of the dataset

```r
summary(wines)
```

```
##                                                                             title       
##  Château Lestage Simon 2012  Haut-Médoc                                        :     4  
##  Château Maine-Gazin 1997  Bordeaux                                            :     4  
##  Concannon 2009 Selected Vineyards, Central Coast Pinot Noir (Livermore Valley):     4  
##  Domaine Vacheron 2015  Sancerre                                               :     4  
##  Vignerons des Pierres Dorées 2015 Salamandre d'Or  (Coteaux Bourguignons)     :     4  
##  Adega Cooperativa de Borba 2009 Senses Syrah (Alentejano)                     :     3  
##  (Other)                                                                       :117855  
##     alcohol               category        vintage           designation   
##  Min.   :   2.20   Dessert    : 1648   Min.   :1150               :35285  
##  1st Qu.:  13.00   Fortified  :   60   1st Qu.:2009   Reserve     : 1924  
##  Median :  13.53   Port/Sherry:  386   Median :2011   Estate      : 1236  
##  Mean   :  13.84   Red        :72354   Mean   :2010   Reserva     : 1214  
##  3rd Qu.:  14.40   Rose       : 4203   3rd Qu.:2013   Riserva     :  669  
##  Max.   :8333.00   Sparkling  : 2273   Max.   :2017   Estate Grown:  584  
##  NA's   :9060      White      :36954                  (Other)     :76966  
##      country                province                      region     
##  US      :50228   California    :33418                       :19360  
##  France  :19164   Washington    : 8106   Napa Valley         : 4234  
##  Italy   :17497   Bordeaux      : 5665   Columbia Valley (WA): 3855  
##  Spain   : 5890   Tuscany       : 5647   Russian River Valley: 2896  
##  Portugal: 4905   Oregon        : 4824   California          : 2200  
##  Chile   : 4235   Northern Spain: 3712   Paso Robles         : 2193  
##  (Other) :15959   (Other)       :56506   (Other)             :83140  
##              subregion                         variety     
##                   :70775   Pinot Noir              :12071  
##  Central Coast    :10277   Chardonnay              :10813  
##  Sonoma           : 8527   Cabernet Sauvignon      : 8933  
##  Columbia Valley  : 7617   Red Blend               : 8233  
##  Napa             : 6450   Bordeaux-style Red Blend: 6564  
##  Willamette Valley: 3286   Riesling                : 4893  
##  (Other)          :10946   (Other)                 :66371  
##                    winery           price             points      
##  DFJ Vinhos           :   208   Min.   :   4.00   Min.   : 80.00  
##  Williams Selyem      :   207   1st Qu.:  17.00   1st Qu.: 86.00  
##  Testarossa           :   205   Median :  25.00   Median : 88.00  
##  Louis Latour         :   193   Mean   :  35.48   Mean   : 88.47  
##  Chateau Ste. Michelle:   192   3rd Qu.:  42.00   3rd Qu.: 91.00  
##  Georges Duboeuf      :   192   Max.   :3300.00   Max.   :100.00  
##  (Other)              :116681   NA's   :7974                      
##             taster_name    rating_category     norm_points      
##                   :23945   Length:117878      Min.   :-4.49580  
##  Roger Voss       :22265   Class :character   1st Qu.:-0.72711  
##  Michael Schachner:13867   Mode  :character   Median : 0.03980  
##  Kerin O’Keefe    : 9747                      Mean   : 0.01183  
##  Virginie Boone   : 8926                      3rd Qu.: 0.70027  
##  Paul Gregutt     : 8747                      Max.   : 4.46378  
##  (Other)          :30381
```

## Univariate Exploration
To better understand the distribution of our data, we did some simple univariate visualization based on specific fields. Additionally, before doing a multivariate analysis and answering our research questions, we first want to ensure our dataset is robust and an accurate representation of the real world.

### Alcohol Amount
The visualization below depicts the distribution of our dataset based on alcohol percentage, `alcohol`. To better understand and visualize the data, we categorized the graph based on `rating_category`. Notice, a majority of wines have an alcohol amount between 12%-15%, and according to [Real Simple](https://www.realsimple.com/holidays-entertaining/entertaining/food-drink/alcohol-content-wine), wine alcoholic content averages between 11%-13%. This leads us to believe our data is an accurate representation of the real world.

```r
wines %>% 
  group_by(alcohol) %>% 
  ggplot() +
  geom_histogram(
    mapping = aes(
      x = alcohol, 
      fill = rating_category),
    na.rm = TRUE,
    bins = 50) +
  scale_x_continuous(
    breaks = seq(0,25,1), 
    limits = c(4,22)) +
  labs(
    title = "Distribution of Alcohol Percentage",
    x = "Alcohol Percentage",
    y = "Count",
    fill = "Rating Category"
  )
```

```
## Warning: Grouping rowwise data frame strips rowwise nature
```

![](report_files/figure-html/unnamed-chunk-11-1.png)<!-- -->

### Vintage
Next, we wanted to see what vintage most of the wines in the dataset were. Again to better understand and visualize the data, we categorized the graph based on `rating_category`. Notice that there is roughly an equal percentage of each rating category per vintage.

(Note: Data points before 1990 have been omitted for clarity in visualization)

```r
wines %>%
  ggplot() +
  geom_bar(
    mapping = aes(
      x=vintage, 
      fill = rating_category),
    na.rm = TRUE) +
  scale_x_continuous(
    breaks = seq(1990,2019,5), 
    limits = c(1990,2019)) +
  labs(
    title = "Distribution of Vintage",
    x = "Vintage", 
    y = "Count",
    fill = "Rating Category")
```

![](report_files/figure-html/unnamed-chunk-12-1.png)<!-- -->

### Winery
To better understand the number wines per winery, we did a visualization that counts the number of wines per winery showing only Top 10 wineries to give you an idea of what winery has the most selection of wines. Notice, each of the top 10 producers of wine have over 100 different wine labels.

```r
wines %>%
  group_by(winery) %>%
  summarise(count = n()) %>%
  arrange(desc(count)) %>%
  slice(1:10) %>%
  ggplot() +
  geom_col(
    mapping = aes(
      x= reorder(winery, count),
      y = count,
      fill = winery)) +
  labs(
    title = "Distribution of Winery (Top 10)",
    x = "Winery", 
    y = "Count") +
  theme(legend.position = "none") +
  coord_flip()
```

```
## Warning: Grouping rowwise data frame strips rowwise nature
```

![](report_files/figure-html/unnamed-chunk-13-1.png)<!-- -->

### Province
To better understand the number of wines per province, we did a visualization that counts the number of wines per province, showing only the top 10 provinces with the most wines. This can give the reader an idea where their wine will most likely be made with California standing out as a clear leader.

```r
wines %>% 
  group_by(province) %>% 
  summarize(count = n()) %>% 
  arrange(desc(count)) %>% 
  slice(1:10) %>% 
  ggplot()+
  geom_col(
    mapping = aes(
      x = reorder(province, count), 
      y = count,
      fill = province)) +
  labs(
    title = "Distribution of Province (Top 10)",
    x = "Province", 
    y = "Count") +
  theme(legend.position = "none") +
  coord_flip()
```

```
## Warning: Grouping rowwise data frame strips rowwise nature
```

![](report_files/figure-html/unnamed-chunk-14-1.png)<!-- -->
### Wine Category
Next, we wanted to visualize the distribution of different wine categories in our dataset. To better understand and visualize the data, we categorized the graph based on `rating_category`. Notice, a majority of the wines are red or white wines.


```r
wines %>% 
  ggplot()+
  geom_bar(
    mapping = aes(
      x = category,
      fill = rating_category)) +
  labs(
    title = "Distribution of Wine Category",
    x = "Wine Category", 
    y = "Count",
    fill = "Rating Category") +
  coord_flip()
```

![](report_files/figure-html/unnamed-chunk-15-1.png)<!-- -->

### Price
Next, we wanted to visualize the distribution of price in our dataset. To better understand and visualize the data, we categorized the graph based on `rating_category`. Notice, a majority of wines are \$50 and below, with the most common being between \$12 - \$25. Again, this accurately represents the real world. As stated by [Vivino](https://www.vivino.com/wine-news/how-much-does-a-good-bottle-of-wine-cost), the average price for a good bottle of red/white wine is ~\$15 and ~\$28 for a very good bottle. (CAUTION: The Vivino prices denoted were simply an average for red/white wines average costs. This was done to generalize the information to make a simple comparison. Also, this limited to red/white wine and does not accurately include other types, which are included within our dataset)

(Note: Data points above $400 have been omitted for clarity in visualization)

```r
wines %>% 
  filter(price < 400) %>% 
  ggplot() +
  geom_histogram(
    mapping = aes(
      x=price, 
      fill = rating_category),
    binwidth = 15) +
  labs(
    title = "Distribution of Price",
    x = "Price", 
    y = "Count",
    fill = "Rating Category")
```

![](report_files/figure-html/unnamed-chunk-16-1.png)<!-- -->

###  Points 
Next, we wanted to visualize the distribution of points in our dataset. Notice, here that a majority of wines receive a score between 87 and 90. Which is accurate to the information provided on [Wine Searcher]("https://www.wine-searcher.com/critics-17-wine+enthusiast"), which states 50% of the scores fall between 86-90 point from Wine Enthusiast ratings.

(Note: We our dataset was reterived from the Wine Enthusiast website)

```r
wines %>%
  ggplot() +
  geom_histogram(
    mapping = aes(x=points),
    bins = 20)+
  labs(
    title = "Distribution of Points",
    x = "Points", 
    y = "Count")
```

![](report_files/figure-html/unnamed-chunk-17-1.png)<!-- -->

## Multivariate Exploration
Now that we have a better understanding of our data, and we know it is an accurate representation of the real world, we can perform a more detailed analysis using multiple variables.

### Points by Taster
To understand the point distribution by tasters, we did a multivariate visualization that correlates taster names based on the average wine points as identified by the x-intercept. This gives the reader an idea of how some reviewers correlate to the overall average.

(Note: The “blank” represents unknown reviewers. We assumed the reviewers not named have not rated a significant amount of wines and can be grouped into a singular reviewer)

```r
wines %>%
  ggplot() +
  geom_boxplot(
    mapping = aes(
      x=taster_name,
      y=points, 
      color = taster_name)) +
  geom_hline(yintercept = mean(wines$points)) +
  theme(legend.position = "none")+
  labs(
    title = "Points by Taster",
    x="Taster Name",
    y="Points"
  )+
  coord_flip()
```

![](report_files/figure-html/unnamed-chunk-18-1.png)<!-- -->


### Price by Points
To understand the price distribution by points, we did a multivariate visualization that creates a scatter plot of the wines based on points and price. Then, we added a smooth transformation to identify trends. Notice, the data is stacked, and the scores range from 80-100

```r
wines %>% 
  ggplot() +
  geom_point(
    mapping = aes(
      x = points, 
      y = price, 
      color = category),
    na.rm = TRUE,
    alpha = 0.2) +
  labs(
    title = "Price by Points", 
    x = "Points",
    y = "Price",
    color = "Wine Category") +
  geom_smooth(
    mapping = aes(
      x = points, 
      y = price),
    na.rm = TRUE)
```

```
## `geom_smooth()` using method = 'gam' and formula 'y ~ s(x, bs = "cs")'
```

![](report_files/figure-html/unnamed-chunk-19-1.png)<!-- -->

Since there are multiple outliers, and the visualization is clustered. By performing a log on all the prices, we can reduce the skewness of the visualization. Notice, as the quality of wine increases, price increases exponentially.

```r
wines %>% 
  ggplot() +
  geom_point(
    mapping = aes(
      x = points, 
      y = log(price), 
      color = category),
    na.rm = TRUE,
    alpha = 0.2) +
  labs(
    title = "log(Price) by Points", 
    x = "Points",
    y = "log(Price)",
    color = "Wine Category") +
  geom_smooth(
    mapping = aes(
      x = points, 
      y = log(price)),
    na.rm = TRUE)
```

```
## `geom_smooth()` using method = 'gam' and formula 'y ~ s(x, bs = "cs")'
```

![](report_files/figure-html/unnamed-chunk-20-1.png)<!-- -->

#### Group by Wine Category
Next, our group wanted to do a more granular analysis by looking at how the price varies by points grouped by the wine category. Notice, all the prices go up as points go up, but the growth rates are different per wine category.

```r
wines %>% 
  ggplot() +
  geom_point(
    mapping = aes(
      x = points, 
      y = log(price), 
      color = category),
    alpha =0.2,
    na.rm = TRUE) +
  geom_smooth(
    mapping = aes(
      x = points, 
      y = log(price)),
    na.rm = TRUE) +
  facet_wrap(~category) +
  labs(
    title = "log(Price) by Points", 
    x = "Points",
    y = "log(Price)")+
  theme_minimal()+
  theme(legend.position = "none" )
```

```
## `geom_smooth()` using method = 'gam' and formula 'y ~ s(x, bs = "cs")'
```

![](report_files/figure-html/unnamed-chunk-21-1.png)<!-- -->


# Data Analysis
Now that we fully understand the dataset we are working with, we plan to answer some research questions proposed by the team.

## What is the best wine?
An easy way to determine the best wine is by simply finding the top 10 wines by rating.

```r
wines %>%
  arrange(desc(points)) %>%
  slice(1:10) %>%
  select(title,price, points,rating_category, norm_points)
```

```
## Source: local data frame [10 x 5]
## Groups: <by row>
## 
## # A tibble: 10 x 5
##    title                                price points rating_category norm_points
##    <fct>                                <int>  <int> <chr>                 <dbl>
##  1 Avignonesi 1995 Occhio di Pernice  …   210    100 Classic                3.71
##  2 Krug 2002 Brut  (Champagne)            259    100 Classic                3.71
##  3 Tenuta dell'Ornellaia 2007 Masseto …   460    100 Classic                3.71
##  4 Casa Ferreirinha 2008 Barca-Velha R…   450    100 Classic                3.71
##  5 Biondi Santi 2010 Riserva  (Brunell…   550    100 Classic                4.46
##  6 Cardinale 2006 Cabernet Sauvignon (…   200    100 Classic                3.71
##  7 Château Léoville Barton 2010  Saint…   150    100 Classic                3.71
##  8 Louis Roederer 2008 Cristal Vintage…   250    100 Classic                3.71
##  9 Salon 2006 Le Mesnil Blanc de Blanc…   617    100 Classic                3.71
## 10 Château Lafite Rothschild 2010  Pau…  1500    100 Classic                3.71
```

However, this does not account for the taster's bias. Instead, our group normalized the points based on each taster based on the number of standard deviations a wine is from the raters average. For example, Taster A could give a wine 100 but has an average rating score of 95 with a standard deviation of 5. Whereas, Taster B could offer a wine 91 and have an average score of 87 with a standard deviation of 2. Although the wine tasted by Taster A got a perfect 100 score, Taster B’s wine was much “better” wine since it was two standard deviations from the tasters average compared to 1 standard deviation of the other wine.

Looking at the `norm_points` these are the top 10 best wines

```r
wines %>%
  arrange(desc(norm_points)) %>%
  slice(1:10)%>%
  select(title,price, points,rating_category, norm_points)
```

```
## Source: local data frame [10 x 5]
## Groups: <by row>
## 
## # A tibble: 10 x 5
##    title                                price points rating_category norm_points
##    <fct>                                <int>  <int> <chr>                 <dbl>
##  1 Biondi Santi 2010 Riserva  (Brunell…   550    100 Classic                4.46
##  2 Tenuta San Guido 2012 Sassicaia  (B…   235     99 Classic                4.06
##  3 Mascarello Giuseppe e Figlio 2008 C…   595     99 Classic                4.06
##  4 Mascarello Giuseppe e Figlio 2010 M…   175     99 Classic                4.06
##  5 Il Marroneto 2012 Madonna delle Gra…   200     99 Classic                4.06
##  6 Charles Smith 2006 Royal City Syrah…    80    100 Classic                3.87
##  7 Cayuse 2008 Bionic Frog Syrah (Wall…    80    100 Classic                3.87
##  8 Oremus 2005 Eszencia  (Tokaji)         320     96 Superb                 3.79
##  9 Royal Tokaji 2013 5 Puttonyos Aszú …    54     96 Superb                 3.79
## 10 Dobogó 2007 Aszú 6 Puttonyos  (Toka…   125     96 Superb                 3.79
```

## What is the best value wine?
A simple value metric we can use to determine best value is `points/price`.

```r
wines %>%
  arrange(desc(points/price)) %>%
  slice(1:10)%>%
  select(title,price, points,rating_category, norm_points)
```

```
## Source: local data frame [10 x 5]
## Groups: <by row>
## 
## # A tibble: 10 x 5
##    title                                price points rating_category norm_points
##    <fct>                                <int>  <int> <chr>                 <dbl>
##  1 Cramele Recas 2011 UnWineD Pinot Gr…     4     86 Good                -0.941 
##  2 Felix Solis 2013 Flirty Bird Syrah …     4     85 Good                -0.621 
##  3 Dancing Coyote 2015 White (Clarksbu…     4     85 Good                -1.33  
##  4 Broke Ass 2009 Red Malbec-Syrah (Me…     4     84 Good                -0.951 
##  5 Terrenal 2010 Cabernet Sauvignon (Y…     4     84 Good                -0.951 
##  6 Terrenal 2010 Estate Bottled Tempra…     4     84 Good                -0.951 
##  7 Felix Solis 2012 Flirty Bird White …     4     82 Acceptable          -1.61  
##  8 In Situ 2008 Reserva Sauvignon Blan…     5     87 Very Good            0.0398
##  9 In Situ 2008 Reserva Sauvignon Blan…     5     87 Very Good            0.0398
## 10 Earth's Harvest 2013 Merlot (Califo…     5     86 Good                -0.959
```

However, again this metric is not normalized. Instead, `norm_points/price` would yield more robust results.

```r
wines %>%
  arrange(desc(norm_points/price)) %>%
  slice(1:10) %>%
  select(title,price, points,rating_category, norm_points)
```

```
## Source: local data frame [10 x 5]
## Groups: <by row>
## 
## # A tibble: 10 x 5
##    title                                price points rating_category norm_points
##    <fct>                                <int>  <int> <chr>                 <dbl>
##  1 Lyrarakis 2014 Kotsifali (Crete)        13     92 Excellent              2.27
##  2 Osborne NV Pedro Ximenez 1827 Sweet…    14     94 Superb                 2.35
##  3 Dionysos 2014 Moschofilero (Mantini…    16     93 Excellent              2.69
##  4 Chateau Grand Traverse 2013 Dry Rie…    13     90 Excellent              2.14
##  5 Hatzimichalis 2015 Assyrtiko (Atala…    12     91 Excellent              1.85
##  6 Royal Tokaji 2016 Late Harvest  (To…    21     94 Superb                 2.81
##  7 Quinta dos Murças 2011 Assobio Red …    13     94 Superb                 1.73
##  8 Boutari 2016 Moschofilero (Mantinia)    17     92 Excellent              2.27
##  9 Lovingston 2012 Josie's Knoll Merlo…    20     91 Excellent              2.65
## 10 Rulo 2007 Syrah (Columbia Valley (W…    20     96 Superb                 2.46
```

## Which province has the best wine?
To determine the best province for wine by points, we averaged the points of all wines per province with a sample size greater than 30 and returned the top 10 with standard error. Notice how the standard error is low, meaning the spread of our data is also small, and the average is very accurate.


```r
wines %>% 
  group_by(province) %>%
  summarise(
    avg_points_prov = mean(points), 
    count = n(), 
    std_err_points_prov = sd(points)/sqrt(count)) %>%
  filter(count>30) %>%
  arrange(desc(avg_points_prov)) %>%
  slice(1:10) %>%
  ggplot() +
  geom_col(
    mapping = aes(
      x = reorder(province,avg_points_prov), 
      y = avg_points_prov,
      fill = province)) +
   geom_errorbar(
    mapping = aes(
      x = province,
      y = avg_points_prov,
      ymin = avg_points_prov - std_err_points_prov, 
      ymax = avg_points_prov + std_err_points_prov
      ),
    width = 0.2)+
  scale_y_continuous(
    limits=c(85,95), 
    oob = rescale_none)+
  labs(
      x = 'Province', 
      y = "Average Points", 
      title = "Average Points By Province (Top 10)") +
  theme(legend.position = "none")+
  coord_flip()
```

```
## Warning: Grouping rowwise data frame strips rowwise nature
```

![](report_files/figure-html/unnamed-chunk-26-1.png)<!-- -->

## Which wine variety is the best?
To determine the best variety of wine, we use the average points of all wines per variety with a sample size greater than 30. The graph below shows the top 10 varieties with their respective standard error.


```r
wines %>% 
  group_by(variety) %>%
  summarise(
    avg_points_variety = mean(points), 
    count = n(), 
    std_err_points_variety = sd(points)/sqrt(count)) %>%
  filter(count>30) %>%
  arrange(desc(avg_points_variety)) %>%
  slice(1:10) %>%
  ggplot() +
  geom_col(
    mapping = aes(
      x = reorder(variety,avg_points_variety), 
      y = avg_points_variety,
      fill = variety)) +
   geom_errorbar(
    mapping = aes(
      x = variety,
      y = avg_points_variety,
      ymin = avg_points_variety - std_err_points_variety, 
      ymax = avg_points_variety + std_err_points_variety
      ),
    width = 0.2)+
  scale_y_continuous(
    limits=c(85,95), 
    oob = rescale_none)+
  labs(
      x = 'Variety', 
      y = "Average Points", 
      title = "Average Points By Variety (Top 10)") +
  theme(legend.position = "none")+
  coord_flip()
```

```
## Warning: Grouping rowwise data frame strips rowwise nature
```

![](report_files/figure-html/unnamed-chunk-27-1.png)<!-- -->

## Jess from New Girl’s favorite wine?
Sounds like a silly question, but take a closer look and you'll find an interesting question within it: "Can we determine the best value wine based on how much people are willing to pay?"  WE SURE CAN!


```r
# If you want to get user input
#user_price <- readline(prompt = "How much are you willing to spend on a bottle?")
#user_price <- as.integer(user_price)
user_price<-11

wines %>% 
  filter(price <= user_price) %>%
  arrange(desc(norm_points/price)) %>%
  slice(1:10) %>%
  select(title, price, points,rating_category, norm_points)
```

```
## Source: local data frame [10 x 5]
## Groups: <by row>
## 
## # A tibble: 10 x 5
##    title                                price points rating_category norm_points
##    <fct>                                <int>  <int> <chr>                 <dbl>
##  1 Mano A Mano 2011 Tempranillo (Vino …     9     90 Excellent             1.03 
##  2 Herdade dos Machados 2012 Toutalga …     7     91 Excellent             0.748
##  3 Dolce Stefania 2007 Bonarda (Mendoz…    10     90 Excellent             1.03 
##  4 Viña Cumbrero 2010 Crianza  (Rioja)     10     90 Excellent             1.03 
##  5 Borsao 2008 Monte Oton Garnacha (Ca…     7     89 Very Good             0.700
##  6 Aveleda 2011 Follies Fonte Nossa Se…    11     92 Excellent             1.08 
##  7 Pedra Cancela 2010 Seleção do Enólo…    11     92 Excellent             1.08 
##  8 Pacific Rim 2009 Riesling (Columbia…    11     92 Excellent             1.04 
##  9 Trivento 2009 Reserve Cabernet Sauv…    11     90 Excellent             1.03 
## 10 Chakana 2006 Malbec (Mendoza)           11     90 Excellent             1.03
```

Now back to the orignal question with Jess
<br>
<div style="width:100%;height:0;padding-bottom:61%;position:relative;"><iframe src="https://giphy.com/embed/3osxY3Ju6p2jJbBo88" width="100%" height="100%" style="position:absolute" frameBorder="0" class="giphy-embed" allowFullScreen></iframe></div>


```r
wines %>% 
  filter(price < 11) %>%
  filter(category == "Sparkling") %>%
  filter(grepl("pink", title, ignore.case = T) == T) %>%
  select(title,price, points,rating_category, norm_points)
```

```
## Source: local data frame [1 x 5]
## Groups: <by row>
## 
## # A tibble: 1 x 5
##   title                                 price points rating_category norm_points
##   <fct>                                 <int>  <int> <chr>                 <dbl>
## 1 Yellow Tail 2015 Pink Bubbles Sparkl…    10     84 Good                  -1.58
```
As you can see, "Yellow Tail 2015 Pink Bubbles Sparkling (South Australia)" is Jess's type of wine!

# Conclusion
After all this exploration, we were able to walk away with some insights. We learned that standardizing tasters gives a more accurate overview of what the best wines really are, that point values affect price, and that you're most likely drinking wine from California. In the end, though, this exploration of wine showed us more than just how to design the perfect flight; we learned the importance of data preprocessing, the power of mindful graphics, how to make every ggplot easy to understand for the reader using color, and the practicality of the pipe tool. We were able to apply data manipulation and exploration skills such as filtering, mutating, arranging, greping, and slicing data. Beyond R skills, we learned how to adapt to being a remote team, which was significantly helped with the utilization of GitHub. We feel this report gives a well-rounded display of the tools we were taught throughout the semester, and we were excited to build from that knowledge and integrate other tools as well.

# Future Works
There is undoubtedly more exploration to be done within this dataset. 
Integrating more Twitter data with packages such as `rtweet`, we could design the "perfect stereotype" of a wine connoisseur by gathering keywords from tweets. Delving into the text mining portion of data science, we could find popular words to describe a wine from each review and design artificial reviews. We could take the data we found, build statistical learning models such as a random forest to predict prices of wines based on the descriptions; this would be a useful model for new, budding (pun intended) wineries to determine the price. Additionally, this data is only a fraction of the data found on the Wine Enthusiast website. Overall, creativity is the only limitation on what other problems we could solve with this dataset.

The data used is just a fraction of the data found on the Wine Enthusiast website, the team has created a script to collect additional information on the site, which can be found [here](https://github.com/C4rbyn3m4n/wine_reviews_data_analysis/tree/master/data/scripts) for future expansion.

# Datasets Cited
Special thanks to [Zack Thoutt](https://www.kaggle.com/zynicide) for providing us with [dataset_1](https://www.kaggle.com/zynicide/wine-reviews) and [Sanyam Kapoor](https://github.com/activatedgeek) for providing us with  [dataset_2](https://github.com/activatedgeek/winemag-dataset).
 
The data we used is available at: [https://github.com/C4rbyn3m4n/wine_reviews_data_analysis/tree/master/data](https://github.com/C4rbyn3m4n/wine_reviews_data_analysis/tree/master/data)
