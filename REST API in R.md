
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

## Endpoint 1 – /countries

The idea behind this endpoint is that it should return countries and their respective data after a couple of filters are applied. 
To be more precise, this endpoint accepts parameter values for continent, life expectancy, and population. Value for continent must be exact, and values for the other two parameters filter data so that only rows with greater values are returned.

If you want to do things right, it’ll require many comments, as you’ve seen previously. It’s a good practice to write a short description, list the parameters, and it’s mandatory to specify the request type and the endpoint.

Below the comments, you’ll place a function that performs the necessary logic and returns the results.

Let’s think about the parameters for a second. You’ll need:

* continent – column continent
* life expectancy – column lifeExp
* population – column pop
All three are mandatory, and you can do the filtering based on the parameter values with the dplyr package. This endpoint will return data for the most recent year only, which is 2007.

Here’s the complete logic behind /countries endpoint:

```

#* Returns countries that satisfy condition
#* @param in_continent
#* @param in_lifeExpGT Life expectancy greater than
#* @param in_popGT Population greater than
#* @get /countries
function(in_continent, in_lifeExpGT, in_popGT) {
  gapminder %>%
    filter(
      year == 2007,
      continent == in_continent,
      lifeExp > in_lifeExpGT,
      pop > in_popGT
    )
}
```

If you were to run the API now, this is what you’d see:

![image](https://user-images.githubusercontent.com/11299574/128609658-fb399363-9a6d-4fa3-9854-18b60409b03b.png)
Image 1 – API documentations page

The endpoint on the bottom of the image (blue box) is clickable. Clicking on it expands a whole another section:

![image](https://user-images.githubusercontent.com/11299574/128609687-d451dce6-c6e6-4ca6-9370-089f820d4893.png)
Image 2 – Documentation for the /countries endpoint

You can click on the “Try it out” button to make a request straight from the browser. You’ll have to fill in the parameter values then; let’s say like this:

![image](https://user-images.githubusercontent.com/11299574/128609695-a0ebbae4-8fde-474f-bf89-9b3a2026ef2d.png)
Image 3 – Testing out /countries endpoint

Once you click on the “Execute” button, the response will show below. Here’s how it looks like in this case:

![image](https://user-images.githubusercontent.com/11299574/128609706-8ab45237-d9e3-4e94-9a7f-9844fb46d960.png)
Image 4 – /countries endpoint example response

And that’s your first endpoint! It takes data in and returns data out. But what if you want to return something else? Like an image, for example. You’ll learn how to do that next.



```
```
### Credits : 
* Dario Radečić , Posted on Appsilon, dated 13 January, 2021 
* Maria Grycuk, Project Manager at Appsilon 
