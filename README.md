# MLPP ETL Read Me


For this assignment I chose age and income variables as the ones to pull from the Census API.

They are as follows:

"B01001_002E" -"Male_Population"
"B01001_026E"- "Female_Population"
'B19013_001E' -"Median_Income"
'B01002_001E' -"Median_Age"
'B01002_002E' -"Median_Age_Male"
'B01002_003E' -"Median_Age_Female

I thought it might be interesting to see how gender and age affected the income of various block groups. With age and gender being potential sources of inequity I wanted to understand the role each played in median income for a block group.

All data comes from the Census American Community Survey of 2019

I utilized both the Census API and Census python library but committed to the API approach as it was more modular.

I also initially used pandas psql method to upload my table to the database as the number of rows I was uploading seemed small enough to perform the operation in a reasonable amount of time, however for the same reason of modular approach I instead opted to create a table and read the contents of my dataframe into a csv and then into the buffer and bulk insert from the buffer.

Since I was uncertain about the usefulness of the Census state and county numbers I cleaned them from the dataframe dictionary keys, separated them, and added them as columns inton the database for potential future use.
