# Sample Datasets

A collection of datasets from multiple sources to be used for demonstrations in data science courses. 

# Data Dictionary and/or Description
(last updated: 2020/10/08. Contribution by Gabriel Mantini, @gmantini)

A data dictionary (or data description) is provided for some of the datasets in this repo. Click on the dataset of interest in the list below to learn more about the available attributes.

<details>
  <summary> Click to see data dictionary for: 

  [`fuel.csv`](https://github.com/reisanar/datasets/blob/master/fuel.csv)
  </summary>  See this website: https://www.fueleconomy.gov/feg/ws/

</details>



<details>
  <summary> Click to see data dictionary for: 

  [`BostonHousing.csv`](https://github.com/reisanar/datasets/blob/master/BostonHousing.csv)
  </summary> This dataset contains information collected by the US Census Service concerning housing in the area of Boston Massachusetts. It was obtained from the StatLib archive (http://lib.stat.cmu.edu/datasets/boston). The dataset has 506 cases.
Source: The data was originally published by Harrison, D. and Rubinfeld, D.L. `Hedonic prices and the demand for clean air`, J. Environ. Economics & Management, vol.5, 81-102, 1978.
There are 14 attributes in each case of the dataset. They are:

  
  Variables |  Description
------------|----------------------------------------------------------------
`CRIM`      | Crime rate
`ZN`        | Percentage of residential land zoned for lots over 25,000 ft2
`INDUS`     | Percentage of land occupied by non-retail business
`CHAS`      | Does tract bound Charles River (`= 1` if tract bounds river, `= 0` otherwise)
`NOX`       | Nitric oxide concentration (parts per 10 million)
`RM`        | Average number of rooms per dwelling
`AGE`       | Percentage of owner-occupied units built prior to 1940
`DIS`       | Weighted distances to five Boston employment centers
`RAD`       | Index of accessibility to radial highways
`TAX`       | Full-value property tax rate per $10,000
`PTRATIO`   | Pupil-to-teacher ratio by town
`LSTAT`     | Percentage of lower status of the population
`MEDV`      | Median value of owner-occupied homes in $1000s
`CAT.MEDV`  | Is median value of owner-occupied homes in tract above $30,000 (`CAT.MEDV = 1`) or not (`CAT.MEDV = 0`)

</details>

<details>
  <summary> Click to see data dictionary for: 

  [`Cereals`](https://github.com/reisanar/datasets/blob/master/Cereals.csv)
  </summary> Source: DATA ANALYSIS FOR STUDENT LEARNING (DASL)
  
  Variables |  Description
------------|----------------------------------------------------------------
`Name`      | Name of cereal
`mfr`        | Manufacturer of cereal where A = American Home Food Products; G = General Mills; K = Kelloggs; N = Nabisco; P = Post; Q = Quaker Oats; R = Ralston Purina
`type`     | cold or hot
`calories`      | calories per serving
`protein`       | grams of protein
`fat`        | grams of fat
`sodium`       | milligrams of sodium
`fiber`       | grams of dietary fiber
`carbo`       | grams of complex carbohydrates
`sugars`       | grams of sugars
`potass`   | milligrams of potassium
`vitamins`     | vitamins and minerals - 0, 25, or 100, indicating the typical percentage of FDA recommended
`shelf`      | display shelf (1, 2, or 3, counting from the floor)
`weight`  | weight in ounces of one serving
`cups`  | number of cups in one serving
`rating`  | a rating of the cereals calculated by Consumer Reports


</details>

<details>
  <summary> Click to see data dictionary for: 

  [`EastWestAirlinesCluster`](https://github.com/reisanar/datasets/blob/master/EastWestAirlinesCluster.csv)
  </summary> East-West Airlines is trying to learn more about its customers.  Key issues are their flying patterns, earning and use of frequent flyer rewards, and use of the airline credit card.  The task is to identify customer segments via clustering.   			 
Source: Based upon real business data; company names have been changed.   
  
  Variables |  Description 
------------|----------------------------------------------------------------
`ID#`      | Unique ID
`Balance`        | Number of miles eligible for award travel
`Qual_miles`     | Number of miles counted as qualifying for Topflight status
`cc1_miles`      | Number of miles earned with freq. flyer credit card in the past 12 months:
`cc2_miles`       | Number of miles earned with Rewards credit card in the past 12 months:
`cc3_miles`        | Number of miles earned with Small Business credit card in the past 12 months:
`note: miles bins`       | 1 = under 5,000. 2 = 5,000 - 10,000. 3 = 10,001 - 25,000. 4 = 25,001 - 50,000. 5 = over 50,000
`Bonus_miles`       | Number of miles earned from non-flight bonus transactions in the past 12 months
`Bonus_trans`       | Number of non-flight bonus transactions in the past 12 months
`Flight_miles_12mo`       | Number of flight miles in the past 12 months
`Flight_trans_12`   | Number of flight transactions in the past 12 months
`Days_since_enroll`     |  Number of days since Enroll_date
`Award?`      | Dummy variable for Last_award (1=not null, 0=null)


</details>

<details>
  <summary> Click to see data dictionary for: 

  [`ToyotaCorolla`](https://github.com/reisanar/datasets/blob/master/ToyotaCorolla.csv)
  </summary> 
  
  Variables |  Description
------------|----------------------------------------------------------------
`Id`        | Record_ID
`Model`     | Model Description
`Price`      | Offer Price in EUROs
`Age_08_04`       | Age in months as in August 2004
`Mfg_Month`        | Manufacturing month (1-12)
`Mfg_Year`       | Manufacturing Year
`KM`       | Accumulated Kilometers on odometer
`Fuel_Type`       | Fuel Type (Petrol, Diesel, CNG)
`HP`       | Horse Power
`Met_Color`       | Metallic Color?  (Yes=1, No=0)
`Color`       | Color (Blue, Red, Grey, Silver, Black, etc.)
`Automatic`   | Automatic ( (Yes=1, No=0)
`CC`     | Cylinder Volume in cubic centimeters
`Doors`      | Number of doors
`Cylinders`  | Number of cylinders
`Gears`  | Number of gear positions
`Quarterly_Tax`  | Quarterly road tax in EUROs
`Weight`     | Weight in Kilograms
`Mfr_Guarantee`      | Within Manufacturer's Guarantee period  (Yes=1, No=0)
`BOVAG_Guarantee`       | BOVAG (Dutch dealer network) Guarantee  (Yes=1, No=0)
`Guarantee_Period`        | Guarantee period in months
`ABS`       | Anti-Lock Brake System (Yes=1, No=0)
`Airbag_1`       | Driver_Airbag  (Yes=1, No=0)
`Airbag_2`       | Passenger Airbag  (Yes=1, No=0)
`Airco`       | Airconditioning  (Yes=1, No=0)
`Automatic_airco`   | Automatic Airconditioning  (Yes=1, No=0)
`Boardcomputer`     | Boardcomputer  (Yes=1, No=0)
`CD_Player`      | CD Player  (Yes=1, No=0)
`Central_Lock`  | Central Lock  (Yes=1, No=0)
`Powered_Windows`  | Powered Windows  (Yes=1, No=0)
`Power_Steering`  | Power Steering  (Yes=1, No=0)
`Radio`        | Radio  (Yes=1, No=0)
`Mistlamps`       | Mistlamps  (Yes=1, No=0)
`Sport_Model`       | Sport Model  (Yes=1, No=0)
`Backseat_Divider`       | Backseat Divider  (Yes=1, No=0)
`Metallic_Rim`       | Metallic Rim  (Yes=1, No=0)
`Radio_cassette`   | Radio Cassette  (Yes=1, No=0)
`Parking_Assistant`     | Parking assistance system  (Yes=1, No=0)
`Tow_Bar`      | Tow Bar  (Yes=1, No=0)


</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`Auto`](https://github.com/reisanar/datasets/blob/master/Auto.csv)
  </summary> Gas mileage, horsepower, and other information for 392 vehicles.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`mpg`         | miles per gallon
`cylinders`   | Number of cylinders between 4 and 8
`displacement`| Engine displacement (cu. inches)
`horsepower`  | Engine horsepower
`weight`      | Vehicle weight (lbs.)
`acceleration`| Time to accelerate from 0 to 60 mph (sec.)
`year`        | Model year (modulo 100)
`origin`      | Origin of car (1. American, 2. European, 3. Japanese)
`name`        | Vehicle name

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`allbacks`](https://github.com/reisanar/datasets/blob/master/allbacks.csv)
  </summary> The allbacks data frame gives measurements on the volume and weight of 15 books, some of which are softback (pb) and some which are hardback (hb). Area of the hardback covers is also included.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`volume`      | book volumes in cubic centimeters
`area`        | hard board cover areas in square centimeters
`weight`| book weights in grams
`cover`  | a factor with levels hb hardback, pb paperback

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`UniversalBank`](https://github.com/reisanar/datasets/blob/master/UniversalBank.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`ID`      | Customer ID
`Age`        | Customer's age in completed years
`Experience` | #years of professional experience
`Income`  | Annual income of the customer ($000)
`ZIPCode`      | Home Address ZIP code
`Family`        | Family size of the customer
`CCAvg`| Avg. spending on credit cards per month ($000)
`Education`  | Education Level. 1: Undergrad; 2: Graduate; 3: Advanced/Professional
`Mortgage`      | Value of house mortgage if any. ($000)
`Personal Loan`        | Did this customer accept the personal loan offered in the last campaign?
`Securities Account` | Does the customer have a securities account with the bank?
`CD Account`  | Does the customer have a certificate of deposit (CD) account with the bank?
`Online`      | Does the customer use internet banking facilities?
`CreditCard`        | Does the customer use a credit card issued by UniversalBank?

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`Utilities`](https://github.com/reisanar/datasets/blob/master/Utilities.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Company`        | Company name
`Fixed_charge` | Fixed-charge coverage ratio (income/debt)
`RoR    `  | Percent rate of return on capital
`Cost    `      | Cost per KW capacity in place
`Load_factor    `        | Annual load factor
`Demand_growth    `| Percent demand growth
`Sales    `  | Sales (KWH use per year)
`Nuclear    `      | Nuclear    			Percent nuclear
`Fuel_Cost`        | Fuel_Cost			Total fuel costs (cents per KWH)

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`West Roxbury`](https://github.com/reisanar/datasets/blob/master/WestRoxbury.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`TOTAL VALUE    `      | Total assessed value for property, in thousands of USD
`TAX   `        | Tax bill amount based on total assessed value multiplied by the tax rate
`LOT SQFT          ` | Total lot size of parcel in square feet
`YR BUILT   `  | Year property was built
`GROSS AREA    `      | Gross floor area
`LIVING AREA         `        | Total living area for residential properties (ft2)
`FLOORS`| Number of floors
`ROOMS`  | Total number of rooms
`BEDROOMS    `      | Total number of bedrooms
`FULL BATH   `        | Total number of full baths
`HALF BATH         ` | Total number of half baths
`KITCHEN        `  | Total number of kitchens
`FIREPLACE   `      | Total number of fireplaces
`REMODEL        `        | When house was remodeled (Recent/Old/None)

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`WorldCupMatches`](https://github.com/reisanar/datasets/blob/master/WorldCupMatches.csv)
  </summary> World Cup Matches dataset shows all the results from the matches contested as part of the different editions of the tournament. You can also complement this dataset with the information in `worldcup.csv` that includes statistics for every player that participated in FIFA 2010 worldcup.

 Variables    |  Description
------------  |----------------------------------------------------------------
`Year`      | The year in which the match was played
`Datetime`        | The Date on which the match was played along with a 24 hour format time
`Stage` | The stage at which the match was played
`Stadium`  | Stadium name where the match was held
`City`      | The city name, where the match was played
`Home Team Name`        | Home team country name
`Home Team Goals`| Total goals scored by the home team by the end of the match
`Away Team Goals`  | Total goals scored by the away team by the end of the match
`Away Team Name`      | Away team country name
`Win conditions`        | Special win condition (if any)
`Attendance` | Total crowd present at the satdium
`Half-time Home Goals`  | Goals scored by the home team until half time
`Half-time Away Goals`      | Goals scored by the away team until half time
`Referee`        | Name of the first refree
`Assistant 1` | Name of the first assistant referee (linesman)
`Assistant 2`  | Name of the second assistant referee (linesman)
`RoundID`      | Unique ID of the Round
`MatchID`        | Unique ID of the match
`Home Team Initials` | Home team country's three letter initials
`Away Team Initials`  | Away team country's three letter initials

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`NBAchampionsdata`](https://github.com/reisanar/datasets/blob/master/NBAchampionsdata.csv) and [`NBArunnerupsdata`](https://github.com/reisanar/datasets/blob/master/NBArunnerupsdata.csv)
  </summary> Game-by-game team totals for the championship team and runner-up team from every finals game between 1980 and 2018. The 1980 NBA Finals was the first Finals series since the NBA added the three point line.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Year`      | Year of competition
`Team`        | Team name
`Game` | Game of Best-of-7 series
`Win`  | Boolean of win or loss, with win represented as `1`
`Home`      | Boolean of Home or Away, with Home represented as `1`
`MP`        | Minutes Played
`FG`| Field Goals (includes both 2-point field goals and 3-point field goals)
`FGA`  | Field Goal Attempts (includes both 2-point field goal attempts and 3-point field goal attempts)
`FGP`      | Field Goal Percentage; the formula is FG / FGA
`TP`        | Time of Possession in minutes
`TPA` | 3-point Field Goal Attempts
`TPP`  | 3-point Field Goal Percentage
`FT`      | Free Throws
`FTA`        | Free Throw Attempts
`FTP` | Free Throw Percentage
`ORB`  | Offensive Rebounds
`DRB`      | Defensive Rebounds
`TRB`        | Total Rebounds
`AST` | Assists
`STL`  | Steals
`BLK`      | Blocks
`TOV`        | Turnovers
`PF`| Personal Fouls
`PTS`  | Points

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`IMDB_movies`](https://github.com/reisanar/datasets/blob/master/IMDB_movies.csv)
  </summary> Information of 1000 of the most popular movies on IMDB in the last 10 years. The data fields included are: Title, Genre, Description, Director, Actors, Year, Runtime, Rating, Votes, Revenue, Metascore (score of the movie on the _metacritic_ website)
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Rank`      | IMDb Ranking
`Title`        | Title Name
`Genre` | Category of Movie
`Description`  | Plot Description
`Director`      | Director Name
`Actors`        | Actor Names
`Year`| Year Released
`Runtime (Minutes)`  | Duration in minutes
`Rating`      | IMDb Rating
`Votes`        | Number of votes received
`Revenue (Millions)` | Total Movie Sales
`Metascore`  | Metascore Rating

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`netflixShows`](https://github.com/reisanar/datasets/blob/master/netflixShows.csv)
  </summary> Understanding the rating distributions of a variety of Netflix shows. Information for 1000 shows is provided including viewer ratings, Motion Picture Association of America film rating system that rates a film's suitability for certain audiences based on its content, release year, and others.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`title`      | Name of Show
`rating`        | TV Parental Guidelines Rating
`ratingLevel` | Description of rating content
`ratingDescription`  | Numerical correlation to rating from 10 to 110
`release year`      | Year of show premiere
`user rating score`        | Average rating
`user rating size`| Sample size of rating

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`harvardMIT`](https://github.com/reisanar/datasets/blob/master/harvardMIT.csv)
  </summary> In 2012, the Massachusetts Institute of Technology (MIT) and Harvard University launched open online courses on edX, a non-profit learning platform co-founded by the two institutions. Data contains information on 290 Harvard and MIT online courses, 250 thousand certifications, 4.5 million participants, and 28 million participant hours on the edX platform since 2012.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Institution`      | HarvardX or  MITx
`Course Number`        | Course Number Identifier
`Launch Date` | Date of Release
`Course Title`  | Name of Course
`Instructors`      | Instructor Names
`Course Subject`        | Name of Course
`Year`| Year 1-4
`Honor Code Certificates`  | Description of Certificate
`Participants (Course Content Accessed)`      | Number of total participants that accessed course content
`Audited (> 50% Course Content Accessed)`        | Number of participants with > 50% Course Content Accessed
`Certified` | Number of certified completions
`% Audited`  | Percentage audited of total participants
`% Certified`      | Percentage certified of total participants
`% Certified of > 50% Course Content Accessed`        | Percentage certified of the audited amount
`% Played Video` | Percent of partcipants that played video
`% Posted in Forum`  | Percent of participants that posted in the forums
`% Grade Higher Than Zero`      | Percentage of partcipants that ended with a grade higher than zero
`Total Course Hours (Thousands)`        | Total course hours of participation
`Median Hours for Certification` | Median hours to complete the course to the point of certification by 
`Median Age`  | Average age of a participant
`% Male`      | Percentage of participants that are male
`% Female`        | Percentage of participants that are female
`% Bachelor's Degree or Higher`| Percentage of participants with a bachelor degree or higher

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`starbucks`](https://github.com/reisanar/datasets/blob/master/starbucks.csv)
  </summary> Starbucks is an American coffee chain founded in Seattle. It serves both beverages and food. This dataset includes the nutritional information for Starbucks' food and drink menu items. All nutritional information for drinks are for a 12oz serving size.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Beverage_category`      | Type of beverage
`Beverage`        | Beverage name
`Beverage_prep` | Preparation of beverage, i.e. Soymilk, 2% milk, Venti, Short Nonfat Milk, Solo, Doppio 
`Calories`  | Number of calories per serving
`Total Fat (g)`      | Total grams of fat per serving
`Trans Fat (g)`        | Total grams of trans fat per serving
`Saturated Fat (g)`| Total grams of saturated fat per serving
`Sodium (mg)`  | Total milligrams of sodium per serving
`Total Carbohydrates (g)`      | Total grams of carbs per serving
`Cholesterol (mg)`        | Total milligrams of cholestrol per serving
`Dietary Fibre (g)` | Total grams of fiber per serving
`Sugars (g)`  | Total grams of sugar per serving
`Protein (g)`      | Total grams of protein per serving
`Vitamin A (% DV)`        | Percentage Vitamin A of standard daily value per serving
`Vitamin C (% DV)` | Percentage Vitamin C of standard daily value per serving
`Calcium (% DV)`  | Percentage Calcium of standard daily value per serving
`Iron (% DV)`      | Percentage Iron of standard daily value per serving
`Caffeine (mg)`        | Total milligrams of Caffeine per serving

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`macmenu`](https://github.com/reisanar/datasets/blob/master/macmenu.csv)
  </summary> This dataset provides a nutrition analysis of every menu item on the US McDonald's menu, including breakfast, beef burgers, chicken and fish sandwiches, fries, salads, soda, coffee and tea, milkshakes, and desserts.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Category`      | Categorization of item: Breakfast, Beef & Pork, Chicken & Fish, Beverages, Desserts, Salads, Snacks & Sides, Coffee & Tea, Smoothies & Shakes
`Item`        | Item name from menu
`Serving Size` | Size of one serving 
`Calories`  | Number of calories per serving
`Calories from Fat`      | Number of calories per serving coming from fat
`Total Fat`        | Total grams of fat per serving
`Total Fat (% Daily Value)`| Percentage fat of standard daily value per serving
`Saturated Fat`  |  Total grams of saturated fat per serving
`Saturated Fat (% Daily Value)`      | Percentage saturated fat of standard daily value per serving
`Trans Fat`        | Total grams of trans fat per serving
`Cholesterol` | Total milligrams of cholestrol per serving
`Cholesterol (% Daily Value)`  | Percenetage cholestrol of standard daily value per serving
`Sodium (mg)`  | Total milligrams of sodium per serving
`Sodium (% Daily Value)`        | Percentage sodium of standard daily value per serving
`Carbohydrates` | Total grams of carbs per serving
`Carbohydrates (% Daily Value)`  | Percentage carbs of standard daily value per serving
`Dietary Fibre (g)` | Total grams of fiber per serving
`Dietary Fiber (% Daily Value)`        | Percentage fiber of standard daily value per serving
`Sugars (g)`  | Total grams of sugar per serving
`Protein (g)`      | Total grams of protein per serving
`Vitamin A (% DV)`        | Percentage Vitamin A of standard daily value per serving
`Vitamin C (% DV)` | Percentage Vitamin C of standard daily value per serving
`Calcium (% DV)`  | Percentage Calcium of standard daily value per serving
`Iron (% DV)`      | Percentage Iron of standard daily value per serving

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`BreadBasket`](https://github.com/reisanar/datasets/blob/master/BreadBasket.csv)
  </summary> The dataset contains more than 6000 transactions from a bakery. Data set containing 15010 observations and more than 6000 transactions from a bakery. The data set contains the following columns: date, time, transaction ID, and item bought.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Date`      | Date of transaction
`Time`        | Time of transaction
`Transaction` | Transaction ID number, in which one transaction is a unique number
`Item`  | Item purchased


</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`disney_movies_total_gross`](https://github.com/reisanar/datasets/blob/master/disney_movies_total_gross.csv)
  </summary> - Additional dataset to consider: `disney-characters.csv` with Disney characters by hero or villain type. 

Information for 579 movies is provided including release date, genre, and total gross.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`movie_title`      | Name of Movie
`release_date`        | Date of release in Month DD, YYYY
`genre` | Type of Movie
`MPAA_rating`  | MPAA_rating: G, PG, PG-13, R, NC-17
`total_gross`      | Total gross profit of the movie
`inflation_adjusted_gross`        | Total gross profit of the movie adjusted for inflation

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`ICUAdmissions`](https://github.com/reisanar/datasets/blob/master/ICUAdmissions.csv)
  </summary> Data from a sample of 200 patients following admission to an adult intensive care unit (ICU)
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`ID`      | 
`Status`        | Patient status: 0=lived or 1=died
`Age` | Age in years
`Sex`  | 0=male or 1=female
`Race`      | 1=white, 2=black, or 3=other
`Service`        | 0=medical or 1=surgical
`Cancer`| Is cancer involved? 0=no or 1=yes
`Renal`  | Is chronic renal failure involved? 0=no or 1=yes
`Infection`      | Is infection involved? 0=no or 1=yes
`CPR`        | Patient gets CPR prior to admission? 0=no or 1=yes
`Systolic` | Systolic blood pressure (in mm of Hg)
`HeartRate`  | Pulse rate (beats per minute)
`Previous`      | Previous admission to ICU within 6 months? 0=no or 1=yes
`Type`        | Admission type: 0=elective or 1=emergency
`Fracture` | Fractured bone involved? 0=no or 1=yes
`PO2`  | (Partial oxygen level from blood gases under 60? 0=no or 1=yes
`PH`      | pH from blood gas under 7.25? 0=no or 1=yes
`PCO2`        | Partial carbon dioxide level from blood gas over 45? 0=no or 1=yes
`Bicarbonate` | Bicarbonate from blood gas under 18? 0=no or 1=yes
`Creatinine`  | Creatinine from blood gas over 2.0? 0=no or 1=yes
`Consciousness`      | Level: 0=conscious, 1=deep stupor, or 2=coma

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`cost-of-living-2018.csv`](https://github.com/reisanar/datasets/blob/master/cost-of-living-2018.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`City`      | Name of City
`Cost of Living Index`        | Cost of Living Index is a relative indicator of consumer goods prices, including groceries, restaurants, transportation and utilities. Does not include accommodation expenses such as rent or mortgage. If a city has a Cost of Living Index of 120, it means [Numbeo](https://www.numbeo.com/cost-of-living/) estimates it is 20% more expensive than New York (excluding rent).
`Rent Index` | Estimation of prices of renting apartments in the city compared to New York City. If Rent index is 80, Numbeo estimates that price of rents in that city is on an average 20% less than the price in New York.
`Cost of Living Plus Rent Index`  | Estimation of consumer goods prices including rent comparing to New York City
`Groceries Index`      | Estimation of grocery prices in the city compared to New York City
`Restaurant Price Index`        | Comparison of prices of meals and drinks in restaurants and bars compared to NYC
`Local Purchasing Power Index`| Shows relative purchasing power in buying goods and services in a given city for the average wage in that city. If domestic purchasing power is 40, this means that the inhabitants of that city with the average salary can afford to buy on an average 60% less goods and services than New York City residents with an average salary.

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`all_billboard_summer_hits`](https://github.com/reisanar/datasets/blob/master/all_billboard_summer_hits.csv)
  </summary> Songs that were part of the Billboard Summer Hits list from 1958 to 2017. Dataset includes music features as provided by the Spotify API, including the "acousticness" and "danceability" of the song, and measurements of valence, tempo, among other audio features. A description of the features can be found at <https://developer.spotify.com/documentation/web-api/reference/tracks/get-audio-features/>
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`danceability`      | 	Danceability describes how suitable a track is for dancing based on a combination of musical elements including tempo, rhythm stability, beat strength, and overall regularity. A value of 0.0 is least danceable and 1.0 is most danceable. 
`energy`        | 	Energy is a measure from 0.0 to 1.0 and represents a perceptual measure of intensity and activity. Typically, energetic tracks feel fast, loud, and noisy. For example, death metal has high energy, while a Bach prelude scores low on the scale. Perceptual features contributing to this attribute include dynamic range, perceived loudness, timbre, onset rate, and general entropy. 
`key` | 	The estimated overall key of the track. Integers map to pitches using standard Pitch Class notation . E.g. 0 = C, 1 = C♯/D♭, 2 = D, and so on. If no key was detected, the value is -1.
`loudness`  | 	The overall loudness of a track in decibels (dB). Loudness values are averaged across the entire track and are useful for comparing relative loudness of tracks. Loudness is the quality of a sound that is the primary psychological correlate of physical strength (amplitude). Values typical range between -60 and 0 db.
`mode`      | 	Mode indicates the modality (major or minor) of a track, the type of scale from which its melodic content is derived. Major is represented by 1 and minor is 0.
`speechiness`        | 	Speechiness detects the presence of spoken words in a track. The more exclusively speech-like the recording (e.g. talk show, audio book, poetry), the closer to 1.0 the attribute value. Values above 0.66 describe tracks that are probably made entirely of spoken words. Values between 0.33 and 0.66 describe tracks that may contain both music and speech, either in sections or layered, including such cases as rap music. Values below 0.33 most likely represent music and other non-speech-like tracks.
`acousticness`| 	A confidence measure from 0.0 to 1.0 of whether the track is acoustic. 1.0 represents high confidence the track is acoustic. 
`instrumentalness`  | 	Predicts whether a track contains no vocals. “Ooh” and “aah” sounds are treated as instrumental in this context. Rap or spoken word tracks are clearly “vocal”. The closer the instrumentalness value is to 1.0, the greater likelihood the track contains no vocal content. Values above 0.5 are intended to represent instrumental tracks, but confidence is higher as the value approaches 1.0. 
`liveness`      | 	Detects the presence of an audience in the recording. Higher liveness values represent an increased probability that the track was performed live. A value above 0.8 provides strong likelihood that the track is live. 
`valence`        | 	A measure from 0.0 to 1.0 describing the musical positiveness conveyed by a track. Tracks with high valence sound more positive (e.g. happy, cheerful, euphoric), while tracks with low valence sound more negative (e.g. sad, depressed, angry).
`tempo` | 	The overall estimated tempo of a track in beats per minute (BPM). In musical terminology, tempo is the speed or pace of a given piece and derives directly from the average beat duration. 
`track_uri`  | spotify track uri
`duration_ms`      | 	The duration of the track in milliseconds.
`time_signature`        | 	An estimated overall time signature of a track. The time signature (meter) is a notational convention to specify how many beats are in each bar (or measure).
`key_mode` | mode of key
`playlist_name`  | name of playlist
`playlist_img`      | image of playlsit url
`track_name`        | name of track
`artist_name` | name of artist
`album_name`  | name of album
`album_img`      | image of album url
`year`        | year of release

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`statewords`](https://github.com/reisanar/datasets/blob/master/statewords.csv)
  </summary> This is the data behind the FiveThirtyEight story [_"What America's Governors Are Talking About"_](https://fivethirtyeight.com/features/what-americas-governors-are-talking-about/). Full description of all variables is included in <https://github.com/fivethirtyeight/data/tree/master/state-of-the-state>. It contains every one-word phrase that was mentioned in at least 10 speeches and every two- or three-word phrase that was mentioned in at least five speeches after a list of stop-words was removed and the word "healthcare" was replaced with "health care" so that they were not counted as distinct phrases.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`phrase`      | one, two, or three-word phrase
`category`        | thematic categories for n-grams hand-coded by FiveThirtyEight staff: economy/fiscal issues, education, health care, energy/environment, crime/justice, mental health/substance abuse
`d_speeches` | number of Democratic speeches containing the n-gram
`r_speeches`  | number of Republican speeches containing the n-gram
`total`      | total number of speeches containing the n-gram
`percent_of_d_speeches`        | percent of the 23 Democratic speeches containing the phrase
`percent_of_r_speeches`| percent of the 27 Republican speeches containing the phrase
`chi2`  | chi^2 statistic
`pval`      | p-value for chi^2 test

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`spacex`](https://github.com/reisanar/datasets/blob/master/spacex.csv)
  </summary> SpaceX launch data including date, booster version, payload mass, customer, and mission outcome. If you use this dataset, please update it to include the latest information on launches <https://www.spacex.com/missions>.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Flight Number`      | Flight number
`Date`        | Date of launch 
`Time (UTC)` | Time of launch in Coordinated Universal Time
`Booster Version`  | Booster version used
`Launch Site`      | Launch site of flight
`Payload`        | Name of spaceship 
`Payload Mass (kg)`| Weight of payload in kg
`Orbit`  | Orbit classification
`Customer`      | Customer of flight
`Mission Outcome`        | Description of mission outcome
`Landing Outcome` | Description of landing outcome

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`Airfares`](https://github.com/reisanar/datasets/blob/master/Airfares.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`S_CODE`      | Starting airport's code 
`S_CITY`        | Starting city
`E_CODE` | Ending airport's code
`E_CITY`  | Ending city
`COUPON`      | Average number of coupons (a one-coupon flight is a nonstop flight, a two-coupon flight is a one-stop flight, etc.) for that route
`NEW`        | Number of new carriers entering that route between Q3-96 and Q2-97
`VACATION`| Whether (`Yes`) or not (`No`) a vacation route
`SW`  | Whether (`Yes`) or not (`No`) Southwest Airlines serves that route
`HI`      | Herfindahl index: measure of market concentration
`S_INCOME`        | Starting city's average personal income
`E_INCOME` | Ending city's average personal income
`S_POP`  | Starting city's population
`E_POP`      | Ending city's population
`SLOT`        | Whether or not either endpoint airport is slot-controlled (this is a measure of airport congestion)
`GATE` | Whether or not either endpoint airport has gate constraints (this is another measure of airport congestion)
`DISTANCE`  | Distance between two endpoint airports in miles
`PAX`      | Number of passengers on that route during period of data collection
`FARE`        | Average fare on that route

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`eBayAuctions`](https://github.com/reisanar/datasets/blob/master/eBayAuctions.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Category`     | Category of the auctioned item.
`currency`     | Currency    
`sellerRating` |  a rating by eBay, as a function of the number of "good" and "bad" transactions the seller had on eBay
`Duration`     | Number of days the auction lasted (set by seller at auction start)
`endDay`       | Day of week that the auction closed
`ClosePrice`   | Price item sold at (converted into USD)
`OpenPrice`    | Initial price set by the seller (converted into USD)
`Competitive?` | Whether the auction had a single bid (`0`) or more (`1`)

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`presidentialElections`](https://github.com/reisanar/datasets/blob/master/presidentialElections.csv)
  </summary> Democratic share of the presidential vote, 1932-2016, in each state and the District of Columbia.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`state`      | Name of state
`demVote`        | percent of the vote for president won by the Democratic candidate
`year` | integer year in YYYY format
`south`  | TRUE if state is one of the 11 states of the former Confederacy

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`ufc`](https://github.com/reisanar/datasets/blob/master/ufc.csv)
  </summary> Upper Flat Creek forest cruise tree data. These are a subset of the tree measurement data from the Upper Flat Creek unit of the University of Idaho Experimental Forest, which was measured in 1991. The inventory was based on variable radius plots with 6.43 sq. m. per ha. BAF (Basal Area Factor).The forest stand was 121.5 ha. This version of the data omits errors, trees with missing heights, and uncommon species. The four species are Douglas-fir, grand fir, western red cedar, and western larch.

 Variables    |  Description
------------  |----------------------------------------------------------------
`plot`      | plot label
`tree`        | tree label
`species` | species kbd with levels DF, GF , WC, WL
`dbh.cm`  | tree diameter at 1.37m from the ground, measured in centimetres
`height.m`      | tree height measured in meters

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`trees`](https://github.com/reisanar/datasets/blob/master/trees.csv)
  </summary> These are a subset of the von Guttenberg data, a set of measurements on Norway spruce (Picea abies [L.] Karst) in several different locations and site categories.

 Variables    |  Description
------------  |----------------------------------------------------------------
`ID`      | A factor identifying the tree by location, site, and tree number.
`Age`        | The age at which the tree was measured.
`Vol ` | The bole volume of the tree, in cubic dm.

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`water`](https://github.com/reisanar/datasets/blob/master/water.csv)
  </summary> Can Southern California's water supply in future years be predicted from past data? One factor affecting water availability is stream runoff.  If runoff could be predicted, engineers, planners and policy makers could do their jobs more efficiently. Multiple linear regression models have been used in this regard This dataset contains 43 years worth of precipitation measurements taken at six sites in the Owens Valley ( labeled APMAM, APSAB, APSLAKE, OPBPC, OPRC, and OPSLAKE), and stream runoff volume at a site near Bishop, California.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Year`      |  collection year
`APMAM`        |  Snowfall in inches measurement site
`APSLAKE` |  Snowfall in inches measurement site
`APSAB` | Snowfall in inches measurement site
`OPBPC`  |  Snowfall in inches measurement site
`OPRC`      |  Snowfall in inches measurement site
`OPSLAKE`        | Snowfall in inches measurement site
`BSAAM`| Stream runoff near Bishop, CA, in acre-feet

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`WorldCities`](https://github.com/reisanar/datasets/blob/master/WorldCities.csv)
  </summary> A data frame with 23,018 observations on the following 10 variables.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`code`      | The ISO (?) city code
`name`        | Name of the city
`latitude` | location in degrees
`longitude`  | location in degrees
`country`      | Two letter country code
`countryRegion`        | A numerical region
`population`| Population
`regionCode`  | ISO (?) Code
`region`      | Name of the region
`date`        | Date estimate made

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`worldcup`](https://github.com/reisanar/datasets/blob/master/worldcup.csv)
  </summary> Data on players from the 2010 World Cup
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Position`      | a factor with levels Defender Forward Goalkeeper Midfielder
`Time`        | Time played in minutes
`Shots` | Number of shots attempted
`Passes`  | Number of passes made
`Tackles`      | Number of tackles made
`Saves`        | Number of saves made

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`vehicles`](https://github.com/reisanar/datasets/blob/master/vehicles.csv)
  </summary> 
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`id`      | Unique EPA identifier
`make`        | Manufacturer
`model` | Model name
`year`  | Model year
`class`      | EPA vehicles size class, http://www.fueleconomy.gov/feg/ws/wsData.shtml#VClass
`trans`        | Transmission
`drive`| Drive Train
`cyl`  | Number of cylinders
`displ`      | Engine displacement, in litres
`fuel`        | Fuel type
`hwy` | Highway fuel economy, in mpg
`cty`  | City fuel economy, in mpg

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`Credit`](https://github.com/reisanar/datasets/blob/master/Credit.csv)
  </summary> A simulated data set containing information on ten thousand customers. The aim here is to predict which customers will default on their credit card debt.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`ID`      | Identification
`Income`        | Income in $10,000's
`Limit` | Credit limit
`Rating`  | Credit rating
`Cards`      | Number of credit cards
`Age`        | Age in years
`Education`| Number of years in education
`Gender`  | A factor with levels Male and Female
`Student`      | A factor with levels No and Yes indicating whether the individual was a student
`Married`        | A factor with levels No and Yes indicating whether the individual was married
`Ethnicity` | A factor with levels African American, Asian, and Caucasian indicating the individual's ethnicity
`Balance`  | Average credit card balance in $

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`AllCountries`](https://github.com/reisanar/datasets/blob/master/AllCountries.csv)
  </summary> Data on the countries of the world. Most data from 2008 to avoid many missing values in more recent years. Data collected from worldbank.org.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Country`      | Name of the country
`Code`        | Three letter country code
`LandArea` | Size in sq. kilometers
`Population`  | Population in millions
`Energy`      | Energy usage (kilotons of oil)
`Rural`        | Percentage of population living in rural areas
`Military`| Percentage of government expenditures directed toward the military
`Health`  | Percentage of government expenditures directed towards healthcare
`HIV`      | Percentage of the population with HIV
`Internet`        | Percentage of the population with access to the internet
`Developed` | Categories for kilowatt hours per capita, 1= under 2500, 2 = 2500 to 5000, 3 = over 5000
`BirthRate`  | Births per 1000 people
`ElderlyPop`      | Percentage of the population at least 65 years old
`LifeExpectancy`        | Average life expectancy (years)
`CO2` | CO2 emissions (metric tons per capita)
`GDP`  | Gross Domestic Prodcut (per capita)
`Cell`      | Cell phone subscriptions (per 100 people)
`Electricity`        | Electric power consumption (kWh per capita)

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`CommuteAtlanta`](https://github.com/reisanar/datasets/blob/master/CommuteAtlanta.csv)
  </summary> Commute times and distance for a sample of 500 people in Atlanta. Data were extracted respondents in the Atlanta metropolitan area. They include only cases where the respondent worked somewhere other than home. Sample chosen using DataFerret at http://www.thedataweb.org/index.html
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`City`      | Atlanta
`Age`        | Age of the respondent (in years)
`Distance` | Commute distance (in miles)
`Time`  | Commute time (in minutes)
`Sex`      | F or M

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`CommuteStLouis`](https://github.com/reisanar/datasets/blob/master/CommuteStLouis.csv)
  </summary> Commute times and distance for a sample of 500 people in St. Louis. Data were extracted respondents in the St. Louis metropolitan area. They include only cases where the respondent worked somewhere other than home. Sample chosen using DataFerret at http://www.thedataweb.org/index.html
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`City`      | St. Louis
`Age`        | Age of the respondent (in years)
`Distance` | Commute distance (in miles)
`Time`  | Commute time (in minutes)
`Sex`      | F or M


</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`FloridaLakes`](https://github.com/reisanar/datasets/blob/master/FloridaLakes.csv)
  </summary> Water quality for a sample of lakes in Florida
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`ID`      | An identifying number for each lake
`Lake`        | Name of the lake
`Alkalinity` | Concentration of calcium carbonate (in mg/L)
`pH`  | Acidity
`Calcium`      | Amount of calcium in water
`Chlorophyll`        | Amount of chlorophyll in water
`AvgMercury`| Average mercury level for a sample of fish (large mouth bass) from each lake
`NumSamples`  | Number of fish sampled at each lake
`MinMercury`      | Minimum mercury level in a sampled fish
`MaxMercury`        | Maximum mercury level in a sampled fish
`ThreeYrStdMercury` | Adjusted mercury level to account for the age of the fish
`AgeData`  | Mean age of fish in each sample

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`HollywoodMovies`](https://github.com/reisanar/datasets/blob/master/HollywoodMovies.csv) 
  </summary> Information for 136 movies released from Hollywood in 2011.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Movie`      | Title of movie
`LeadStudio`        | Studio that released the movie
`RottenTomatoes` | Rotten Tomatoes rating (reviewers)
`AudienceScore`  | Audience rating (via Rotten Tomatoes)
`Story`      | General theme - one of 21 themes
`Genre`        | Type of Movie: Action, Adventure, Animation, Comedy, Drama, Fantasy, Horror, Romance, or Thriller
`TheatersOpenWeek`| Number of screens for opening weekend
`BOAverageOpenWeek`  | Average box office income per theater - opening weekend
`DomesticGross`      | Gross income for domestic viewers (in millions)
`ForeignGross`        | Gross income for foreign viewers (in millions)
`WorldGross` | Gross income for all viewers (in millions)
`Budget`  | Production budget (in millions)
`Profitability`      | WorldGross/Budget
`OpeningWeekend`        | Opening weekend gross (in millions)

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`MiamiHeat`](https://github.com/reisanar/datasets/blob/master/MiamiHeat.csv)
  </summary> Game log data for all the Miami Heat basketball team in 2010-11. Information from online boxscores for all 82 regular season games played by the Miami Heat during the 2010-11 regular season.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Game`      | ID number for each game
`Date`        | Data the game was played
`Location` | Away or Home
`Opp`  | Opponent team
`Win`      | Game result: L or W
`FG`        | Field goals made
`FGA`| Field goals attempted
`FG3`  | Three-point field goals made
`FG3A`      | Three-point field goals attempted
`FT`        | Free throws made
`FTA` | Free throws attempted
`Rebounds`  | Total rebounds
`OffReb`      | Offensive rebounds
`Assists`        | Number of assists
`Steals` | Number of steals
`Blocks`  | Number of shots blocked
`Turnovers`      | Number of turnovers
`Fouls`        | Number of fouls
`Points` | Number of points scored
`OppFG`  | Opponent's field goals made
`OppFGA`      | Opponent's Field goals attempted
`OppFG3`        | Opponent's Three-point field goals made
`OppFG3A`| Opponent's Three-point field goals attempted
`OppFT`  | Opponent's Free throws made
`OppFTA`        | Opponent's Free throws attempted
`OppOffReb` | Opponent's Offensive rebounds
`OppRebounds`  | Opponent's Total rebounds
`OppAssists`      | Opponent's assists
`OppSteals`        | Opponent's steals
`OppBlocks`| Opponent's shot blocked
`OppTurnovers`  | Opponent's turnovers
`OppFouls`        | Opponent's fouls
`OppPoints`| Opponent's points scored

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`NutritionStudy`](https://github.com/reisanar/datasets/blob/master/NutritionStudy.csv) 
  </summary> Variables related to nutrition and health for 315 individuals.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`ID`      | ID number for each subject in this sample
`Age`        | Subject's age (in years)
`Smoke` | a factor with levels No Yes
`Quetelet`  | Weight/(Height^2)
`Vitamin`      | Vitamin use: 1 = Regulary, 2 = Occasionally, or 3 = No
`Calories`        | Number of calories consumer per day
`Fat`| Grams of fat consumed per day
`Fiber`  | Grams of fiber consumed per day
`Alcohol`      | Number of alcoholic drinks consumed per week
`Cholesterol`        | Cholesterol consumed (mg per day)
`BetaDiet` | Dietary beta-carotene consumed (mcg per day)
`RetinolDiet`  | Dietary retinol consumed (mcg per day)
`BetaPlasma`      | Plasma beta-carotene (ng/ml)
`RetinolPlasma`        | Plasma retinol (ng/ml)
`Gender` | Coded as Female or Male
`VitaminUse`  | Coded as No Occasional Regular
`PriorSmoke`      | Smoking status: 1 = Never, 2 = Former, or 3 = Current

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`RestaurantTips`](https://github.com/reisanar/datasets/blob/master/RestaurantTips.csv) 
  </summary> Tip data from the First Crush Bistro in Potsdam, NY. Restaurant bills were collected over a two week period that was believed to provide a good sample of customers. Data recorded from 157 bills with 7 variables.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Bill`      | Size of the bill (in dollars)
`Tip`        | Size of the tip (in dollars)
`Credit` | Paid with a credit card? n or y
`Guests`  | Number of people in the group
`Day`      | Day of the week: m=Monday, t = Tuesday, w = Wednesday, th = Thursday, or f = Friday
`Server`        | Code for waiter/waitress: A, B, or C
`PctTip`| Tip as a percentage of the bill

</details>

<details>
  <summary> Click to see data dictionary for:
    
  [`SleepStudy`](https://github.com/reisanar/datasets/blob/master/SleepStudy.csv) 
  </summary> Data from a study of sleep patterns for college students. Obtained from sample of students who did skills tests to measure cognitive function, completed a survery that asked many questions about attitudes and habits, and kept a sleep diary to record time and quality of sleep over a two week period.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`Gender`      | 1 = male, 0 = female
`ClassYear`        | Year in school, 1 = first year, ..., 4 = senior
`LarkOwl` | Early riser of night owl? Lark, Neither, or Owl
`NumEarlyClass`  | Number of classes per week before 9am
`EarlyClass`      | Indicator for any early classes
`GPA`        | Grade point average (0-4 scale)
`ClassesMissed`| Number of classes missed in a semester
`CognitionZscore`  | Z-score on a test of cognitive skills
`PoorSleepQuality`      | Measure of sleep quality (higher values are poorer sleep)
`DepressionScore`        | Measure of degree of depression
`AnxietyScore` | Measure of amount of anxiety
`StressScore`  | Measure amount of stress
`DepressionStatus`      | Coded depression score: normal, moderate, or severe
`AnxietyStatus`        | Coded anxiety score: normal, moderate, or severe
`Stress` | Coded stress score: normal or high
`DASScore`  | Combined score for depression, anxiety and stress
`Happiness`      | Measure of degree of happiness
`AlcoholUse`        | Self-reported: Abstain, Light, Moderate, or Heavy
`Drinks` | Number of alcoholic drinks per week
`WeekdayBed`  | Average wqeekday bedtime (24.0 = midnight)
`WeekdayRise`      | Average weekday rise time (8.0 = 8am)
`WeekdaySleep`        | Average hours of sleep on weekdays
`WeekendBed`| Average weekend bedtime (24.0 = midnight)
`WeekendRise`  | Average weekend rise time (8.0 = 8am)
`WeekendSleep` | Average weekend bedtime (24.0 = midnight)
`AverageSleep` | Average hours of sleep for all days
`AllNighter`   | Had an all-nighter this semester? 1 = yes, 0 = no

</details>
See more details at https://cran.r-project.org/web/packages/Lock5Data/index.html

<details>
  <summary> Click to see data dictionary for:
    
  [`HomesForSale`](https://github.com/reisanar/datasets/blob/master/HomesForSale.csv) 
  </summary> Data on homes for sale in four states, selected from zillow.com in 2010.
  
 Variables    |  Description
------------  |----------------------------------------------------------------
`State`      | Location of the home: CA NJ NY PA
`Price`        | Asking price (in $1,000's)
`Size` | Area of all rooms (in 1,000's sq. ft.)
`Beds`  | Number of bedrooms
`Baths`      | Number of bathrooms

</details>
