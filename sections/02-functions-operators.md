← [Software Setup](01-software-setup.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Importing Data](03-importing-data.md) →
---

# 2. Functions & Operators

## Functions

It's all about the functions!

The functions in *R* are analagous to those available within spreadsheet programs such as Excel. To use a function, one or more arguments/parameters need to be specified. For example, in Excel, you can compute the average of the values contained in the first 10 rows of column A (viz., A1:10) by entering the average function in some other cell (e.g., B1): =average(A1:A10) (n.b., functions in Excel always begin with =). Given the same 10 values (e.g., 3,4,5,4,5,6,7,8,9,7) stored in variable *x*, **mean(x)** returns the average in *R*.

```r
x = c(3,4,5,4,5,6,7,8,9,7)
mean(x)
```

A function performs an operation or a set of operations to accomplish a task. For example, the mean(x) function is used to sum the values of variable *x* and divide the sum by the number of *x* values. *R* comes with many functions that are part of pre-installed packages (n.b., a package is a collection of functions that serve a related purpose).

It is also possible to define your own functions. The following is an example of creating and storing a custom function that computes and reports the mean. Notice that the function itself is constructed from other functions.

```r
x = c(3,5,4,3,6,4,5,7)

myMean = function(x){
    val=sum(x)/length(x)
    cat("Mean:",val)
}

myMean(x) # using the function
```

To use functions in *R*, it helps to know how they are structured. The anatomy of a function is as follows:

- Function name: case-sensitive, appears before a set of parentheses.
- Arguments/parameters: input used by the function to perform its work. Arguments/parameters are comma-delimited, and need to be stated in a specific order or referenced by name.

It is typical that a function will take a number of parameters (some required, many optional) that are listed in a default order. Hint: Type a function name such as **barplot()** at the command prompt, position your cursory within the parentheses (if not already positioned there), and then press the TAB key. A list of arguments should appear. Or, you could type **?barplot** to view the help page, which begins with a list of arguments as well as a brief explanation of each argument. As you will see within the help page for **barplot()**, many of the arguments have default values.

When you use a function with multiple arguments, it is a good practice to employ the `argument = ' convention. For example, although you can use **barplot(x)**, because the 1st expected argument defines the height of the bars, it is safer to use **barplot(height=x)**. With the latter approach, the order of the arguments is irrelevant; however, with the former approach, the argument order must strictly match that defined on the function help page.

In general, *R* is blind to space, which means that **mean (x)** produces the same output as **mean(x)**; however, *R* is case-sensitive (e.g., **Mean(x)** will produce an error: Error in Mean(x) : could not find function "Mean"


## Mathematical & Logical Operators

To familiarize yourself with the mathematical and logical operators, try each of the examples in the table below at the command prompt **>** in the Console.

| Operation | Symbol/Function | Example | Result |
| --- | --- | --- | --- |
| Addition | + | 2 + 2 | 4 |
| Subtraction | - | 20 - 5 | 15 |
| Multiplication | * | 12 * 12 | 144 |
| Division | / | 86 / 2 | 43 |
| Power | ^ | 4^4 | 256 |
| Greater than | > | 3 > 2 | TRUE |
| Greater or equal | >= |  3 >= 4 | FALSE |
| Less than | < |  4 < 1 | FALSE |
| Less or equal | <= |  3 <= 3 | TRUE |
| Square Root | sqrt() |  sqrt(4) | 2 |
| Factorial | factorial() |  factorial(4) | 24 |
| Logarithm | log() |  log(732) | 6.595781 |
| Exponential | exp() |  exp(6.595781) | 732.0004 |
| Order of Operations | |  20 - 2 * 3 | 14 |
| Order of Operations | () | (20 - 2) * 3 | 54 |
| Equal to? | == |  4 == 4 | TRUE |
| Assignment | = |  x = 4 | no result |
| Assignment | <- |  x <- 4} | no result |