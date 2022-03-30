
```R
data("ToothGrowth")

View(ToothGrowth)
# R is case sensitive
# usually it will appear in the console, but with view it will show in the script of contents of the datasets.


>install.package(dplyr)
>librbary(dplyr)

filtered_tg <- filter(ToothGrowth, dose==0.5)
View(filtered_tg)

arrange(filtered_tg,len)

# Nested
arrange(filter(ToothGrowth, dose==0.5,) len)

# %>% Pipe
filtered_toothgrowth <- ToothGrowth %>%
  filter(dose==0.5) %>%
  arrange(len)
  
# Pipe
filtered_toothgrowth <- ToothGrowth %>%
  filter(dose==0.5) %>%
  group_by(supp) %>%
  summarise(mean_len = mean(len,na.rm = T), group="drop")
```
