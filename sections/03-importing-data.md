← [Functions & Operators](02-functions-operators.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Validating Data](04-validating-data.md) →
---

# 3. Importing Data

In many cases, data may already be available in a text file, an Excel file, or an SPSS data file. One approach is to first open the data file with Excel or SPSS and save the file as a comma-separated values (*.csv) file. The *csv* file will contain commas to separate the columns in the original data file. Then, in *R*, use the **read.csv()** function to import the data.

Summary of steps to import data:


1. Open data file with Excel or SPSS
 - If a text file or an Excel file, provide variable names in the first row. If an SPSS data file, be sure to label variables.
2. 'File' -> 'Save as...' -> 'Comma delimited (.csv)' or 'Comma Separated Values (.csv)'
3. Open *csv* file with *R*

If the variable names are contained in the first row of the \textsl{csv} file, then the \texttt{read.csv()} function takes two arguments. The first argument is the filename. Instead of typing the filename, you may use the \texttt{file.choose()} function to cause a file chooser to open at the time that you execute the \texttt{read.csv()} function. The second argument specifies that there is a header.

For example, \texttt{read.csv(file.choose(),header=T)} can be used to import any comma-delimited data file that already contains variable names in the header (i.e., the first row). Two notes: (1) be sure to use an uppercase \texttt{T} to indicate \textsl{true}, and (2) the \texttt{file.choose()} function does not take an argument.

If, however, the comma-delimited data file \textsl{does not} contain variable names, then you can specify variable names at the time the data are imported into \textsl{R} with a third argument within the \texttt{read.csv()} function. The third argument specifies column (i.e., variable) names: \newline \texttt{col.names = c(`var1',`var2',`var3')}. \newline When specifying variable names within the \texttt{read.csv()} function, be sure to use \texttt{header=F} to indicate that the data file does not contain a header (i.e., a first row) with variable names. See R Code~\ref{list:import}.

Finally, it is useful to store the imported data in \textsl{R} by introducing a name for the data (e.g., \textsl{mydata}) and setting it equal to the results of the \texttt{read.csv()} function.

\begin{lstlisting}[caption=\small Importing data.,label=list:import]
> mydata = read.csv(file.choose(),header=T)
> mydata = read.csv(file.choose(),header=F,col.names=c('var1','var2','var3')
> head(mydata) # take a look at the top 6 lines
\end{lstlisting}

