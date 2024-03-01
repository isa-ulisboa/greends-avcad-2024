# Analysis and Visualization of Complex Data
---
## Exercise 02 - Best charts to represent different data or dataset types.

Each type of data or datasets is best visualized by certain kinds of charts, depending on both the targeted audience as well as the personal preferences of the data visualizer. In this exercise you will first simulate different types of data and datasets in python. Randomizations are usefull to understand certain statistical concepts and also as a basis for random sampling, which may be required when dealing with big data. Based on these simulated data, the exercise will consist on choosing the type of chart that you find more adequate to represent the different types of data and datasets.

The objectives of this exercise are to:
1. identify each type of variables and tables that were created.

2. try your best to interpret each line of the code provided by inserting a note in front of each line (it might be usefull to create a jupiter notebook from the markdown file)

2. based on these simulated data, draw sketches of the charts that you find more adequate to represent the different types of data and datasets. You should identify the different axis of the plot, if applicable.

You will use two modules that provide pseudo-random number generators to implement random sampling routines. Have a look [here](https://docs.python.org/3/library/random.html) (random module) and [here](https://numpy.org/doc/stable/reference/random/index.html) (numpy.random module). Both allow to simulate data and take random samples, although np.random allows more pseudo-random generator methods to be implemented.

To run the simulations, you should first import pandas, numpy and random modules (in case you still did not installed these modules, you will need to install beforehand).

```
import pandas as pd
import numpy as np
import random

# Simulate var1
var1 = []
random.seed(24) # optional: used to fix the seed of the pseudo-random number generator (use any number of your choice)
levels = ["Permanent crops", "Irrigated crops", "Managed Forest", "Natural Forest", "Agro-Forestry system", "Urban", "Pasture", "Shrubland" ]
for _ in range(100): # why is a loop needed?
    var1 += random.sample(levels, 1) # var1.append(random.sample(levels, 1)) would also work

# Simulate var2
np.random.seed(24) # optional: used to fix the seed of the pseudo-random number generator (use any number of your choice)
var2 = np.random.uniform(0, 100, 100)

# Simulate table1
table1 = pd.DataFrame(var1).value_counts(sort=True)
table1 = table1.rename_axis("landuse")
table1 = table1.reset_index(name="Frequency")

# Simulate table2
table2 = pd.DataFrame(list(zip(var1, var2)), columns = ["landuse", "cover"])

# Note: The zip() function returns a zip object, which is an iterator of tuples where the first item in each passed iterator is paired together, and then the second item in each passed iterator are paired together, etc. The tuple() function displays a readable version of the result - try running: print(tuple(zip(var1,var2)))

# Simulate table3
np.random.seed(24) # optional: used to fix the seed of the pseudo-random number generator (use any number of your choice)
year = list(range(1970,2021))
temp = np.random.normal(17,2,51)
table3 = pd.DataFrame(list(zip(year, temp)), columns = ["Year", "Temperature"])

# Simulate table4
xx = np.array([16,21])
yy = np.array([300, 1200])
means = [xx.mean(), yy.mean()]  
stds = [xx.std() / 3, yy.std() / 3]
corr = -0.7 # correlation
covs = [[stds[0]**2          , stds[0]*stds[1]*corr], 
        [stds[0]*stds[1]*corr,           stds[1]**2]] # covariance matrix
table4 = pd.DataFrame(np.random.multivariate_normal(means, covs, 100), columns = ["Mean Anual Temperature", "Total Precipitation"])

# Simulate table5
col1 = pd.Series(list(range(1900,2010,10))).repeat(8)
col2 = ["Permanent crops", "Irrigated crops", "Managed Forest", "Natural Forest", "Agro-Forestry system", "Urban", "Pasture", "Shrubland" ]*11
col3 = np.random.uniform(0, 100, 90)
table5 = pd.DataFrame(list(zip(col1, col2, col3)), columns = ["Year", "Landuse", "Cover"])

```
