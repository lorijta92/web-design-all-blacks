## Goal

Use HTML and CSS to build a webpage that displays an analysis of the All Blacks match data, including charts and a scrolling data table. 

## Process

**Data Cleaning and Analysis**

Before building out the webpage, I first needed to perform basic data cleaning and analysis to create some charts. I downloaded a data set from [Kaggle]( https://www.kaggle.com/harryarthur/all-black-match-data20032018) and read it into Jupyter Notebook using Pandas. Next, I separated the year from the date and deleted extraneous columns. After, I calculated the correlation coefficients, using the Pearson method with `df.corr(method="pearson")`, for all applicable categories to be used later. 

The next step was to create the charts. The first, was a simple donut chart showing the total match results for the All Blacks. A pie chart was first created, and then a circle was layered on top to create the donut chart. 

The second, would display the match results over time as a stacked bar chart. The data first had to  be grouped by `Year` and `Result`, before then pivoting on `Year` using `df.pivot()`. To plot, tick positions were set and the total score calculated. From the total score, the percentage of wins, draws, and losses were calculated. The wins for each year were plotted first, then the draws (whose bottoms were set to the top of the win bars), and then the losses (whose bottoms were set to the top of the draw bars). This stacked bar process was then repeated to create stacked bar charts for the match results by opposition team

Next, I wanted to compare the average game rating (of both New Zealand and opposition teams) to the average point gap over time. The mean was taken for the data grouped by year, and then those results were stored in a data frame. The correlation coefficient was calculated to see if there was any meaningful connection between the categories. Then, simple line charts were plotted as subplots. 

To visualize the total sum point gap per opposition team, data was grouped by `Opposition Name`, and then plot as a standard bar chart. The individual point gap per team was also plot over time, though these charts were not used in the final webpage.

The last chart used, was a straight-forward scatter plot, showing the relationship between `Debutants` and `Point Gap`. 

Finally, the cleaned data frame was exported as an HTML table using `df.to_html()` to be used in the final webpage. 

**Web Page Design**
