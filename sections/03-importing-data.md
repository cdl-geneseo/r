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

## Let's practice!

If you still need to do so, download <a href="https://raw.githubusercontent.com/cdl-geneseo/r/main/data_files/phrases.csv">phrases.csv</a> and <a href="https://github.com/cdl-geneseo/r/raw/main/data_files/negations.xlsx">negations.xlsx</a> files to use during workshop

The data for this workshop derive from the Michigan Corpus of Academic Spoken English (Simpson, Swales, & Briggs, 2002) and frequency counts are reported in a subsequent paper (Pastizzo & Carbone, 2007). Given a recent interest in double-negatives (and negative framing in general), I selected a subset of spoken language from the corpus that included *not* and variants of *not* (e.g., *doesn't*). The *phrases.csv* file contains all of the two-word phrases that begin with a negation along with the frequencies of those phrases, and the *negations.xlsx* file contains the various negations and their frequency of occurrence within the 1.6 million word corpus.

One file format is a CSV (comma-separated values) and the other is Excel (xlsx). I included two typical formats to provide an opportunity to import two different file formats.

There are two methods to navigate to the downloaded files:

1. Directory-based approach: set the working directory within *R* before importing data.
2. File-chooser approach: choose the working directory with a file selection window.

### Directory-based approach

First, determine your current working directory (i.e., folder) with the **getwd()** function:

```r
getwd() # akin to pwd in a terminal
```

Next, set the current working directory to the folder that contains the downloaded files. I saved the files to the Desktop on my computer:

```r
setwd("/Users/pastizzo/Desktop/") # the path will vary by operating system
dir() # provides a list of files, akin to ls in a terminal
```

Import data and save as a new data object:

```r
phrases = read.csv('phrases.csv',header=T)
dim(phrases) # 4061 rows and 4 columns
head(phrases) # view top 6 rows
View(phrases) # spreadsheet view

library(openxlsx) # only needed once per session (may need to be installed, see [Software setup](01-software-setup.md))
negations = read.xlsx('negations.xlsx')
dim(negations) # 28 rows and 2 columns
head(phrases) # view top 6 rows
View(phrases) # spreadsheet view
```

<img src="https://github.com/cdl-geneseo/r/blob/main/images/import.png" height="250">

## References

 - Pastizzo, M.J., & Carbone, R.F. (2007). Spoken word frequency counts based on 1.6 million words in American English. *Behavior Research Methods, 39*, 1025-1028.

- Simpson, R., Swales, J., & Briggs, S. (2002). The Michigan corpus of academic spoken English. Retrieved July, 2005, from www.lsa.umich .edu/eli/micase/index.htm.