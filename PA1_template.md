# Reproducible Research: Peer Assessment 1


## Loading and preprocessing the data
Unzip the data and load it into a data frame.

```r
unzip("activity.zip")
activity <- read.csv("activity.csv")
str(activity)
```

```
## 'data.frame':	17568 obs. of  3 variables:
##  $ steps   : int  NA NA NA NA NA NA NA NA NA NA ...
##  $ date    : Factor w/ 61 levels "2012-10-01","2012-10-02",..: 1 1 1 1 1 1 1 1 1 1 ...
##  $ interval: int  0 5 10 15 20 25 30 35 40 45 ...
```



## What is mean total number of steps taken per day?
Aggregate the data frame by day, then take the mean.

```r
steps.per.day <- aggregate(activity$steps, 
                           list(day=activity$date), sum)
hist(steps.per.day$x, 
     breaks=10, 
     main="Histogram of steps per day",
     xlab="Steps")
```

![](PA1_template_files/figure-html/unnamed-chunk-2-1.png)

###Mean

```r
mean(steps.per.day$x, na.rm=TRUE)
```

```
## [1] 10766.19
```
###Median

```r
median(steps.per.day$x, na.rm=TRUE)
```

```
## [1] 10765
```



## What is the average daily activity pattern?



## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
