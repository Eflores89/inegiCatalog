# inegiCatalog
Catalog of INEGI indicators. It is an extension to the [inegiR](https://github.com/Eflores89/inegiR) package, making it easier to find the data you want.

# Install
```
library(devtools)
install_github("Eflores89/inegiCatalog")
```

# Usage
```
library(dplyr)
library(inegiR)
data("inegi_catalog")

# to ilustrate the hierarchy
ind <- inegi_catalog %>% 
  filter(AVAILABLE == 1) %>%
  filter(ENT_CODE == "00") %>% 
  filter(LEVEL1 == "Población, Hogares y Vivienda") %>% 
  filter(LEVEL2 == "Natalidad y fecundidad") %>% 
  filter(LEVEL3 == "Natalidad") %>% 
  filter(DESC == "Nacimientos")

# download this indicator from INEGI  
api_token <- "[xxx]" # api token
df <- serie_inegi(serie = as.character(ind$R_URL), 
                  token = api_token, 
                  metadata = TRUE)

# or you can use the english version: inegi_series() since v2.0
```


## Updated: 2016-08-03

