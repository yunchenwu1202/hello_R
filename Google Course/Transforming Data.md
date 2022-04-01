# Creating Data Frame

```R
id <- c(1:10)

name <-c("John Mendes", "Rob Stewart", "Rachel Abrahamson", "Christy Hickman", "Johnson Harper", "Candace Miller", "Carlson Landy", "Pansy Jordan", "Darius Berry", "Claudia Garcia")

job_title <- c("Proffational", "Programmer", "Management","Clerical","Developer", "Programmer","Management", "Clerical","Developer","Programmer")

employee <- data.frame(id , name, job_title)

print(employee)
   id              name    job_title
1   1       John Mendes Proffational
2   2       Rob Stewart   Programmer
3   3 Rachel Abrahamson   Management
4   4   Christy Hickman     Clerical
5   5    Johnson Harper    Developer
6   6    Candace Miller   Programmer
7   7     Carlson Landy   Management
8   8      Pansy Jordan     Clerical
9   9      Darius Berry    Developer
10 10    Claudia Garcia   Programmer
>
```

## separate() Function - Separeting one column into two
```R
separate(employee, name, into=c('first_name','last_name'), sep=' ')

first_name <-c("John", "Rob", "Rachel", "Christy", "Johnson", "Candace", "Carlson", "Pansy", "Darius", "Claudia")
last_name <-c("Mendes","Stewart","Abrahamson", "Hickman", "Harper", "Miller", "Landy", "Jordan", "Berry", "Garcia")
job_title <- c("Proffational", "Programmer", "Management","Clerical","Developer", "Programmer","Management", "Clerical","Developer","Programmer")

employee <- data.frame(id , first_name, last_name, job_title)

print(employee)

> print(employee)
   id first_name  last_name    job_title
1   1       John     Mendes Proffational
2   2        Rob    Stewart   Programmer
3   3     Rachel Abrahamson   Management
4   4    Christy    Hickman     Clerical
5   5    Johnson     Harper    Developer
6   6    Candace     Miller   Programmer
7   7    Carlson      Landy   Management
8   8      Pansy     Jordan     Clerical
9   9     Darius      Berry    Developer
10 10    Claudia     Garcia   Programmer
```

## unite() Function - To combine two data

```R
first_name <-c("John", "Rob", "Rachel", "Christy", "Johnson", "Candace", "Carlson", "Pansy", "Darius", "Claudia")
last_name <-c("Mendes","Stewart","Abrahamson", "Hickman", "Harper", "Miller", "Landy", "Jordan", "Berry", "Garcia")
job_title <- c("Proffational", "Programmer", "Management","Clerical","Developer", "Programmer","Management", "Clerical","Developer","Programmer")

employee <- data.frame(id , first_name, last_name, job_title)

print(employee)

unite(employee,'name',first_name, last_name, sep = ' ')

> unite(employee,'name',first_name, last_name, sep = ' ')
   id              name    job_title
1   1       John Mendes Proffational
2   2       Rob Stewart   Programmer
3   3 Rachel Abrahamson   Management
4   4   Christy Hickman     Clerical
5   5    Johnson Harper    Developer
6   6    Candace Miller   Programmer
7   7     Carlson Landy   Management
8   8      Pansy Jordan     Clerical
9   9      Darius Berry    Developer
10 10    Claudia Garcia   Programmer
```

