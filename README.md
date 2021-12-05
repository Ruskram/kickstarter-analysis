# kickstarter-analysis
Performing analysis on Kickstarter data to uncover trends

# Kickstarting with Excel

## Overview of Project

### Purpose

The purpose of this analysis is to help an upcoming playwright named Louise. She has a idea for a play called "Fever" and determined that it will cost her 10,000+ dollars to fund what she needs to make the play happen. She wants to start a crowdfunding campign to raise the money. This is where she needs our help. She has a list of data from all the kickstarters that happened over a 9 year period. There is a lot of data there and Louise dosen't know how to make sense of it. Our goal is to look at the data and provide information like what is the likely hood that with the budget the play will succeed, what percentage of plays in this goal range end up failing, or best times to start a kickstarter. This will help her have the tools to run a successful kickstarter.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/92827264/144694053-cd12c582-cb45-4e6b-a913-9cfbbb99ca58.png)

This graph was made to look at all the Theater kickstarters and the month that they started. This is to see if there is any impact to the success of a kickstarter based on when it starts. To come up with this analysis a few things needed to be done. First the data needed to be more refined so that it can be filtered in a way that only the desired data will show up. To do this the column "Category and Subcategory" needed to be broken up. This was done by copying the column and pasting it into the next available blank column. Using the data tab in the excel ribbon, there is a button called "Text to Columns". This button allows you to seperate the text in one column in to multiple columns by using the "Delimited" option and selecting "/" as the delimiter.

<img width="422" alt="image" src="https://user-images.githubusercontent.com/92827264/144694453-9f25a1c1-8e16-489b-b0d0-a854a2541791.png">

After this was done the new columns where renamed Parent category and Subcategory. This allows much easier filtering to find more specific information from the large amount of data.

Next, the data and the new columns where put into a pivot table. The pivot table is a great tool that allows data to be visualized by draging the desired information into 4 categories Filters, Columns, Rows, and Values. One challange that was encounters was that I had not used a pivot table before, so figuring out how to get all the information that was needed in the pivot table was a struggle. I kept experimenting with the categories until I was able to filter and show the information that I needed.


### Analysis of Outcomes Based on Goals

![Outcomes_vs_Goals](https://user-images.githubusercontent.com/92827264/144732697-a7f74db7-547b-426b-aa03-4a0d2d21321d.png)

This graph was made to look at price goals of the kickstarters and what the outcomes are for every price range. To start this section a list of price ranges and a list of columns in which to calucate data was provided. The first four columns are just looking through the data and counting how many of the kickstarters where successful, failed or canceled for each of the goal ranges. This was accomplished using the COUNTIFS() function. This function allows the use of conditions to be checked for each row of the data set and count each time that set of conditions is true. For example, =COUNTIFS(Kickstarter!$D:$D,"<1000",Kickstarter!$F:$F, "successful") is the function used to check the column "D" of the Kickstarter sheet which is the "Goals" for each kickstarter to see which one was under 1,000 dollars. The second condition in the formula Kickstarter!$F:$F, "successful" is to see if the first condition is true then is the column "F" which is Outcome also successful. The last 3 columns are calculating the percentage of each of the outcomes (Successful/Failed/Canceled). This was done by taking each outcome in the row and dividing it by the total. This section did not give me much difficulties because I have worked with functions in Excel for a while, but I can see someone having trouble with the COUNTIFS() function if they have never worked with it before.

![image](https://user-images.githubusercontent.com/92827264/144734343-7b884710-b7c7-499c-998c-799e865b6438.png)


### Challenges and Difficulties Encountered

Overall I did not really have many difficulties with this assignment. I use Excel extensively at work to manipulate data and get it into certain formats for my projects, so I am  comfortable with parsing data from a dataset. The only thing that gave me a bit of a pause was making a pivot table because I have never used one before.

One challenge that I can see someone having is with spliting data into multiple categories with the "Text to Columns" button if they do not know about this. This is a very powerful too especially if there is a large amount of data like in this worksheet. It can be done with cuting from the cell and pasting it, but with 4000+ rows would take forever. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

  1. The first conculsion that I can draw is that kickstarters that launch in the beginning of spring have a higher success. This could be that people are tired of being cooped at home in the winter and are more likely to want to go out and see some plays or theater once the weather starts getting better.
  2. The second conclusion is that around May time is when tax returns come back. People have a bit of extra mone in their pocket and are more likely to spend on supporting a play/theater kickstarter that they are interested. From the chart December has the lowest success which makes sense because everyone is saving money to spend on gifts.

- What can you conclude about the Outcomes based on Goals?

  My conclusion based on this is that the most successful kickstarters are lower budget ones. As the goal for price gets higher it is a lot more likely to fail or get canceled. Louise kickstarter is in the 10,000 ballpark so it still has a higher chance to succeed than to fail, but it is close to the range where the likelyhood switches. 

- What are some limitations of this dataset?

  One limitation of this graph is that it doesn't have the maximum/minimun donation amount. This might be deceptive because the kickstarter could not have had much interest but a generous donation covered 90% of the goal. This would make it more luck than and might be considered as an outlier.

- What are some other possible tables and/or graphs that we could create?

  I think a category vs percentage funded graph would be useful. This graph would show what kind of kickstarters get funded and would likely be easier to succeed.
