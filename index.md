---
title       : My First Shiny App
subtitle    : BMI Calculator
author      : James Oliver
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## My Shiny App

My application takes input from you and creates a BMI score.
This is calculated based on 

1. Your Weight
2. Your Height

These values are matched against a dataframe within the application and returns a BMI score.
This score is the classified into the typical categories for BMI.

--- .class #id 

## Future Developments

This is a basic application at present and is very similar to many existing webpages.  
However it will do 2 things in the future:

1.  It will advise you on the amount of weight that you need to gain or lose in order to achieve a healthy BMI.
2.  It will plot your BMI against BMI measures to show how close you are to being healthy.

---
##  Development Plan 1: Weight to Gain or Lose

Based on the values you have entered, the following R code will calculate how much weight you need to gain or lose to enter the healthy bracket.
The input will be called amount of weight you need to lose.  Negative values are therfore weight you should gain.




```r
consequences<- function(ht,wt){
        bmi<-df[which.min(abs(x-ht)),which.min(abs(y-wt))]
        if(bmi>25) {
       val<-wt-y[max(grep(24,df[which.min(abs(x-ht)),]))]
                } else if(bmi<19){
                        val<-wt-y[max(grep(18,df[which.min(abs(x-ht)),]))]
                } else val<-c("You are Healthy.  You're doing great and don't need to lose weight")
                val
}
```

---
## Example Output from Development One

The function in the previous slide will calculate a range of values to advise the user wheteher they need to gain, lose or maintain weight.
Below are example outputs on some height and weight combinations.

```r
consequences(ht=166,wt=100)
```

```
## [1] -10
```

```r
consequences(ht=166,wt=150)
```

```
## [1] "You are Healthy.  You're doing great and don't need to lose weight"
```

```r
consequences(ht=160,wt=160)
```

```
## [1] 20
```


