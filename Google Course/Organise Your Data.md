
## arrange() Function - sorting data in asending order
```R
> penguins %>%
+   arrange(bill_length_mm)
# A tibble: 344 × 8
   species island    bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
   <fct>   <fct>              <dbl>         <dbl>             <int>       <int>
 1 Adelie  Dream               32.1          15.5               188        3050
 2 Adelie  Dream               33.1          16.1               178        2900
 3 Adelie  Torgersen           33.5          19                 190        3600
 4 Adelie  Dream               34            17.1               185        3400
 5 Adelie  Torgersen           34.1          18.1               193        3475
 6 Adelie  Torgersen           34.4          18.4               184        3325
 7 Adelie  Biscoe              34.5          18.1               187        2900
 8 Adelie  Torgersen           34.6          21.1               198        4400
 9 Adelie  Torgersen           34.6          17.2               189        3200
10 Adelie  Biscoe              35            17.9               190        3450
# … with 334 more rows, and 2 more variables: sex <fct>, year <int>
```

## arrange(-) Function - sorting data in descending order
```R
> penguins %>%
+   arrange(-bill_length_mm)
# A tibble: 344 × 8
   species   island bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
   <fct>     <fct>           <dbl>         <dbl>             <int>       <int>
 1 Gentoo    Biscoe           59.6          17                 230        6050
 2 Chinstrap Dream            58            17.8               181        3700
 3 Gentoo    Biscoe           55.9          17                 228        5600
 4 Chinstrap Dream            55.8          19.8               207        4000
 5 Gentoo    Biscoe           55.1          16                 230        5850
 6 Gentoo    Biscoe           54.3          15.7               231        5650
 7 Chinstrap Dream            54.2          20.8               201        4300
 8 Chinstrap Dream            53.5          19.9               205        4500
 9 Gentoo    Biscoe           53.4          15.8               219        5500
10 Chinstrap Dream            52.8          20                 205        4550
# … with 334 more rows, and 2 more variables: sex <fct>, year <int>
```
## Saving results as new table
```R
> penguins2 <- penguins %>% arrange(-bill_length_mm)
> View(penguins2)
```

## group_by() Function - 
## drop_na() Function - remove null
```R
> penguins %>% group_by(island) %>% drop_na() %>% summarize(mean_bill_length_mm = mean(bill_length_mm))
# A tibble: 3 × 2
  island    mean_bill_length_mm
  <fct>                   <dbl>
1 Biscoe                   45.2
2 Dream                    44.2
3 Torgersen                39.0
```
## max() Function -  
```R
> penguins %>% group_by(island) %>% drop_na() %>% summarize(max_bill_length_mm = max(bill_length_mm))
# A tibble: 3 × 2
  island    max_bill_length_mm
  <fct>                  <dbl>
1 Biscoe                  59.6
2 Dream                   58  
3 Torgersen               46  
```

###### putting mean and max together
```R
> penguins %>% group_by(species, island) %>% drop_na() %>% summarize(max_b1 = max(bill_length_mm), mean_b1 = mean (bill_length_mm))
`summarise()` has grouped output by 'species'. You can override using the
`.groups` argument.
# A tibble: 5 × 4
# Groups:   species [3]
  species   island    max_b1 mean_b1
  <fct>     <fct>      <dbl>   <dbl>
1 Adelie    Biscoe      45.6    39.0
2 Adelie    Dream       44.1    38.5
3 Adelie    Torgersen   46      39.0
4 Chinstrap Dream       58      48.8
5 Gentoo    Biscoe      59.6    47.6
```

## filter() Function - contains only data in specific area
```R
> penguins %>% filter(species == "Adelie")
# A tibble: 152 × 8
   species island    bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
   <fct>   <fct>              <dbl>         <dbl>             <int>       <int>
 1 Adelie  Torgersen           39.1          18.7               181        3750
 2 Adelie  Torgersen           39.5          17.4               186        3800
 3 Adelie  Torgersen           40.3          18                 195        3250
 4 Adelie  Torgersen           NA            NA                  NA          NA
 5 Adelie  Torgersen           36.7          19.3               193        3450
 6 Adelie  Torgersen           39.3          20.6               190        3650
 7 Adelie  Torgersen           38.9          17.8               181        3625
 8 Adelie  Torgersen           39.2          19.6               195        4675
 9 Adelie  Torgersen           34.1          18.1               193        3475
10 Adelie  Torgersen           42            20.2               190        4250
# … with 142 more rows, and 2 more variables: sex <fct>, year <int>
> 
```
