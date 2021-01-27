← [Importing Data](03-importing-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Renaming & Recoding](05-renaming-recoding-data.md) →
---

# 4. Validating Data

Okay, now we have imported the data. Did it work...correctly? Here's where it is important to *think* about the data. I often ask myself the following questions:

1. How many observations do I expect there to be? (number of rows?)
2. How many variables were there? (number of columns?)

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
n = negations # ditto
```

### Check dimensions & structure

Notice in the code below that there are multiple ways to obtain the same information. Based on my experience, that *flexibility* can be very helpful and, in my view, part of what makes *R* an amazing environment to explore data. For example, on some occasions, I only need to know how many rows - the **nrow()** function - are in the data set. At other times, I'd like to see the dimensions and the variable names at the same time - the **str()** function.

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

Note the **[]** subset function is a special unamed function in *R*. Within the square brackets, we specify the element number, which can be stated explicitly or in the form of another function that evaluates to the desired number.

```r
names(p) # get all variable names

names(p)[1] # get the 1st variable name
names(p)[1:2] # first two variable names

names(p)[1:ncol(p)] # equivalent to names(p)

names(p)[4] # last variable, or
names(p)[ncol(p)] # or,
names(p)[dim(p)[2]] # recall that the second reported element of dim() is the number of columns

```

### Data preview

If the dimensions and names check out, then I take a quick peak at the data. I use the **head()** function to examine the top few rows and the **tail()** function to view the last few rows. Truncated data (i.e., fewer rows than expected) can be spotted easily by viewing the bottom of the file, and **tail()** is much more efficient than scrolling down countless pages to get to the bottom of a spreadsheet!

```r
head(p) # by default, shows the top 6 rows
head(p,10) # the second argument requests 10 rows

tail(p) # by default, shows the bottom 6 rows
tail(p,15) # show the bottom 15 rows
```

### Screenshot example

<img src="https://github.com/cdl-geneseo/r/blob/main/images/console2.png" height="700">