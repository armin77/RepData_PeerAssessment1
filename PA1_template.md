# Reproducible Research: Peer Assessment 1

Setting locale to en_US.


## Loading and preprocessing the data


```r
data <- read.csv("activity.csv")
data$date <- strptime(data$date, format="%Y-%m-%d")
```

## What is mean total number of steps taken per day?

### Histogram showing the total number of steps taken each day
<img src="figure/histogram.png" title="plot of chunk histogram" alt="plot of chunk histogram" width="792" />

### Simple Statistics 

The mean for steps / day is __10766.19__.

The median for steps / day is __10765__.

## What is the average daily activity pattern?

<img src="figure/timeseries.png" title="plot of chunk timeseries" alt="plot of chunk timeseries" width="792" />

## Imputing missing values



## Are there differences in activity patterns between weekdays and weekends?
