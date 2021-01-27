↻ [Lessons](../README.md#lessons)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;← [4. Validating Data](04-validating-data.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[6. Merging, Filtering & Aggregating](06-merging-filtering-aggregating-data.md) →

# 5. Renaming & Recoding Variables

It is often useful to rename variables either because the names are too lengthy, opaque, or will conflict with names in another data set that you plan to merge. Sometimes I encounter a data file (CSV or Excel) with missing variable names, which means I have to specify **header=F** within the **read.csv()** function. In that event, the default variable names are the generic, V1, V2, V3, etc.

Before proceeding, it is important that you have the data objects p and n created in the [previous lesson](04-validating-data.md).

It is interesting that the way to rename variables is closely related to the method of retrieving variable names. Try the following code:

```r

```