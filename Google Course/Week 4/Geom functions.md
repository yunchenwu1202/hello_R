## geom_smooth

```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_smooth(mapping=aes(x=flipper_length_mm, y=body_mass_g))
```
![geom_smooth](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/584f9435-7245-4825-92ec-8eef29399311.png)

## geom_smooth + geom_point
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_smooth(mapping=aes(x=flipper_length_mm, y=body_mass_g)) + 
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g))
  
```
![geom_smooth](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/74df5824-1fe0-4cc1-b3aa-cb0a687f3ca5.png)

## geom_smooth with linetype
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_smooth(mapping=aes(x=flipper_length_mm, y=body_mass_g)) + 
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g))

ggplot(data=penguins)+
  geom_smooth(mapping=aes(x=flipper_length_mm,y=body_mass_g,linetype=species))
  
```
![geom_smooth with linetype](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/bb9725e9-15d5-4521-9053-d157e7851ee6.png)

## geom_jitter
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_smooth(mapping=aes(x=flipper_length_mm, y=body_mass_g)) + 
  geom_jitter(mapping=aes(x=flipper_length_mm, y=body_mass_g))
  
```
![geom_jitter](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/0b323c59-cdb1-4b80-b371-862599cc83c0.png)

## geom_bar
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_bar(mapping=aes(x=body_mass_g)) 
```
![geom_bar](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/ff945866-e977-4c4d-99d2-23b0793231a4.png)











