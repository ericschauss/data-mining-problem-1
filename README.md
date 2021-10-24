# data-mining-problem-1
library(dplyr)
patents <- read.csv("patents_11 (1).csv")
head(patents)
colnames(patents)
pts = subset(patents, select = -c(X))
head(pts)
# Count how many patents by each country
table(pts$ee_country)
countriesWithpatents <- table(pts$ee_country)
sort(countriesWithpatents, decreasing = TRUE)
head(pts)

# Number of patents by year 
table(pts$applyear)

head(years)
library(tidyverse)
ggplot(years, aes(x = Var1, y = Freq))+
  geom_point()+
  geom_line()


# company names
table(pts$ee_name)
names <- table(pts$ee_name)
names <- sort(names, decreasing = TRUE)
head(names)


#different types of patents
ptypes <- table(pts$ptype)
ptypes <- sort (ptypes, decreasing = TRUE)
head(ptypes)

# different types of patents filed by year 2010-2016
sapply(pts, class)
typesubset <- pts[pts$applyear>"2009",]
typesubset <- typesubset[typesubset$applyear< "2017",]
head(typesubset)
max(typesubset$applyear, na.rm = TRUE)
min(typesubset$applyear, na.rm = TRUE)
