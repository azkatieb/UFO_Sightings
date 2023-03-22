# **UFO Sightings in Arizona**

![arizona ufo](/images/ufo%20arizona%202018.jpg)

## Group 1 Team Members: 
- Connie Aceves
- Angelica Rosario
- Jordan Peterson
- Katie Bernstein
***

# **Overview**
This respository includes the dataset, source code, images and other relevant documents for the Arizona UFO Sightings and Predictions project.

## Topic Rationale
Arizona is one of the top tourist destinations in the world for UFO sightings due to the high number of sightings over the last 50 years - totalling over 4600 sightings. As residents of Arizona, we selected this topic as a fun and interesting way to show the data visualization, machine learning, database and other data analytic skills we have learned throughout the bootcamp as well as explore a topic that pertains to our home state.

## Data Questions
* Does the amount of UFO sightings in Arizona increase at a similar rate as the population growth in Arizona cities?

***

# **Project Outline:** 

## __Datasets__

__UFO Sightings Data Source:__ https://www.kaggle.com/datasets/sadeghjalalian/ufo-sightings-in-usa

 Full text and geocoded UFO sighting reports from the National UFO Research Center (NUFORC). The National UFO Research Center (NUFORC) collects and serves over 100,000 reports of UFO sightings. This dataset contains the report content itself including the time, location duration, and other attributes in both the raw form as it is recorded on the NUFORC site as well as a refined, standardized form that also contains lat/lon coordinates. (source: kaggle.com)

__City and Population Data Source: US Census Bureau:__ https://data.census.gov/cedsci/

__World Population Review__ https://worldpopulationreview.com/

United States Census data was utilized to determine proper city naming conventions along with gathering population data for each year of the project scope (2000 to 2022) to allow us to analyze the growth of the cities in relationship to the number of sightings in each city.
***


## __Data Cleaning (Extract, Transform, Load):__
Steps for Preparing Data

Preprocessing the UFO dataset to manage unnecessary columns, rows with null values, and mixed data types before using algorithms.
- Data selection entails making good choices about which data will be used. Consider what data is available, what data is missing, and what data can be removed.
- Data processing involves organizing the data by formatting, cleaning, and sampling it. In the UFO dataset the cities names had numerous misspellings. 
- Data transformation entailed loading csv files into python and processed so it could be exported to be used in analysis. 

UFO dataset loaded into pandas dataframe: 
![pandas 1](/images/Panda1.png)

Pandas dataframe filtered for the state of Arizona:
![pandas 2](/images/Panda2.png)

Pandas loading Arizona city names to correct misspellings, left merge by city.
![pandas 3](/images/Panda3.png)

Pandas loaded Arizona population for the years 2000 to 2021 with merge on left and right keys.
![pandas 4](/images/Panda4.png)

Data transformation entailed loading csv files into python and processed so it could be exported to be used in analysis.
![pandas 5](/images/Panda5.png)

***

## __Database__
- Utilizing the Kaggle and population datasets, the data was loaded into a SQL database in PGAdmin and then exported into Python to be cleaned utilizing the ETL code created and then exported back into SQL. After the clean data for Arizona was imported back into SQL, the clean data table was then joined with the clean population table which held the Arizona cities and population data from the year 2000 to 2022. The table created can then be utilized to run the machine learning models. 
- We utilized a local instance of PGAdmin and a connection string using SQLAlchemy to connect to Python to demonstrate our team's database knowledge. Amazon Web Services (AWS) could be utilized for this process to hold the raw data files and the database and a connection string using SQLAlchemy to connect to Python/Google Colab for all team members to connect remotely and the provide the link to others outside the team as a longer term solution. 

SQL Database ERD (Entity Relationship Diagram)
![UFO AZ ERD](/images/UFO%20Final%20Project%20ERD%20Chart.png)
***

## Machine Learning Model 
We evaluated our data using the following models:
- Unsupervised K-means Clustering - we used this method because we had to convert all the labels to numbers 
- The 3D-Cluster model supports our hypothesis:
    Cities with larger populations have more sightings throughout a given year.
- We performed K-Means Clustering to determine the optimal number of clusters to test our dataset.
- Based on our ML unsupervised model, our elbow curve is around the 3 mark. 
       K=3 meaning 3 clusters would be best.

- SK Learn Module - Clustering
- ![Clustering](/images/UFO_3D_Clustering.png)
- Plotly
- ![plot](/images/UFO_Elbow.png)
- Matplotlib
- ![matplotlib](/images/UFO_Clusters.png)
- HV Plot
- ![plot](/images/UFO_Scaled.png)
***

## __Power BI Dashboard__
An interactive dashboard was created in Power BI that included all of our data for sightings in the US as well as drilled down to just the Arizona sightings.

UFO SIGHTINGS IN US 
![us dashboard](/images/UFO%20Sightings%20in%20the%20US.png)

UFO SIGHTINGS IN ARIZONA
![arizona dashboard](/images/Arizona%20UFO%20Dashboard.png)

***
### __Future Analysis Recommendations__

- Deeper Analysis on States that indicates what time of year & day UFO Sightings may occur, based on climate
- UFO Sighting characteristics by Country 
- How Economic variables & Pandemics, affect volume of Sightings


__National UFO Reporting Center Recommendations:__ 
- Less free form answers – more drop down options to reduce the amount of non-sense data or variability in the data. 
- Sighting Validation – new column or area of data where NUFORC can add their feedback that either approves or denies the sightings. Currently it is listed in the comment box. 

- Additional Datasets to include:
    - Weather Patterns
    - Locations of Government Testing Sites, Military Bases and other business locations that might effect the data.
***

### __Lessons Learned__
- Select a dataset that has less free form data fields
    - More conclusive results with machine learning models
- Fully understand the Frequency & Accuracy of the Organization’s Auditing Process 
    - When did this Auditing Process Begin?
    - Does everyone Audit with the Same Method? 
- There are numerous ways that city & town data can be aggregated – Not all sources go down to the same level of detail or use the same names
    EXAMPLES:  
    - Pinetop-Lakeside vs. Pinetop & Lakeside separately
    - Sightings in National Forests (no population)
***

### __Technologies Used__
- Dataset ETL/ERD: 
    - Python
    - Jupyter Notebook
    - Power Query
- Machine Learning Model: 
    - Google Colab – PySpark
    - Pandas
    - SKLearn Cluster
    - Plotly
    - Matplotlib
    - HV Plot
- Database Creation
    - PGAdmin: Creating tables and joining tables
    - SQL Alchemy: Connection String to Python
    - QuickDBA: ERD Creation
- Data Visualization
    - Power BI
***
## Presentation
![presentation slide](/images/Presentation%20Slide.png)
***
# **Conclusion**
![conclusion](/images/Conclusion%20Slide.png)
***