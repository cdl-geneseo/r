↻ [Lessons](../README.md#lessons)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;← [4. Validating Data](04-validating-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[6. Merging, Filtering & Aggregating](06-merging-filtering-aggregating-data.md) →

# 5. Renaming & Recoding Variables

It is often useful to rename variables either because the names are too lengthy, opaque, or will conflict with names in another data frame that you plan to merge. Sometimes I encounter a data file (CSV or Excel) with missing variable names, which means I have to specify **header=F** within the **read.csv()** function. In that event, the default variable names are the generic, V1, V2, V3, etc.

Before proceeding, it is important that you have the data objects p and n created in the [previous lesson](04-validating-data.md).

It is interesting that the way to rename variables is closely related to the method of retrieving variable names. Try the following code:

```r
names(p)
names(n)
```

## Renaming

Notice that the first column in the phrases data frame (**p**) contains the same words as the first column in the negations data frame (**n**). In the next lesson, we will merge these two data frames into a single data object, which means that it will be helpful to have a shared variable name. At the same time, data frame **p** and **n** both contain frequency data in a column called **freq**. When merged, we would like to distinguish these two different frequencies. In the phrase (**p**) data frame, **freq** corresponds to the frequency of each phrase (e.g., "don't worry"). In the negation (**n**) data frame, **freq** corresponds to the frequency of each modifier (e.g., "don't").

Our goals are to:

1. rename the first variable in the negation (**n**) data frame to match the first variable in the phrases data frame (**p**)
2. rename the **freq** variables to be more specific

```r
names(n)[1] # confirm that this is the correct variable

names(n)[1] = "c1" # assign a new name that matches the first variable in p, or
names(n)[1] = names(p)[1] # this ensures that the exact same name is used

names(p)[4] # freq variable for phrases
names(p)[4] = "phrase_freq"

names(n)[2] # freq variable for negations
names(n)[2] = "neg_freq"

```

## Recoding

Some analyses and visualizations require a change to the nature of a variable through a transformation (e.g., converting numbers to category labels, computing the logarithm of values). In other situations, it is necessary to create new variables based on existing variables. To change variables or create new variables based on existing variables, we first need to access a variable from within a data frame. We can access a single variable using the **$** convention.

```r
p$phrase_freq # get all 4061 values of the phrase frequency variable

length(p$phrase_freq) # 4061

mean(p$phrase_freq) # produces an NA because there are missing data, try this instead:
mean(p$phrase_freq, na.rm = T) # removes NAs, mean = 5.516932
```

### A pop-up reveals the variable names
<img src="https://github.com/cdl-geneseo/r/blob/main/images/console3.png" height="400">

