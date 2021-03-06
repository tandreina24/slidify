---
title       : "Shiny: Assignment Developing Data Product"
subtitle    : "Total tweets of Famous people"
author      : "Andreina Torres"
job         : 
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---

## Total tweets App 

Try the app in the following link: https://andreinatorres.shinyapps.io/TwitterDDP/

**About the app:** This App create a histogram for the total number of tweet posted by some famous personalities.

**Data source:** The data were downladed from the following link.
https://www.kaggle.com/speckledpingu/RawTwitterFeeds

Also, A breaf data cleaning were preformed to get the format needed, the cleaning code could be found in the Github Repo.

## How use the app (Instructions)

1. Select the famous personalitity in the selection box (Author).
2. It going to appear the corresponding histograms for that person.
3. These graph are interactive.


--- .class #id 

## R expression that got evaluated (Ui.R)

To use the app please select the famous personalitity in the selection box (Author).

![](Appsidebar.png)


--- .class #id 
##  The server calculation (Server.R)

**Graph1:** "Total number of tweets by year and month"
It  performed the calculation of an histogram plot of total number of tweets for the author 
selected by month and year.

          x <- list(title = "Month and Year")
          y <- list(title = "Total number of tweets")
          data3<-data2[data2$author==input$Author,]
          plot_ly(x = ~data3$DateFinal2, type = "histogram")  %>%
          layout(xaxis = x, yaxis = y)

**Graph2:** "Total number of tweets by year"
It performed the calculation of an histogram plot of total number of tweets for the author 
selected by year.

          x <- list(title = "Year")
          y <- list(title = "Total number of tweets")
          data3<-data2[data2$author==input$Author,]
          plot_ly(x = ~year(data3$dateFinal), type = "histogram") %>%
          layout(xaxis = x, yaxis = y)


--- .class #id 
## Example Output displayed

Try the app in the following link: https://andreinatorres.shinyapps.io/TwitterDDP/

![](ApptwitterDDPexample.png)

Thank you! 
Andreina Torres
