---
title: "Shiny Web App"
authors:
- Christophe Z Guilmoto
- Alex R. Cook
- admin
tags: []
categories: []
date: "2019-05-01T00:00:00Z"
featured: false
draft: true
runtime: shiny
---
  
  ```{r include = FALSE}
library(shiny)
library(viridis)
```

You've seen the Maunga Whau volcano displayed in a variety of colors. Now pick your favorite.

```{r echo = FALSE}
selectInput("colors", "Choose a color palette", 
  choices = c("viridis", "magma", "inferno", "plasma", "heat",
  "terrain", "topographic", "cyan/magenta", "rainbow"))
colorPalette <- reactive({
  switch(input$colors, 
         "viridis" = viridis(200),
         "magma" = viridis(200, option = "A"),
         "inferno" = viridis(200, option = "B"),
         "plasma" = viridis(200, option = "C"),
         "heat" = heat.colors(200),
         "terrain" = terrain.colors(200),
         "topographic" = topo.colors(200),
         "cyan/magenta" = cm.colors(200),
         "rainbow" = rainbow(200))
})
renderPlot({
  image(volcano, col = colorPalette())
})
```
