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

# Number of applied for and granted patents by year 
table(pts$applyear)

head(years)
library(tidyverse)
# number of patents applied for
ggplot(years, aes(x = Var1, y = Freq))+
  geom_point()+
  geom_line()

# number of patents granted
grantYear <- data.frame((table(pts$grantyear)))
head(grantYear)

ggplot(grantYear, aes(x = Var1, y = Freq))+
  geom_point()



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

typeByyear <- table(typesubset$ptype, typesubset$applyear)
head(typeByyear)
# ^ the number of design patents applied for has increased from 2010-2016, while the number of utility patents applied for has decreased in the same time frame
