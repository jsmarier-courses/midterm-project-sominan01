**November 4, 2024**<br>
**MPAD2003 Introductory Data Storytelling**<br>
**Somin An**<br>
**Presented to Jean-Sébastien Marier**<br>

# Midterm Project: Exploratory Data Analysis (EDA)

## Foreword

For this assignment, you must extract data from a dataset provided by the instructor. You must then clean and analyze the data, create exploratory charts/visualizations, and find a potential story idea. Your assignment must clearly detail your process. You are expected to write about 1500-2000 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub Classroom.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item.

## 1. Introduction

I will analyze the City of Ottawa dataset, which provides a summary of service requests received through various channels, including the 311 Contact Centre, Client Service Centre, 311 Email, and Web-based Self-Service portal. This open data is available to the public, with the latest update on October 3, 2024. The dataset includes details such as the date of the service request, status, type, description, address, latitude, longitude, ward number, and the channel.

# Link to the original dataset on Open Ottawa:
https://311opendatastorage.blob.core.windows.net/311data/311opendata_currentyear.csv

The main goals for this assignment are to clean the data using various methods, build a pivot table and chart, and create a potential story.

## 2. Getting Data

Following the instruction above, I downloaded the CSV file and then selected file > import > insert > Import location: replace spreadsheet, separator type: coma, convert text to numbers, dates, and formulas > import data. 

Screenshot of Import Data:
<img src="import-screen-capture1.png"/>

Public link to Google Sheets spreadsheet: 
https://docs.google.com/spreadsheets/d/1Yma-y9bHKEZ5epXcet01zzsU41Ia8wDiBIO_9p_B14E/edit?usp=sharing 

## General Obeservation: 
This data has 28539 rows and 11 columns before the data clean up. 
The data has some clutters, but it is cleaner than I expected.
The service request ID and opened date are in order.  
There are \N in description, closed date, address, latitude, longitude, and ward columns. For water and environment, many descriptions are written as /N. 
There are two blank rows in 28538 and 28539.  

## Specific Observations: 
Column C and D are nominal variables under categorical variables. 
Column E and F are discrete variables under numeric variables.
Here, dates can only be whole number and cannot be in decimal. 
Column B and K are nominal variables under categorical variables. 
Column H and I are continuous variables under numeric variables. 

## Formulate one hypothesis: 
Active complaints are usually roads and transportation, water and the environment, bylaw services that might be difficult to solve faster than complaints such as garbage and recycling and parking control. 

**Here are examples of functions and lines of code put in grey boxes:**

1. If you name a function, put it between "angled" quotation marks like this: `IMPORTHTML`.
1. If you want to include the entire line of code, do the same thing, albeit with your entire code: `=IMPORTHTML("https://en.wikipedia.org/wiki/China"; "table", 5)`.
1. Alternatively, you can put your code in an independent box using the template below:

``` r
=IMPORTHTML("https://en.wikipedia.org/wiki/China"; "table", 5)
```
This also shows how to create an ordered list. Simply put `1.` before each item.

## 3. Understanding Data

### 3.1. VIMO Analysis
Cairo mentioned (2016) data visualization is to enlighten and inform people. A good visualization is truthful with a reliable information. 
VIMO analysis is a method to check the data accuracy and validation.
VIMO stands for Valid, Invalid, Missing, and Outliers. 
Valid, Invalid, and Missing components focus on missing data and valid range. 
In this data, there are missing data. 
Through google sheets filter, I found some blank and /N in few sections. 
I added /N in service request id 202457133382 address section because it was missing data. I also added Bylaw Services in property standards - grass long/weeds based on original document provided by City of Ottawa.  
If the adress column is \N, latitude and longitude need to be also \N. 
Other than blank spaces, I double checked to see any errors between latitude, longtitude, and address.

### outliers
The values are extremely small or large relative to expectations. 
For instance, in my chart, Garbage and Recycling and License and Permits are outliers because Garbage and Recycling is the largest value and License and Permits is the smallest value. However, the data is not invalid just because the numbers are higher or smaller than norm. 

Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

### 3.2. Cleaning Data

I used three different methods to clean the data. 
First, I used SPLIT and CONCATENATE functions. 
I used SPLIT function to divide the English and French descriptions. 
After, I copied and pasted the value only and deleted the original English and French combined description, and French description which only leaves to English description in the data.  
Moreover, the bound of service requests are Ottawa, Ontario, so I decided to add the specific address using CONCATENATE function. 
Second, I froze the first row to see the category everytime I scrolled down the data. Then, I added the filter to entire column. 
Finally, I used OpenRefine to clean up the clusters. 
There are small changes to make through OpenRefine. 
For the channel column, I got rid of white space in one of the voice in category concluding 828 rows. 
I also narrowed down the category by merging zones to zoning, walk-in to walk in, and signal flasher to signal flash. 
I deleted the latitude and longitude columns because they were irrelevant to the data and the address can represent them instead.  

A screen capture of my dataset:
<img src="import-screen-capture2.png"/>

### 3.3. Exploratory Data Analysis (EDA)

Using the data, I created pivot table and chart. 
I chose two variables which are types of service requests and ward numbers. 
These two variables can illustrate wards that have the highest amounts of requests in Ottawa. I chose these two variables to show the amount of requests par ward.  
Garage and Recycling, Bylaw Services, and Roads and Transportations are the top three requests made in Ottawa. 
Ward 12 (Rideau-Vanier Ward), Ward 14 (Somerset), and Ward 15 (Kitchissippi) received the highest amounts of service requests. 

**This section should include a screen capture of your pivot table, like so:**
<img src="screen-capture3.png"/>
This pivot table displays the number of requests for each ward, as well as the total number of requests across all wards.

**This section should also include a screen capture of your exploratory chart, like so:**
<img src="screen-capture4.png"/>
This exploratory chart shows types of service requests by ward numbers with visual elements. I chose a line chart over other types of charts because it effectively compares the relationship or variation between two variables visually. The line chart I created illustrates trends and relationships within the data, allowing for a comparison of trends across different groups.

## 4. Potential Story

Ward 12, 14, and Ward 15 are downtown areas where many people live, work, and visit. This might be the reason why these wards have the highest service requests. For instance, noise requests occur more in downtown than towns outside of downtown. 
Moreover, city's highest service requests are garbage and recycling, bylaw services, and roads and transportations. These requests are part of daily acitivities that people usually do compared to licenses and permits and recreation and culture. Health and safety are relatable to the daily life but people usually contact other departments rather than City of Ottawa affiliated call centre for help or to request services. 

For this potential story, I can interview people living in ward 12 about each top three service requests. Then, I will interview people living in ward 5, the lowest service requests in Ottawa as a comparison. 

For the relevant data, I would search for demographics in each ward to compare how demographics affect the numbers of service requests. 
This is a link to current population and house hold estimates by ward:
https://ottawa.ca/en/living-ottawa/statistics-and-demographics/current-population-and-household-estimates

## 5. Conclusion

First, I would like to apologize for being late. Time management is crucial in the workplace and university, and I have not been doing well with submitting the assignment on time. To do this assignment better, I would start earlier to avoid late submission. 

Second, it was difficult to identify the differences between  descriptions. For example, new pool no fence and pool fence inquiry look the same but I was unsure to merge them as the same category. I wanted to make description category shorter but there are many detailed descriptions that sounded the same, but quite different. 

Third, most challenging process was my macbook air crashing and slowing down eveytime I made changes in Google Sheets. I had to redo the whole process by using Window computer on campus. 

Finally, most rewarding part was finding the small clusters by using Open Refine and Google Sheets filter. It was sastifying to find small clusters and fill out the blank based on the original data by City of Ottawa. 


## 6. References

Data Accuracy and Validation: Methods to ensure the quality of data. (2020b, September 23). Www.statcan.gc.ca. https://www.statcan.gc.ca/en/wtc/data-literacy/catalogue/892000062020008

Government of Canada, S. C. (2021, September 2). 5.5 Line chart. Www150.Statcan.gc.ca. https://www150.statcan.gc.ca/n1/edu/power-pouvoir/ch9/line-lineaire/5214824-eng.htm

The Truthful Art: Data, Charts, and Maps for Communication. (2016). New Riders.

