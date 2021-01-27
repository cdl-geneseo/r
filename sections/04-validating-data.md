← [Importing Data](03-importing-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Renaming & Recoding](05-renaming-recoding-data.md) →
---

# 4. Validating Data

Okay, we have imported the data. Did it work...correctly? Here's where it is important to think about the data. I often ask myself the following questions:

1. How many observations do I expect there to be? (this corresponds to the number of rows)
2. How many variables were there? (this corresponds to the number of columns)

Although it is tempting to look at the *entire* data object (and we can certainly do so using the **View()** function), scrolling through large data sets is often impractical and of little value. Consider for example, working with a data set that include 20+ variables and 10s of thousands of rows. In these cases, I prefer to think about the anticipated dimensions (i.e., the number of rows and columns) and check by asking *R* about those dimensions. I also like to check the variable names, and the variable types. Finally, it is always nice to get a peak at the data, if only the top/bottom few rows.

> Helpful tip: *R* is typically structured to process/report rows first, then columns.

In the previous lesson, we imported and stored frequency data. If you are jumping in here, you need to start by importing the data.

```r
phrases = read.csv('https://raw.githubusercontent.com/cdl-geneseo/r/main/data_files/phrases.csv')
library(openxlsx) # only needed once per session
negations = read.xlsx('https://github.com/cdl-geneseo/r/raw/main/data_files/negations.xlsx')
```

For convenience, I like to select shorter object names, which saves typing!

```r
p = phrases # creates a new object called p, which is equivalent to phrases
n = negations
```

### Check dimensions & structure

```r
dim(p) # dimensions: 4061 rows, 4 columns

nrow(p) # 4061 rows
ncol(p) # 4 columns

str(p) # structure
summary(p) # summary of variables

dim (n) # 28 rows, 2 columns

nrow(n) # 4061 rows
ncol(n) # 4 columns

str(n) # structure
summary(n) # summary
```

### Check variable names & types

Note the **[]** subset function is a special unamed function in *R*.

```r
names(p) # get all variable names
names(p)[1] # get the 1st variable name
names(p)[1:2] # first two variable names
names(p)[1:ncol(p)] # equivalent to names(p)
```