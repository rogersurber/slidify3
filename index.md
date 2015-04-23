---
title       : Stopping Distance for Cars
subtitle    : We Make the Drive with Your Car More Secure
author      : Roger Surber
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Disclaimer

This data examples are based on old data (year 1920) from a dataset in RStudio used for 
demonstrations' purpose only.

Do not make any driving decisions based on this data!


--- .class #id 


## Idea

We use an advanced algorithm to keep a safe distance based on:
- speed of car
- weight
- temperature of street
- incline of street
- tyres
- airpressure of tyres
- and many other real-time data

We estimate the stopping distance at any given moment
of your car ride with this real-time input. 
Combined with the device measuring the distance to the next car ahead of you 
we calculate the appropriate and safe distance to the next car any given time 
and adjust autonomously the speed at any given moment.


--- .class #id 

## At its Core (simplified)


```r
data(cars)
#Calculate the model
stoppingDistance <- function(speed) {
        fit <- lm(dist ~ speed, data = cars)
        new.speed <- data.frame(speed)
        round(predict(fit, newdata = new.speed), digits = 0)
}
#Use the speed of 15mph for the example
speed <- 15
#Estimate the stopping distance based on the model
stoppingDistance(speed)
```

```
##  1 
## 41
```

--- .class #id 

## Solution

We show you just a hint on how we use intelligent algorithms to 
determine the right variables for your safest possible journey with your car. 

As a result you get a safe distance to the car in front of you, considering the 
whole context of your current situation.

We innovate for your safety!
