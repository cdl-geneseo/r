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

4. Download [CSV](file1) and [XLSX](file2) files to use during workshop

> During the workshop we will also experiment with importing directly from the URLs.

## Launch & Customize (optional) *R* Studio

*RStudio* provides a powerful graphical user interface for using R. Please note that *R* must be installed for *RStudio* to work. In essence, *RStudio* is a shell that greatly facilitates working with *R*. For example, *RStudio* keeps data, scripts, and plots all organized in one environment making it easy to switch quickly between various elements.

When you open *RStudio* there will be one large window with 4 sections or window panes. The pane locations can be customized and each pane can include multiple tabs. Although the default settings work well, feel free to modify the pane layout using the following menu sequence:

 - Mac: RStudio > Preferences > Pane Layout
 - Windows: Tools > Options > Pane Layout

> Read more: [Customizing RStudio](https://support.rstudio.com/hc/en-us/articles/200549016-Customizing-RStudio)

## Console Basics

When *RStudio* first launches, the Console contains information about the version of *R* installed. It also contains the command prompt (>) with a cursor next to the prompt.

The Console is where all code is executed/implemented/run. Note that code can be typed directly into the Console, or in a separate script (i.e., a text file with a list of commands). To run code typed in a separate script (i.e., text file), code is first sent to the Console (line-by-line or all-at-once).

 - Clear the console: CTRL + L
 - Browse previous commands: up/down arrows
 - Case-sensitive: mean(x) is different from MEAN(x)
 - Extra space ignored: mean ( x ) is functionally equivalent to mean(x)

## Testing the Console

To confirm that the Console is working, try the following (pressing Enter/Return to run the code):

```r
2 + 2
```

## Debugging

As a general principle, when using *R*, "no news is good news." That can be a little unsettling at first.