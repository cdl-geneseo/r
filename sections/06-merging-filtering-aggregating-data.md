↻ [Lessons](../README.md#lessons)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;← [5. Renaming & Recoding Data](05-renaming-recoding-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[7. Visualization Techniques](07-visualization-techniques.md) →

# 6. Merging, filtering & aggregating data

*R* is a great environment for organizing and restructuring data. I frequently encounter a situation where I have multiple datasets with different information that I would like to combine. The two (or more) data frames can be merged together as long as they share a key variable. In the previous lessons, we have been working with two data frames that each contain a variable that specifies the negation word (viz., *not* or a contraction). The phrases (**p**) data frame contains information about the phrase (e.g., *don't hesitate*) and the negation (**n**) data frame contains information about the frequency of the negation word. For further analysis, it would be helpful to combine these data into a single data frame.

Before proceeding, it is important that you have the data objects p and n created in the [Validating Data lesson](04-validating-data.md) and that you have renamed variables as demonstrated in [Renaming & Recoding lesson](05-renaming-recoding-data.md).

We will use the **merge()** function to merge the **p** and **n** data frames into a new data frame called **d**. Note that the **p** contains some values that are missing from the **n** data frame. We can choose to keep all the observations in the **p** data frame by using the **all.x = T** parameter.

```r
## First, we can check the dimensions
dim(p) # 4061 rows, 7 columns
dim(n) # 28 rows, 2 columns

dim(merge(p,n)) # 4031 rows (missing rows), 8 columns (as expected)

dim(merge(p,n,all.x = T)) # keeps all rows from the first data frame

## Preview the merged data
head(merge(p,n,all.x = T))
tail(merge(p,n,all.x = T))

## Merge into a single data frame

d = merge(p,n,all.x = T)
dim(d) # 4061 rows (same as p), 8 columns (9 columns minus 1 shared column)
```

Now that we have a single data frame, we can make some decisions. We may want to reorder the columns, and we also may want to remove observations (i.e., rows) with missing data. Let's give it a try!

```r
## Check outcome before committing
head(d[,c(7,8,1:6)])

## If satisfied with the new order, then replace d with a new version of itself (be careful!)
d = d[,c(7,8,1:6)]

## Now, let's check for missing data
View(d[!complete.cases(d),]) # 45 rows with NAs

dim(d[complete.cases(d),]) # 4016 rows (4061 minus 45)

## Filter out the observations with NAs
d = d[complete.cases(d),] # only keep trials without NAs
dim(d)
head(d)
```

## Subsetting the data

Sometimes it is really useful to create a new data frame based on a subset of the data. For example, suppose that we would like to focus on only those phrases that begin with *don't*.

```r
head(d[which(d$c1=="don't"),]) # preview the subset results

do_not = d[which(d$c1=="don't"),] # store in a new data frame
head(do_not)
nrow(do_not) # 449 phrases

## check on most frequenct phrases that begin with don't
head(do_not[order(do_not$phrase_freq,decreasing = T),]) # the most frequent is "don't know" with 1790 occurrences

```