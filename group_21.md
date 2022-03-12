Reactivity - How do you generate a reactive plot? Can you indicate (1) the basic way to create a reactive plot, (2) how to create a plot reactive to more than one input and, (3) how to create more than one reactive output (for example, having a plot and text to print on the screen)?

## Reactive Plot in Dash
### Brief description

(1) Dash offers the callback function with the new value of the input property, and Dash updates the property of the output component with whatever was returned by the function. So the basic way to create a reactive plot is to to make a connection between input data and output data. This will be done by adding a callback function. We can choose any name for the function which is written in the @app.callback decorator, then move the plot function down under the app.layout just like what we did in lecture notes.

(2) In order to create a plot reactive to more than one input is similar to the basic reactive plot, we need to add another inputs to the callback decorator, then update the plot function and app.layout to be designed to accept multiple inputs.

(3) To create more than one reactive output(for example, having a plot and text to print on the screen) is basiclly similar to plot reactive to more than one input, we need to list all the properties to update in app.callback, and return that many items from the callback. Also we need update the plot function and app.layout with corresponding changes.

### Long description

(1) The basic way to create a reactive plot is to make a connection between input data and output data. This will be done by adding a callback function, for callback functions, they are automatically called by Dash whenever an input component's property changes, so these will update some property in the output. We can also name the function which is written in the @app.callback decorator like a dropdown, a slider bar, and markdown text data. Then we need to move the plot function down under the app.layout and then we use the callback decorator directly on this function (worth to mention, The Dash Core Components (dash.dcc) module includes a Graph component called dcc.Graph. dcc.Graph renders interactive data visualizations using the open source plotly.js JavaScript graphing library). After the input changes, the function wrapped by the callback decorator will get called automatically. All in all, Dash provides this callback function with the new value of the input property as its argument, and Dash updates the property of the output component with whatever was returned by the function, that is, whenever an cell changes (the input), all the cells that depend on that cell (the outputs) will get updated automatically. This is the basic way to create a reactive plot by Dash.

(2) In Dash, the output can have multiple input components. In order to create a plot reactive to more than one input is basically similar to the basic reactive plot, we need to add another inputs to the callback decorator @app.callback, also update the plot function and app.layout. The input arguments of the callback are the current value of each of the input properties, in the order that they were specified. This is worth to mention when a Input updates once (i.e. a user can only change the value of a single Dropdown in a given moment), Dash collects the current state of all specified input properties and passes them to the callback function. These callback functions are always guaranteed to receive the newest state of the application. See below for an example from 532 lecture:
```
cars = data.cars()

# Setup app and layout/frontend
app = Dash(__name__,  external_stylesheets=['https://codepen.io/chriddyp/pen/bWLwgP.css'])
app.layout = html.Div([
    html.Iframe(
        id='scatter',
        style={'border-width': '0', 'width': '100%', 'height': '400px'}),
    dcc.Dropdown(
        id='xcol-widget',
        value='Horsepower',  # REQUIRED to show the plot on the first page load
        options=[{'label': col, 'value': col} for col in cars.columns])])
    dcc.Dropdown(
        id='ycol-widget',
        value='Displacement',
        options=[{'label': col, 'value': col} for col in cars.columns])
@app.callback(
    Output('scatter', 'srcDoc'),
    Input('xcol-widget', 'value'),
    Input('ycol-widget', 'value'))
def plot_altair(xcol, ycol):
    chart = alt.Chart(cars).mark_point().encode(
        x=xcol,
        y=ycol,
        tooltip='Horsepower').interactive()
    return chart.to_html()
```

(3)  To create more than one reactive output(for example, having a plot and text to print on the screen) is basiclly similar to plot reactive to more than one input, we need to list all the properties to update in @app.callback decorator, and return the same number of items from the callback. Still we need to update the plot function and app.layout with corresponding changes to make reactive plot work. In lecture notes, it also mentioned we can define an output area and link it to the plot function as the output area, we can use a Div and the decorated function will now take an additional output in the decorator and return two values instead of one. See below for an example from 532 lecture:
```
@app.callback(
    Output('scatter', 'srcDoc'),
    Output('mean-x-div', 'children'),  # This is the ID of our new output Div
    Input('xcol-widget', 'value'),
    Input('ycol-widget', 'value'))
def plot_altair(xcol, ycol):
    chart = alt.Chart(cars).mark_point().encode(
        x=xcol,
        y=ycol,
        tooltip='Horsepower').interactive()
    return chart.to_html(), f'The mean of {xcol} is {cars[xcol].mean().round(1)}'
```
### Links

Some useful links are included below if wish to learn more:

* https://dash.plotly.com/basic-callbacks
* https://dash.plotly.com/basic-callbacks#dash-app-layout-with-figure-and-slider
* https://dash.plotly.com/basic-callbacks#dash-app-with-multiple-outputs
* https://dash.plotly.com/basic-callbacks#dash-app-with-multiple-inputs
* https://stackoverflow.com/questions/45837031/is-there-a-better-way-to-perform-multiple-output-with-dash-by-plotly
* https://budavariam.github.io/posts/2021/04/05/plotly-dash-development-tips/
