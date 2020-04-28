# Foilum-For-G-Map
Google Map creation using Python - Folium Lib

# My Code - For one Single cordinate to show in a graph
import folium

# using folium map function for cordinates
lwmap = folium.Map(location=[46.71654363386108, -84.58394125000001], zoom_start=12, tiles="Stamen Terrain")

# Proving icon and pop for cordinate
tooltip = 'Click me!'

folium.Marker(location=[46.71654363386108, -84.58394125000001],
              popup='<i>LW</i>', tooltip=tooltip, 
              icon=folium.Icon(color='red')).add_to(lwmap)

lwmap

# Importing Pandas library in order to use cordinates excel file.

import pandas as pd

dataset = pd.read_excel("Your file name")
# This will tell about number of column/rows and other info

dataset.info()
# info about data column wise
dataset.columns

# First 3 data lines
dataset.head(3)

# using map function in Folium
covidmap = folium.Map(location=[49.769,-92.840], zoom_start=10)

dataset.columns
# exporting as list for cordinates
Place = dataset[['Latitude', 'Longitude']]

type(Place)

#Converting this into list
Place = Place.values.tolist()

type(Place)

Place
# starting for loop and color/tooltip functionality

tooltip = 'Click me!'
for cordinate in Place:
    folium.Marker(location=cordinate,
                  popup='<i> </i>', tooltip=tooltip,
                  icon=folium.Icon(color='red')).add_to(covidmap)

covidmap
