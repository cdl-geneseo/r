← [Functions & Operators](02-functions-operators.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Validating Data](04-validating-data.md) →
---

# 3. Importing Data

In many cases, data may already be available in a text file, an Excel file, or an SPSS data file. One approach is to first open the data file with Excel or SPSS and then save the file as a comma-separated values (*.csv) file. The *csv* file will contain commas to separate the columns in the original data file. Then, in *R*, use the **read.csv()** function to import the data.

Summary of steps to import data:


1. Open data file with Excel or SPSS. If it is a text file or an Excel file, provide variable names in the first row. If an SPSS data file, be sure to label variables.
2. 'File' -> 'Save as...' -> 'Comma delimited (.csv)' or 'Comma Separated Values (.csv)'
3. Open *csv* file with *R*

If the variable names are contained in the first row of the *csv* file, then the **read.csv()** function takes two arguments. The first argument is the filename. Instead of typing the filename, you may use the **file.choose()** function to cause a file chooser to open at the time that you execute the **read.csv()** function. The second argument specifies that there is a header.

For example, **read.csv(file.choose(),header=T)** can be used to import any comma-delimited data file that already contains variable names in the header (i.e., the first row). Two notes: (1) be sure to use an uppercase **T** to indicate *true*, and (2) the **file.choose()** function does not take an argument. As another option, the filename can be a URL.

If, however, the comma-delimited data file *does not* contain variable names, then you can specify variable names at the time the data are imported into *R* with a third argument within the **read.csv()** function. The third argument specifies column (i.e., variable) names:

**col.names = c('var1','var2','var3')**

When specifying variable names within the **read.csv()** function, be sure to use **header=F** to indicate that the data file does not contain a header (i.e., a first row) with variable names.

Finally, it is useful to store the imported data in *R* by introducing a name for the data (e.g., **mydata**, **d**) and setting it equal to the results of the **read.csv()** function.

Let's practice!
