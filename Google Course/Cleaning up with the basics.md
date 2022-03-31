
Package to download for cleaning:
dplyr
skimr
janitor
here

## head() Function - the first rows. 

> install.packages("palmerpenguins")
> library("palmerpenguins")

## skim_without_charts() Function - view data summary
```R
> skim_without_charts(penguins)
── Data Summary ────────────────────────
                           Values  
Name                       penguins
Number of rows             344     
Number of columns          8       
_______________________            
Column type frequency:             
  factor                   3       
  numeric                  5       
________________________           
Group variables            None    

── Variable type: factor ───────────────────────────────────────────────────────
  skim_variable n_missing complete_rate ordered n_unique
1 species               0         1     FALSE          3
2 island                0         1     FALSE          3
3 sex                  11         0.968 FALSE          2
  top_counts                 
1 Ade: 152, Gen: 124, Chi: 68
2 Bis: 168, Dre: 124, Tor: 52
3 mal: 168, fem: 165         

── Variable type: numeric ──────────────────────────────────────────────────────
  skim_variable     n_missing complete_rate   mean      sd     p0    p25    p50
1 bill_length_mm            2         0.994   43.9   5.46    32.1   39.2   44.4
2 bill_depth_mm             2         0.994   17.2   1.97    13.1   15.6   17.3
3 flipper_length_mm         2         0.994  201.   14.1    172    190    197  
4 body_mass_g               2         0.994 4202.  802.    2700   3550   4050  
5 year                      0         1     2008.    0.818 2007   2007   2008  
     p75   p100
1   48.5   59.6
2   18.7   21.5
3  213    231  
4 4750   6300  
5 2009   2009
```

## glimpse() Function - view a part of the data
```R
> glimpse(penguins)
Rows: 344
Columns: 8
$ species           <fct> Adelie, Adelie, Adelie, Adelie, Adelie, Adelie, Adel…
$ island            <fct> Torgersen, Torgersen, Torgersen, Torgersen, Torgerse…
$ bill_length_mm    <dbl> 39.1, 39.5, 40.3, NA, 36.7, 39.3, 38.9, 39.2, 34.1, …
$ bill_depth_mm     <dbl> 18.7, 17.4, 18.0, NA, 19.3, 20.6, 17.8, 19.6, 18.1, …
$ flipper_length_mm <int> 181, 186, 195, NA, 193, 190, 181, 195, 193, 190, 186…
$ body_mass_g       <int> 3750, 3800, 3250, NA, 3450, 3650, 3625, 4675, 3475, …
$ sex               <fct> male, female, female, NA, female, male, female, male…
$ year              <int> 2007, 2007, 2007, 2007, 2007, 2007, 2007, 2007, 2007…
```
## head() Function - view the first few rows of the data
```R
> head(penguins)
# A tibble: 6 × 8
  species island bill_length_mm bill_depth_mm flipper_length_… body_mass_g sex  
  <fct>   <fct>           <dbl>         <dbl>            <int>       <int> <fct>
1 Adelie  Torge…           39.1          18.7              181        3750 male 
2 Adelie  Torge…           39.5          17.4              186        3800 fema…
3 Adelie  Torge…           40.3          18                195        3250 fema…
4 Adelie  Torge…           NA            NA                 NA          NA NA   
5 Adelie  Torge…           36.7          19.3              193        3450 fema…
6 Adelie  Torge…           39.3          20.6              190        3650 male 
# … with 1 more variable: year <int>
```

## select() Function - select certain data
```R
> penguins %>%
+   select(-species)
# A tibble: 344 × 7
   island  bill_length_mm bill_depth_mm flipper_length_… body_mass_g sex    year
   <fct>            <dbl>         <dbl>            <int>       <int> <fct> <int>
 1 Torger…           39.1          18.7              181        3750 male   2007
 2 Torger…           39.5          17.4              186        3800 fema…  2007
 3 Torger…           40.3          18                195        3250 fema…  2007
 4 Torger…           NA            NA                 NA          NA NA     2007
 5 Torger…           36.7          19.3              193        3450 fema…  2007
 6 Torger…           39.3          20.6              190        3650 male   2007
 7 Torger…           38.9          17.8              181        3625 fema…  2007
 8 Torger…           39.2          19.6              195        4675 male   2007
 9 Torger…           34.1          18.1              193        3475 NA     2007
10 Torger…           42            20.2              190        4250 NA     2007
# … with 334 more rows
```
## rename() Function - rename column
```R
> penguins %>%
+   rename(island_new=island)
# A tibble: 344 × 8
   species island_new bill_length_mm bill_depth_mm flipper_length_mm body_mass_g
   <fct>   <fct>               <dbl>         <dbl>             <int>       <int>
 1 Adelie  Torgersen            39.1          18.7               181        3750
 2 Adelie  Torgersen            39.5          17.4               186        3800
 3 Adelie  Torgersen            40.3          18                 195        3250
 4 Adelie  Torgersen            NA            NA                  NA          NA
 5 Adelie  Torgersen            36.7          19.3               193        3450
 6 Adelie  Torgersen            39.3          20.6               190        3650
 7 Adelie  Torgersen            38.9          17.8               181        3625
 8 Adelie  Torgersen            39.2          19.6               195        4675
 9 Adelie  Torgersen            34.1          18.1               193        3475
10 Adelie  Torgersen            42            20.2               190        4250
# … with 334 more rows, and 2 more variables: sex <fct>, year <int>
```

## rename_with() Function - change column to upper case or lower case
```R
> rename_with(penguins,toupper)
# A tibble: 344 × 8
   SPECIES ISLAND    BILL_LENGTH_MM BILL_DEPTH_MM FLIPPER_LENGTH_MM BODY_MASS_G
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
# … with 334 more rows, and 2 more variables: SEX <fct>, YEAR <int>

> rename_with(penguins,tolower)
# A tibble: 344 × 8
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
# … with 334 more rows, and 2 more variables: sex <fct>, year <int>
```

## clean_names() Function - ensure theres only characters, numbers and undercore in names
