# Creating-scatterplot-with-ggplot-in-R-programming

### make sure to install all the packages below. 
pacman::p_load(datasets, pacman, psych, rio, tidyverse)

### Using qplot scatterplot 
qplot(Petal.Width, Petal.Length, data = iris)

### Colored by species
qplot(Petal.Width, Petal.Length, color = Species, data = iris)

### Using ggplot 
### Basic scatterplot 
ggplot(data = iris, mapping = aes(x = Petal.Width, Petal.Length)) + 
  geom_point()

### Scatterplot, jittered
ggplot(data = iris, mapping = aes(x = Petal.Width, Petal.Length)) + 
  geom_jitter()


### Scatterplot, jittered, variable size, colored by species 
ggplot(data = iris, mapping = aes(x = Petal.Width, Petal.Length,
                                  size = Sepal.Length,
                                  color = Species)) + 
                                geom_jitter(alpha = 0.5)

### Scatterplot, jittered, colored by species, and fitting a line 
ggplot(data = iris, mapping = aes(x = Petal.Width, Petal.Length,
                                  size = Sepal.Length,
                                  color = Species)) +
                              geom_point(size = 3) +
                              geom_smooth(method = lm)


### Scatterplot, jittered, colored by species, and fitting a line and density
ggplot(iris, mapping = aes(x = Petal.Width, Petal.Length, color = Species)) +
  geom_point(size = 3) +
  geom_smooth(method = lm) + 
  geom_density2d(alpha = 0.5) + 
  theme(legend.position = "bottom")
  

