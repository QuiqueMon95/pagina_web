---
title: "Covid free"
author: "Quique Montero"
date: "2022-01-26"
excerpt: sdjndjnsdjnjnss
---


```r
library(tidyverse)
library(readxl)
```


## Pandemia Covid-19

sdnodnndoincdisndikcndinsidnio´nsindindinvidnvivnidnisdnikcnkxncxknckndsindi
sndcndncjndjncjnsidnisneiknveionviod


## shdjdbcjdb


```r
casos_cv <- read_xlsx("~/GitHub/COVID_19/data/data/base_datos_covid.xlsx") %>% 
  select(fecha, casos_cv) %>% na.omit() %>% 
  mutate(fecha = as.Date(fecha)) %>% 
  mutate(cv_rolling = zoo::rollmean(casos_cv, k = 7, fill = NA, align = "left")) 
```

```
## New names:
## * `` -> ...51
## * `` -> ...52
## * `` -> ...56
## * `` -> ...57
## * `` -> ...58
```

```r
casos_cv %>% 
  
  filter(fecha >= "2021-06-01") %>%
  ggplot(aes( x = fecha, y = casos_cv, group = 1 )) +
  
  geom_bar(stat = "identity", fill = "#f78d6e", alpha = 0.4, width = 1) +
  geom_line(aes(fecha,cv_rolling), size = 2.4, color = "#FFFFFF") +
  geom_line(aes(fecha,cv_rolling), size = 1.2, color = "#E74C3C") +
  
  geom_hline(yintercept = 0, colour = "#908982") +
  
  scale_x_date(date_breaks = "month", date_labels = "%b", expand = c(0, 0)) +
  scale_y_continuous(expand = c(0, 0)) +
  
  theme_minimal() +
  
  theme(legend.position="bottom", 
        panel.grid.major=element_blank(),
        panel.grid.minor=element_blank(),
        text=element_text(size=35, family= "Montserrat"),
        axis.text.x=element_text(size=35, hjust = -0.2,  colour = "#908982"),
        axis.text.y = element_text(size = 35, colour = "#908982"), 
        plot.title=element_text(size=50,  vjust = 1.5), 
        plot.subtitle=element_text(size=45,  vjust = 1.5),
        plot.caption = element_text(size = 35, colour = "#908982", hjust = 0),
        panel.grid.major.x = element_blank(),
        panel.grid.minor.x = element_blank(),
        axis.ticks.y = element_blank(),
        axis.ticks = element_line(linetype = "longdash", lineend = "round", colour = "#66615d")) +
  
  labs(title=bquote(bold("Nº de casos confirmados por PDIA positivas en la Comunidad Valenciana")),
       subtitle = "Casos diarios (media móvil 7 días)",
       x="", 
       y="", 
       caption ="Fuente: elaboración propia, datos de: http://coronavirus.san.gva.es/es/estadisticas                                                                                                                                              Autor: @Montero_Quique")
```

```
## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database

## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database

## Warning in grid.Call(C_stringMetric, as.graphicsAnnot(x$label)): font family not
## found in Windows font database
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database

## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database
```

```
## Warning in grid.Call.graphics(C_text, as.graphicsAnnot(x$label), x$x, x$y, :
## font family not found in Windows font database

## Warning in grid.Call.graphics(C_text, as.graphicsAnnot(x$label), x$x, x$y, :
## font family not found in Windows font database
```

```
## Warning in grid.Call(C_textBounds, as.graphicsAnnot(x$label), x$x, x$y, : font
## family not found in Windows font database
```

<img src="{{< blogdown/postref >}}index_files/figure-html/unnamed-chunk-2-1.png" width="672" />

