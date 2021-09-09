 # Weather Data Project 
 
The Weather Data Project is one of my first projects on Data Analysis
It is a time-series data set with per hour information about the weather conditions at a particular location.It records Temperature, Dew Point Temperature, Relative Humidity, Wind Speed, Visibility, Pressure and Conditions.  

## Data Source: Kaggle

##  Project outcomes:
####  We will be successfully answering a bunch of questions :

### 1. Check whether the data is sucessfully loaded or not
```
weather_df = pd.read_csv('Weather Data.csv')
weather_df.head()  
```
### 2. Find all the unique 'Wind Speed' values in data.
 ```
 weather_df['Wind Speed_km/h'].unique()
 ```
### 3. Number of times the weather is exactly clear
```
len(weather_df[weather_df['Weather'] == 'Clear'])
```
### 4. Find out the Null Values in our DataSet
```
weather_df.isnull().sum()
```
### 5. Rename the column 'weather' to 'weather condition'
```
weather_df = weather_df.rename(columns={'Weather':'Weather Condition'})
weather_df.info()
```
### 7.Number of times the 'wind speed was exactly equal to 4km/hr'
```
len(weather_df.groupby('Wind Speed_km/h').get_group(4))
```
### 8. Calculate the mean visibility
```
weather_df['Visibility_km'].mean()
```
### 9. Calculate the Standard Deviation of 'Pressure' in this data
```
weather_df['Press_kPa'].std()
```
### 10. Calculate the variance of 'Relative Humidity' in the data given
```
weather_df['Rel Hum_%'].var()
```
### 11. Displaying Results for condition where Weather Condition is equal to'Snow'
```
weather_df[weather_df['Weather Condition']=="Snow"]
```
### 12. Find all instances when 'Wind Speed' is greater than 24 and 'Visibility is 25'
```
weather_df[(weather_df['Wind Speed_km/h']>24) & (weather_df['Visibility_km']==25)]
```
### 13. What is the mean value of each column against each 'Weather Condition'
```
weather_df.groupby(weather_df['Weather Condition']).mean()
```
### 14. What is the Minimum and Maximum value of each column against each 'weather condition'
```
weather_df.groupby(weather_df['Weather Condition']).max()
```
### 15. Show all the records where 'weather condition' is Fog
```
weather_df[weather_df['Weather Condition']=='Fog']
```
### 15. Find all instances where 'Weather is clear' or 'visibility is above 40'
```
weather_df[(weather_df['Weather Condition']=='Clear') | (weather_df['Visibility_km'] > 40)]
```
### 16. All instances when 'weather is clear' and 'relative humidity is greater than 50' or 'Visibility is above 40'
```
weather_df[(weather_df['Weather Condition']=='Clear') & (weather_df['Rel Hum_%']>50) | (weather_df['Visibility_km'] > 40)]
```

## Project Setup
To clone this repository you will need to have Python compiler 
installed on your system alongside with the Pandas library.I would rather suggest that you download jupyter notebook if you've not already.

To access all of the files I recommend you fork this repo and then clone it locally. Instructions on how to do this can be found here: https://help.github.com/en/github/getting-started-with-github/fork-a-repo

The other option is to click the green "clone or download" button and then click "Download ZIP". You then should extract all of the files to the location you want to edit your code.

Installing Jupyter Notebook: https://jupyter.readthedocs.io/en/latest/install.html<br>
Installing Pandas library: https://pandas.pydata.org/pandas-docs/stable/install.html





