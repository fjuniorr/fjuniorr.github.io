---
layout: post
title:  "Exploratory Data Analysis"
date:   2014-06-10 23:47:00
categories: notes
---

Exploratory Data Analysis
========================================================

This notes were produced to apply the skills obtained in the Exploratory Data Analysis course of the Data Science Specialization offered by Coursera and John Hopkins University.

### 1. Plotting a graph without x-axis and adding a labeled one after


```r
x <- rnorm(100)
plot(x, xaxt="n")

axis(side=1, 
     at=seq(from=0, to=100, by=25), 
     labels=c("0","Q1", "Q2", "Q3", "100"))
```

![plot of chunk unnamed-chunk-1](/figure/2014-06-09-exploratory-data-analysis-01.png) 

### 2. Plotting groups with different colors and legend


```r
group <- rep(x=c("male", "female"), each=50)
x <- rnorm(100)
y <- rnorm(100)

plot(x, y, type="n")

points(x[group=="male"], y[group=="male"], col="blue", pch=19)
points(x[group=="female"], y[group=="female"], col="red", pch=19)

legend("topleft", legend=c("male", "female"), col=c("blue", "red"), pch=19)
```

![plot of chunk unnamed-chunk-2](/figure/2014-06-09-exploratory-data-analysis-02.png) 

### 3. Plotting a regression line


```r
x <- rnorm(100)
y <- 2 + 3*x + rnorm(100)

plot(x, y)
model <- lm(y ~ x)

abline(reg=model, col="red") # estimated relationship
abline(a=2, b=3, col="blue") # true relationship
```

![plot of chunk unnamed-chunk-3](/figure/2014-06-09-exploratory-data-analysis-03.png) 

### 4. Putting a label in a specific point




