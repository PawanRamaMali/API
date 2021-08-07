
# REST API in R


R allows you to develop REST APIs with the plumber package. 

You can read the official documentation at https://www.rplumber.io/ 

It’s easy to repurpose any R script file to an API with `plumber`, because you only have to decorate your functions with comments. You’ll see all about it in a bit.

## Develop a Simple REST API with R and Plumber

To start, create an empty R script file. You’ll need a couple of packages:

`plumber` – to develop the API
`dplyr` – to filter datasets based on the request body (or URL params)
`ggplot2` – for data visualization
`gapminder` – for data. That’s what you’ll use as a basis for the API.

You can place two roxigen2-like comments for specifying API title and description. These two aren’t mandatory, but you shouldn’t skip them. Here’s how the entire code snippet (imports, name, and description) looks like:

```
library(plumber)
library(dplyr)
library(ggplot2)
library(gapminder)

#* @apiTitle Gapminder API
#* @apiDescription API for exploring Gapminder dataset
```

You’re now ready to create your first endpoint.

