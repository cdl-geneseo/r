# 1. Getting Started

## Setting ourselves up

To prepare for the workshop, we recommend installing both *R* and *R* Studio ([Step-by-step video](video1)). You will also need to install several packages. A package is a collection of functions written by various contributors that extend the base functionality.

> **Hint**: Use CMD+click (Mac) or CTRL+click (Windows) to open external links in another tab

1. Download & Install *R* (base package)
    - Download the appropriate version: [Mac](https://cran.r-project.org/bin/macosx/) | [Windows](https://cran.r-project.org/bin/windows/base/)
    - Run the downloaded file: Mac (`.pkg` ) | Windows (`.exe` file)

2. Download & Install *R* Studio
    - [Mac/Windows](https://rstudio.com/products/rstudio/download/#download)

3. Install necessary packages ([Step-by-step video](video2))
    - Open *R* Studio
    - Locate the Console
    - At the command prompt (>), type (**case-sensitive**):
```r
install.packages(c("plyr", "reshape2", "openxlsx", "clipr", "ggplot2", "ggwordcloud"))
```

4. Download [CSV](file1) and [XLSX](file2) files to use during workshop
