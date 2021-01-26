↻ [Start/README](../README.md)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;[Functions & Operators](02-functions-operators.md) →
---

# 1. Getting Started

## Install *R* and *RStudio*

To prepare for the workshop, we recommend installing both *R* and *R* Studio. You will also need to install several packages. A package is a collection of [functions](#functions) written by various contributors that extend the base functionality.

[Step-by-step video](https://youtu.be/8O9d37J10YU)

> **Hint**: Use CMD+click (Mac) or CTRL+click (Windows) to open external links in another tab

1. Download & Install *R* (base package)
    - Download the appropriate version: [Mac](https://cran.r-project.org/bin/macosx/) | [Windows](https://cran.r-project.org/bin/windows/base/)
    - Run the downloaded file: Mac (`.pkg` ) | Windows (`.exe` file)

2. Download & Install *RStudio*
    - [Mac/Windows](https://rstudio.com/products/rstudio/download/#download)

3. Install necessary packages
    - Open *RStudio*
    - Locate the Console
    - At the command prompt (>), type (**case-sensitive**):

```r
install.packages(c("plyr", "reshape2", "openxlsx", "clipr", "ggplot2"))
```

4. Download [CSV](https://raw.githubusercontent.com/cdl-geneseo/r/main/data_files/phrases.csv) and [XLSX](https://github.com/cdl-geneseo/r/blob/main/data_files/negations.xlsx) files to use during workshop

> During the workshop we will also experiment with importing directly from the URLs.

## Launch & Customize *R* Studio (optional)

*RStudio* provides a powerful graphical user interface for using R. Please note that *R* must be installed for *RStudio* to work. In essence, *RStudio* is a shell that greatly facilitates working with *R*. For example, *RStudio* keeps data, scripts, and plots all organized in one environment making it easy to switch quickly between various elements.

When you open *RStudio* there will be one large window with 4 sections or window panes. The pane locations can be customized and each pane can include multiple tabs. Although the default settings work well, feel free to modify the pane layout using the following menu sequence:

 - Mac: RStudio > Preferences > Pane Layout
 - Windows: Tools > Options > Pane Layout

> Read more: [Customizing RStudio](https://support.rstudio.com/hc/en-us/articles/200549016-Customizing-RStudio)

## Console Basics

When *RStudio* first launches, the Console contains information about the version of *R* installed. It also contains the command prompt (>) with a cursor next to the prompt.

The Console is where all code is executed/implemented/run. Note that code can be typed directly into the Console, or in a separate script (i.e., a text file with a list of commands). To run code typed in a separate script (i.e., text file), code is first sent to the Console (line-by-line or all-at-once).

### A few console tricks:

 - Clear the console: CTRL + L
 - Browse previous commands: up/down arrows
 - Case-sensitive: mean(x) is different from MEAN(x)
 - Extra space ignored: mean ( x ) is functionally equivalent to mean(x)

## Testing Out the Console & Debugging

As a general principle, when using *R*, "no news is good news." That can be a little unsettling at first. Consider the following code:

```r
x = c(3,2,5,4,3)
```

In the code above, the c() function creates a list of values and we store those values in a variable called *x*. After typing the code and pressing Enter/Return, we are simply met with a blinking cursor. No response from *R*. This is a great example of "silent success." How do we know it worked? We can check, and that is very much the spirit of using *R*! I like to think of *R* as an interactive programming environment where we can ask questions about data using short commands. The trick is to learn those commands and how they work!

As a quick example, to learn about variable *x* created in the code above, we can do a few things: 1) we can simply enter the variable name to look at the data, 2) we can check on its characteristics, or 3) we can use variable *x* within another function. In the command console, try the code below (pressing Return/Enter at the end of each line) to see what happens:

```r
x = c(3,2,5,4,3)
x
View(x)
str(x)
length(x)
mean(x)
```

## Why *R*?

One time while searching the internet looking for some help on how to use a specific function in *R*, I came across a webpage with the header: "I think, therefore I *R*." I enjoy the play on words, and more important the sentiment of *thinking* about data. Popular statistical software alternatives tend to emphasize visual appearance. Although such programs provide an attractive graphical user interface with an impressive assortment of pre-definied functions, navigation often involves traversing layer upon layer of menus and pop-up windows.

While it is a natural instinct to look at data in a neat spreadsheet format and it is convenient to have pre-defined analyses and graphs, a great deal of understanding comes from the actual process of exploring data, from recurrently asking questions and receiving immediate feedback within a single environment. In this way, the process is just as (and in some cases, perhaps more) important than a result. In *R* we can quickly and easily generate statisics, creating visualizations and interact with the data in a flexible and dynamic way. In the following lessons, we will explore a number of functions that will help us to achieve those goals. Beyond these lessons, I encourage you to search for functions that are designed to produce the designed results. Along the way you will inevitably learn more about the underlying logic and ways in which functions can be customized to suit your analysis needs.