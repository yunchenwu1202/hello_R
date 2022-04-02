## bias() Function - To check rather the data is accurate

```R
>library(SimDesign)

> actual_temp <-c(68.3, 70, 72.4, 71, 67, 70)
> predicted_temp <-c(67.9,69,71.5, 70, 67, 69)
> bias(actual_temp, predicted_temp)
[1] 0.7166667
```
