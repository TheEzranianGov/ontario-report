# Notes from R lesson on Jan 26, 2026
# Goals: Learn how to plot in R with ggplot

# load packages
install.packages("tidyverse")

library(tidyverse)

#load data
sample_data <- read_csv("sample_data.csv")
round(3.14159, 3)

#Plot
ggplot(data = sample_data) + 
  aes(x = temperature, y = cells_per_ml, 
      color = env_group, 
      size = chlorophyll) +
  labs(x = "Temperature (C)", 
       y = "Calls per mL", 
       title = "Does Temperature affect microbial abundance?", 
       color = "Environmental Group", 
       size = "Chlorophyll (ug/L)") +
  geom_point()

# Load in new data
buoy_data <- read_csv("buoy_data.csv")
dim(buoy_data) # <-- this tells you the number of rows, columns
head(buoy_data)

ggplot(data = buoy_data) +
  aes(x = day_of_year, 
      y = temperature, 
      color = depth, 
      #group = sensor
      ) +
  geom_line() + 
  facet_wrap(~buoy)

# What is the structure of the data?
str(buoy_data)

# Let's go back to sample data
ggplot(data = sample_data) +
  # x-axis that is discrete: categorical
  aes(x = env_group, y = cells_per_ml,
       fill = env_group) +
  geom_jitter(aes(size = chlorophyll),
              shape = 23, alpha = 0.5) +
  geom_boxplot(alpha = 0.2, outliers = FALSE) + 
  scale_color_brewer(palette = "Set1") +
  scale_fill_brewer(palette = "Set1")

ggplot(sample_data) +
  aes(x = cells_per_ml) +
  geom_histogram(bins = 20) +
  theme_minimal()

# Saving plots
ggsave("histogram_cellsPerML.png",
       width = 6, height = 4, units = "in")

ggplot(sample_data) +
  aes(x = chlorophyll, y = temperature, color = cells_per_ml, size = 25) +
  labs(x = "Chlorophyll Conc.", y = "Temperature", 
       title = "Chlorophyll Concentration vs Temperature") +
  geom_point() +
  geom_smooth(size = 2, color = "red")
  
