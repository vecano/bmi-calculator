---
title       : Calculating Body Mass Index
subtitle    : Body Mass Index (BMI) attempts to quantify an individual's tissue mass
author      : Vicente E. Cano
job         :
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      #
widgets     : [mathjax]     # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## What is the Body Mass Index

The Body Mass Index (BMI) is a value derived from the mass (weight) and height of an individual. The BMI is defined as the body mass divided by the square of the body height. The BMI is an attempt to quantify the amount of tissue mass (muscle, fat, and bone) in an individual, and then categorize that person as underweight, normal weight, overweight, or obese based on that value. [1]

The equation (where weight is measured in pounds and height is measured in inches) is described as:

$$BMI = {703 \times {weight} \over {height^2}}.$$

### References

1. [Wikipedia's Body Mass Index Article](https://en.wikipedia.org/wiki/Body_mass_index)

---

## BMI Categories

The BMI of an individual can grouped into categories based on the height and weight of that individual when entered into the BMI equation. These categories are:

* Very severely underweight: < 15.0
* Severely underweight: 15 – 15.9
* Underweight: 16 – 18.49
* Normal weight: 18.5 – 24.9
* Overweight: 25 – 29.9
* Obese Class I (Moderately obese): 30 – 34.9
* Obese Class II (Severely obese): 35 – 39.9
* Obese Class III (Very severely obese): 40 or greater

---

## Examples

An individual whose height is 5'11" and weight is 155 pounds would be under a normal weight:


```r
bmi <- function(height, weight) {
  return(703 * weight / height^2)
}

bmi(71, 155)
```

```
## [1] 21.61575
```

But if that same individual where to increase its weight to 200 pounds, he would be in the overweight category:


```r
bmi(71, 200)
```

```
## [1] 27.89129
```

---

## Online Application and Limitations

### Online Application

I have created a `shinyapp` for calculating the BMI of an individual. It can be found at [BMI Calculator](https://vecano.shinyapps.io/bmi-application/). This application contains two slider bars to enter the height and weight of an individual and provides the BMI based on these parameters.

### Limitations

BMI is useful because it is a simple way to assess the health of an individual but it has certain limitations, some examples are:

* It does not take into account variation in physical characteristics. It adds roughly 10% for a large (or tall) frame and subtracts roughly 10% for a smaller frame (short stature).
* It does not differentiate between muscle mass and fat mass. BMI is particularly inaccurate for people who are very fit or athletic, as their high muscle mass can classify them in the overweight category by BMI.
