## ggplot() Function

Geom (R) - The geometric object used to represent your data. 

Mapping (R) - Mathcing up a specific variable in your dataset with a specific aesthetic. 

## Getting Started with ggplot
1. Start with the ggplot function and choose a dataset to work with. 
```R
ggplot(data=penguins)
```
2. Add a geom_ function to display your data.
```R
 +geom_point()
```
3. Map the variables you want to plot in the arguments of the aes() function.
```R
mapping=aes(x=flipper_length_mm, y=body_mass_g)
```
You will get...
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g))
```
![palmerpenguin](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/plot.png)

## Reusing the plot 

```R
ggplot(data=<DATA>) + <GEOM_FUNCTION>(mapping=aes(<AESTHETICS MAPPINGS>))
```

## Adding color to the plot

```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g, color=species))
```
![Adding_colour](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/d1b23cf5-bfcc-44c3-b79a-60c3d1079531.png)

## Adding shape to the plot
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g, shape=species))
```
![Adding shape](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/00e3f5d1-aca3-4429-8d19-b473df584d0f.png)


## Adding both shape and color to the plot
```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g, shape=species,color=species))
```
![Adding shape and color](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/cfb93abd-19c0-4d9c-a9db-865b746b8ce1.png)


## Adding shape, color and size to the plot

```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g, shape=species,color=species, size= species))
```
![Adding shape size color](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/5d8fbc02-c4d4-45ce-a775-f353b0f554a1.png)

## Adding Alpha

```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g, alpha=species))
```
![Adding alpha](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/c7901e16-79b0-4c34-8412-f36147a2fff6.png)

## Adding specific color

```R
library("ggplot2")
library("palmerpenguins")

ggplot(data=penguins) +
  geom_point(mapping=aes(x=flipper_length_mm, y=body_mass_g, color='pink'))
```
![Adding alpha](https://github.com/yunchenwu1202/hello_R/blob/main/Google%20Course/4cfd7bdc-a71f-49b5-9ca4-98ca1ab97d81.png)








