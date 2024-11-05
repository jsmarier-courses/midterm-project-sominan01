**November 4, 2024**<br>
**MPAD2003 Introductory Data Storytelling**<br>
**Somin An**<br>
**Presented to Jean-Sébastien Marier**<br>

# Midterm Project: Exploratory Data Analysis (EDA)

Use one hashtag symbol (`#`) to create a level 1 heading like this one.

## Foreword

For this assignment, you must extract data from a dataset provided by the instructor. You must then clean and analyze the data, create exploratory charts/visualizations, and find a potential story idea. Your assignment must clearly detail your process. You are expected to write about 1500-2000 words, and to include several screen captures showing the different steps you went through. Your assignment must be written with the Markdown format and submitted on GitHub Classroom.

I have been assigning different versions of this project to my digital journalism and data storytelling students for a few years now. Its structure was inspired by the main sections/chapters of [*The Data Journalism Handbook*](https://datajournalism.com/read/handbook/one/). This version was further inspired by the [Key Capabilities in Data Science](https://extendedlearning.ubc.ca/programs/key-capabilities-data-science) program offered by the University of British Columbia (UBC).

**Here are some useful resources for this assignment:**

* [GitHub's *Basic writing and formatting syntax* page](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax)
* [The template repository for this assignment in case you delete something by mistake](https://github.com/jsmarier/jou4100_jou4500_mpad2003_project2_template)

Did you notice how to create a hyperlink? In Markdown, we put the clickable text between square brackets and the actual URL between parentheses.

And to create an unordered list, we simply put a star (`*`) before each item.

## 1. Introduction

I will analyze a City of Ottawa dataset about a summary of service requests received through channels such as 311 Contact Centre, Client Service Centre, 311 Email, and Web-based Self-Service portal. It is open data to the public and the latest update was on October 3, 2024. The data includes date of service request, status, type, description, address, latitude, longitude, ward, and channel. 

Link to the original dataset on Open Ottawa:
https://311opendatastorage.blob.core.windows.net/311data/311opendata_currentyear.csv

The main goals for this assignment are cleaning the data using different methods, building pivot table and chart, and creating a story. 

## 2. Getting Data

Following the instruction above, I downloaded the CSV file and then file > import > insert > Import location: replace spreadsheet, separator type: coma, convert text to numbers, dates, and formulas > import data 

Screenshot of Import Data:
<img src="import-screen-capture1.png"/>

Public link to Google Sheets spreadsheet: 
https://docs.google.com/spreadsheets/d/1Yma-y9bHKEZ5epXcet01zzsU41Ia8wDiBIO_9p_B14E/edit?usp=sharing 

Use two hashtag symbols (`##`) to create a level 2 heading like this one.

![](import-screen-capture.png)<br>
*Figure 1: The "Import file" prompt on Google Sheets.*

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

Use three hashtag symbols (`###`) to create a level 3 heading like this one. Please follow this template when it comes to level 1 and level 2 headings. However, you can use level 3 headings as you see fit.

Valid 
There is no missing data. The values are within a valid range. 
For Column F, there are 3,020 \N listed which match the numbers of active status of complaints. 

Invalid (not sure) 
Isn’t dispatch includes email, voice in, and counter (?), are they not considered as one dispatch category? 

Missing values 
There are no missing values. 

\N is for private complaints. 

Column H represents latitude and 24,148 are listed as \N. 
Column I represents longitude and 24,149 are listed as \N like column H. 

(used as an example) For instance, *Deeper observation..Correlation between latitude, longitude, and address 
Most of latitude, longitude, and address are listed when dealing with roads and transportation. (and another factor) 
Roads and transportation 4,214
28539 - 4214 = 24325, (similar number as latitude and longitude blank space) 
Others are social community service, recreation and culture, and more.
There are all public domain complaints 


Support your claims by citing relevant sources. Please follow [APA guidelines for in-text citations](https://apastyle.apa.org/style-grammar-guidelines/citations).

**For example:**

As Cairo (2016) argues, a data visualization should be truthful...

### 3.2. Cleaning Data

Insert text here.

### 3.3. Exploratory Data Analysis (EDA)

Insert text here.

**This section should include a screen capture of your pivot table, like so:**

![](pivot-table-screen-capture.png)<br>
*Figure 2: This pivot table shows...*

**This section should also include a screen capture of your exploratory chart, like so:**

![](chart-screen-capture.png)<br>
*Figure 3: This exploratory chart shows...*

## 4. Potential Story

Insert text here.

## 5. Conclusion

Insert text here.

## 6. References

Include a list of your references here. Please follow [APA guidelines for references](https://apastyle.apa.org/style-grammar-guidelines/references). Hanging paragraphs aren't required though.

**Here's an example:**

Bounegru, L., & Gray, J. (Eds.). (2021). *The Data Journalism Handbook 2: Towards A Critical Data Practice*. Amsterdam University Press. [https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153](https://ocul-crl.primo.exlibrisgroup.com/permalink/01OCUL_CRL/hgdufh/alma991022890087305153)
