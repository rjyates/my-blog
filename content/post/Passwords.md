---
date: "2020-12-07"
title: Paswords
---
THE DATA
```{r}
passwords <- readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-01-14/passwords.csv')
passwords
```

rank = popularity in their database of released passwords

password = Actual text of the password

category = What category does the password fall in to?

value	=	Time to crack by online guessing

time_unit = Time unit to match with value

offline_crack_sec = Time to crack offline in seconds

rank_alt = Rank 2

strength = quality of password where 10 is highest, 1 is lowest, please note that these are relative to these generally bad passwords

font_size = Used to create the graphic for KIB

CATEGORY OF PASSWORD v.s. PASSWORD STRENGTH
```{r}

df <- data.frame(readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-01-14/passwords.csv'))
head(df)

library(ggplot2)

p<-ggplot(data=df, aes(x=category, y=strength)) +
  geom_bar(stat="identity")
p + coord_flip()

p
```


PASSWORD STRENGTH v.s. HOW LONG IT TOOK TO CRACK OFFLINE IN SECONDS
```{r}
df <- data.frame(readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-01-14/passwords.csv'))
head(df)

library(ggplot2)

 ggplot(data=df, aes(x=strength, y=offline_crack_sec, group=1)) +
   geom_line()+
   geom_point()

```


STRENGTH OF PASSWORD v.s. HOW LONG IT TOOK TO CRACK OFFLINE IN SECONDS
```{r}
df <- data.frame(readr::read_csv('https://raw.githubusercontent.com/rfordatascience/tidytuesday/master/data/2020/2020-01-14/passwords.csv'))
head(df)

library(ggplot2)

p<-ggplot(data=df, aes(x=category, y=offline_crack_sec)) +
  geom_bar(stat="identity")
p + coord_flip()
```
