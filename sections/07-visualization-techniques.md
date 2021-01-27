↻ [Lessons](../README.md#lessons)&nbsp;&nbsp;&nbsp;|&nbsp;&nbsp;&nbsp;← [6. Merging, Filtering & Aggregating](06-merging-filtering-aggregating-data.md)

# 7. Visualization Techniques

Saving the best for last, visualization! When I first learned about statistics, creating a graph was something done only after all the statistics (e.g., *correlations*, *t-tests*, *ANOVAs*) were computed and it was time to complete the results section of a report. I would then dutifully select the most appropriate graph from the preset menu options (e.g., *scatterplot*, *barplot*, *lineplot*). Graphs were generally time-consuming to generate, especially in a publication-ready form, with countless fiddly details that left me thinking more about font and label choices than the actual data!

When I discovered that *R* makes it simple to use powerful and incredibly flexibile visualization tools, all of that changed. Many of my data analysis projects now *begin* with visualization. In my psychology of language experiments, for example, I will often collect response time data (i.e., how quickly participants press a button in response to presented stimuli). Although it is tempting to jump right into computing descriptive statistics to find out out if our manipulation worked, I've learned that first looking at the data can be informative and save some trouble further along in the analysis. One of the most basic reasons to visualize the data is check the data integrity. How are the data distributed? Are there errors? Were some responses abnormally fast/slow? A picture is worth a 1,000 words, and can help to develop a rich understanding of the data throughout the data exploration process.


### Plotting functions

The standard *plot()* function is included in the base *R* package and can be used to make quick plots or can be refined to produce professional graphs that are publication ready. If **plot()** is awesome, then **ggplot2** is turbo-charged! Some regard the **ggplot2** package (and associated functions) as a graphing language, that has it's own syntax, and allows us to build visualizations in layers, which means that if we can imagine it, we can create it!

In this lesson, we will only scratch the surface. *R* has extensive visualization capabilities, including the ability to create interative plots where the plot changes dynamically in response to user input.

### Additional resources

[Quick R](http://www.statmethods.net)
[R Tutorial](http://www.r-tutor.com)
[DataCamp](https://www.datacamp.com)
[Cookbook for R](http://www.cookbook-r.com/Graphs)
[stackoverflow](http://stackoverflow.com)