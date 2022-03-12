
# Dash: Backend and Project Structure
## Brief description

Dash primarily supports Plotly objects. It is, however, possible to use other plotting libraries with Dash. Dash prides itself as a language-agnostic framework that supports range of programming languages. According to the [documentation](https://dash.plotly.com/), Dash provides support for **Python**, **R**, **F#** and **Julia** programming languages. 

Other plotting libraries that can be used with Dash via different conversion mechanisms are **Altair**, **Matplotlib**,  **ggplot**, etc.

The following types of maps and map components can be implemented in Dash: Choropleth Maps, Mapbox Choropleth Maps, Bubble Maps, Mapbox Density Heatmap, Hexbin MapBox, Mapbox Map Layers and more.

The typical file structure for a successful build and development of a Dash app is:

```
|── data/            .csv 
│   ├── processed/
│   └── raw/
├── src/             app.py/app.R
├── doc/             .md
├── Procfile
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── README.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
└── LICENSE.md
```

## Long description

###  Common Plotting Libraries
Dash prides itself as a language-agnostic framework that supports range of programming languages. According to the [documentation](https://dash.plotly.com/), Dash provides support for **Python**, **R**, **F#** and **Julia** programming languages. 

In Python, Dash primarily supports **Plotly** objects. It is, however, possible to use other plotting libraries with Dash via different conversion mechanisms such as **Seaborn/Matplotlib**, **Altair/Vega-Lite** and **Bokeh**. Similarly, in R, aside from the **Plotly** library, Dash also supports some common graphing packages such as **ggplot**. However, the level of interaction and robustness of those graphs are maximized when they are plotted using **Plotly**.

* For Altair: We can take advantage of the `to_html()` method to include charts in iframes. This is essentially nesting a HTML page within a page.
* For Matplotlib: There is a `mpl_to_plotly()` function in `plotly.tools` library that will return a plotly figure(which can then be returned to Graph's figure attribute) from `matplotlib` figure.
* For ggplot: With `ggplotly()` by Plotly, you can convert your ggplot2 figures into interactive ones powered by *plotly.js*, ready for embedding into Dash applications.

###  Map and Map Libraries Overview

According to [here](https://plotly.com/python/maps/), the following types of maps and map components can be implemented in Dash:

* Choropleth Maps
* Mapbox Choropleth Maps
* Bubble Maps
* Mapbox Density Heatmap
* Hexbin MapBox
* Mapbox Map Layers and more…

While Plotly is the primary map plotting library for Dash, other plotting libraries can as well be used. Other popular libraries such as Altair, ggplot, Folium are the other popular options that can be used in Dash via conversion mechanisms.


### Files Organization and Structure
For a successful build and deployment of the app on Heroku, the following files are must-haves:
* app.py or app.R file
* Dockerfile
* Docker-compose.yml
* Procfile
* requirements.txt

The typical file structure is:

```
project/
├── data/            .csv
│   ├── processed/
│   └── raw/
├── src/             app.py/app.R
├── doc/             .md
├── Procfile
├── Dockerfile
├── docker-compose.yml
├── requirements.txt
├── README.md
├── CODE_OF_CONDUCT.md
├── CONTRIBUTING.md
└── LICENSE.md
```

Another popular alternative is to put the app.py or app.R file in the root folder of the project.


## Links
* https://medium.datadriveninvestor.com/plotly-dash-everything-you-need-to-know-bc09a5e45395
* https://appsilon.com/dash-vs-shiny/
* https://plotly.com/ggplot2/
* https://towardsdatascience.com/dash-for-beginners-create-interactive-python-dashboards-338bfcb6ffa4
* https://plotly.com/python/maps/
* https://medium.com/swlh/interactive-choropleth-maps-in-python-dd943b99df50
