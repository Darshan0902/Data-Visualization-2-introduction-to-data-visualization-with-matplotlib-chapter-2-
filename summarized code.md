# Importing all essential libraries.


```
import matplotlib.pyplot as plt
import numpy as np
import pandas as pd

```

<h2> Read data with a time index </h2>

Exercise : 

pandas DataFrame objects can have an index that denotes time. This is useful because Matplotlib recognizes that these measurements represent time and labels the values on the axis accordingly.

In this exercise, you will read data from a CSV file called climate_change.csv that contains measurements of CO2 levels and temperatures made on the 6th of every month from 1958 until 2016. You will use pandas' read_csv function.

To designate the index as a DateTimeIndex, you will use the parse_dates and index_col key-word arguments both to parse this column as a variable that contains dates and also to designate it as the index for this DataFrame.

INSTRUCTIONS :

Import the pandas library as pd.
Read in the data from a CSV file called 'climate_change.csv' using pd.read_csv.
Use the parse_dates key-word argument to parse the "date" column as dates.
Use the index_col key-word argument to set the "date" column as the index.


```

# Import pandas as pd
import pandas as pd

# Read the data from file using read_csv
climate_change = pd.read_csv("climate_change.csv", parse_dates=["date"],index_col=["date"])

```

<h2> Plot time-series data </h2>

<h3> EXERCISE : </h3>

<br> To plot time-series data, we use the Axes object plot command. The first argument to this method are the values for the x-axis and the second argument are the values for the y-axis.
<br>This exercise provides data stored in a DataFrame called climate_change. This variable has a time-index with the dates of measurements and two data columns: "co2" and "relative_temp".
<br>In this case, the index of the DataFrame would be used as the x-axis values and we will plot the values stored in the "relative_temp" column as the y-axis values. We will also properly label the x-axis and y-axis.


<h3> INSTRUCTIONS </h3>

<br> Add the data from climate_change to the plot: use the DataFrame index for the x value and the "relative_temp" column for the y values.
<br> Set the x-axis label to 'Time'.
<br> Set the y-axis label to 'Relative temperature (Celsius)'.
<br> Show the figure

```

import matplotlib.pyplot as plt
fig, ax = plt.subplots()

# Add the time-series for "relative_temp" to the plot
ax.plot(climate_change.index, climate_change['relative_temp'])

# Set the x-axis label
ax.set_xlabel('Time')

# Set the y-axis label 
ax.set_ylabel('Relative temperature (Celsius)')

# Show the figure
plt.show()

```

































