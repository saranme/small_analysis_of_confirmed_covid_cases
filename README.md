# Small analysis of confirmed covid cases
Small analysis of confirmed Covid cases from Systematic dataset of Covid-19 policy, from Oxford University

# Data wrangling

Selection and explanation of the relevant variables for the study

* **The Oxford Covid-19 Government Response Tracker (OxCGRT) dataset**: collects the policies taken by governments during the Covid. The variables to analyze are:

    * *CountryName*: country
    * *Date*: date
    * *C1_School closing*: school closing policy
        * 0 - no action taken
        * 1 - it is recommended to close or significantly alter the operation of schools
        * 2 - closing is required (some levels or categories. For example only institutes or colleges)
        * 3 - it is required to close all levels
    * *ConfirmedCases*: cumulative confirmed Covid cases
    
    
* **HDI dataset**: collects the HDI Indices of each country. The HDI Index is an indicator that measures the level of development of the country according to variables such as life expectancy, education or per capita income.
    * *Country*: country
    * *2019*: last HDI Index found
    
    
* **Population dataset**: collects the number of inhabitants per country.
    * *Country Name*: country
    * *2020*: number of inhabitants, most up-to-date data

Data cleansing
* **HDI dataset**:
    * Selection of country and last HDI Index and elimination of the rest of variables.
    * Creation of a new variable that categorizes the HDI Index as low, medium, high and very high.
    
    
* **Population dataset**:
    * selection of country and number of inhabitants and elimination of the rest of the variables.
 
 
* **The Oxford Covid-19 Government Response Tracker (OxCGRT) dataset**:
    * Selection of the variables country, date, school closure policy and confirmed cases.
    * Elimination of the rest of variables for not being of interest to the study.
    * Transformation column *Date* to date format.
    * Creation of variable *daily increment of Covid cases*: to carry out a more detailed analysis of confirmed Covid cases.
    * Cleaning of variable *Jurisdiction*: I filter only NAT_TOTAL since the study is at the national level, not state or regional. Later this variable is eliminated.
        
        
* Union of *The Oxford Covid-19 Government Response Tracker (OxCGRT) dataset* with the rest of the dataset gives rise to the final dataframe:
    * variables country, date, school closure policy, confirmed cases, HDI categories and population.

# Data Analysis
Object of study:
* Which countries have a higher increase in Covid cases per month?
* Which countries have experienced more cases of Covid in relation to the population of each country?
* In the months with the highest Covid peaks, were the same policies taken in the schools as in the months with the fewest Covid peaks?
