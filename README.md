# ETL_Project
_______________________________

## Finding our Data Source:
World Bank

Data Sets: 
Population data: https://data.worldbank.org/indicator/SP.POP.TOTL
![population](https://user-images.githubusercontent.com/62813833/215004277-f2759a5e-d0c9-4818-8b15-71852f66081c.png)

GDP data: https://data.worldbank.org/indicator/NY.GDP.MKTP.CD 
![gdp](https://user-images.githubusercontent.com/62813833/215004378-07969ef8-44d6-4231-8d5d-24cb252507c8.png)


Our GDP dataset included the years 1960-2021, and also included regional and economic data along with specific country data. 
Lastly, our population dataset included the years 2000-2015, with only countries. There were 51 indicators present, but we choose "Population, total" as our indicator.

_______________________________

## Proposal/Findings: 
We chose these datasets to compare population and GDP of countries in the years 2010 - 2015.
Our hypothesis suggests there is a correlation between an increase in population and an increase in GDP (in USD).


We are going to load our refined dataset in Postgres for analysis.
_______________________________

## Data Cleanup and Transformation:
![popbrackersheaders](https://user-images.githubusercontent.com/62813833/215005313-15d3d338-b9b3-4f38-97bc-1cae8537d80e.PNG)

In our Jupyter Notebook, we imported our .CSV and .XLS and began the cleanup process:

* First we extracted our population data, and filtered data by population total 
  * We chose "Population, total" as our indicator
  ![pop-loc](https://user-images.githubusercontent.com/62813833/215004663-a956a878-8cac-4020-b4ef-a6373ecf0383.png)

* Then we selected our target columns and renamed them
![poprename](https://user-images.githubusercontent.com/62813833/215004739-aa8e1833-8ef8-440a-ba84-b702c3045556.png)
  * Filtered by the years 2010 - 2015 and removed any columns we deemed as redundant.
    ![poptargetcolumns](https://user-images.githubusercontent.com/62813833/215004777-8f6c7db2-65d8-4d36-8f56-c23feb0011d7.png)
  * For the years, we removed the brackets from the headers
  ![popbrackersheaders](https://user-images.githubusercontent.com/62813833/215005344-25d1afa1-01e3-4d5d-ac2c-c6e060105fd7.PNG)

______________________________

* We then imported our second data set, GDP Data, and selected our target columns and renamed them
![gdpcolumns](https://user-images.githubusercontent.com/62813833/215005485-7e7955f7-8b21-432f-969e-3bc06229f65d.PNG)
  * Renamed columns in our GDP dataset so they would be more cohesive when merged with our population dataset


* Finally, we merged our two dataframes together by country code
  * Renamed columns so our headers matched their original dataframe
  ![image](https://user-images.githubusercontent.com/62813833/215005612-61ec3172-7d12-4324-96a3-bc648640485f.png)

  * Dropped any N/A values in our new dataframe
  * Exported it to a CSV 
  
  ![image](https://user-images.githubusercontent.com/62813833/215005662-0d5968b8-5c98-4729-9171-61f54badf443.png)

  
_______________________________
## Load to Postgres
<img width="1072" alt="sqlscreenshot" src="https://user-images.githubusercontent.com/62813833/215006100-8270c3fe-d133-46c0-8a78-71fee8a58f6c.png">

  * Created a new database 
    * Created a table to upload our .CSV file 
    * Ran a query to view the table

  * This topic was chosen because our group was interested in finding out if there is a correlation between an increase in population and an increase in GDP.




