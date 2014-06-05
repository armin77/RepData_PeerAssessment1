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

The median for steps / day is __10765.00__.

## What is the average daily activity pattern?

<img src="figure/timeseries.png" title="plot of chunk timeseries" alt="plot of chunk timeseries" width="792" />

## Imputing missing values

There are __2304__ values missing in the original dataset.

We create a new copy of that dataset and impute the missing values from the corresponding 5min interval average.


```r
newdata <- data

for(i in seq(1, nrow(data)) ) {
    if ( is.na(data$steps[i]) ) {
        newdata$steps[i] <- averagePerInterval[[as.character(data$interval[i])]]
    }
}
```

### Resulting histogram with imputed data
### Histogram showing the total number of steps taken each day
<img src="figure/histogram_2.png" title="plot of chunk histogram_2" alt="plot of chunk histogram_2" width="792" />

### Simple Statistics for new dataset

The new mean for steps / day is __10766.19__.

The new median for steps / day is __10766.19__.

Both values are now identical.
With the original dataset the median was a tiny bit lower than the mean.

## Are there differences in activity patterns between weekdays and weekends?
