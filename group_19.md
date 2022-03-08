Reactivity - How do you generate a reactive plot? Can you indicate ,  and, (3) how to create more than one reactive output (for example, having a plot and text to print on the screen)?


## Reactive Plot in Shiny
### Brief description

The basic way to create a reactive plot is to create a Shiny UI with the Fluidpage() function. The UI object will set the general layout of the dashboard, and inside that we will define the input box with the numeric input, title and value (similar to Dash). We then create a server function which would take in input, output and session. Inside the function we will use a reactive() expression to tell the server to watch for the changes in inputs. Also, we define the output which tells the UI how to update plots, boxes or texts. We can only call the reactive() expression within a render function or another reactive expression.

In order to create a plot reactive to more than one input is basically similar to the basic reactive plot, but now instead of one input we define multiple numericInputs(). Inside the server function we can call the input by calling input with the $ sign (example: `input$a`). We need to give the plot function to renderplot(). The plot function needs to be designed to accept multiple inputs.

To create more than one reactive output (for example, having a plot and text to print on the screen) we need to add the same input into multiple renders. For example inside the server function an input a can be given to to renderPlot(), renderTable() and renderText() simultaneously. Inside the render functions we should have the functions that create the plot, table, text.


### Long description

The basic way to create a reactive plot is to create a Shiny UI with the Fluidpage() function. The UI object will set the general layout of the dashboard, and inside that we will define the input box with the numeric input, title and value (similar to Dash). We then create a server function which would take in input, output and session. Inside the function we will use a reactive() expression to tell the server to watch for the changes in inputs. Also, we define the output which tells the UI how to update plots, boxes or texts. We can only call the reactive() expression within a render function or another reactive expression.

In order to create a plot reactive to more than one input is basically similar to the basic reactive plot, but now instead of one input we define multiple numericInputs(). Inside the server function we can call the input by calling input with the $ sign (example: `input$a`). We need to give the plot function to renderplot(). The plot function needs to be designed to accept multiple inputs.

To create more than one reactive output (for example, having a plot and text to print on the screen) we need to add the same input into multiple renders. For example inside the server function an input a can be given to to renderPlot(), renderTable() and renderText() simultaneously. Inside the render functions we should have the functions that create the plot, table, text.

See below for an example.
```
ui <- fluidPage(
  numericInput("a", "a", value = 10),
  numericInput("b", "b", value = 1),
  numericInput("c", "c", value = 1),
  plotOutput("x"),
  tableOutput("y"),
  textOutput("z")
)

server <- function(input, output, session) {
  rng <- reactive(input$a * 2)
  smp <- reactive(sample(rng(), input$b, replace = TRUE))
  bc <- reactive(input$b * input$c)
  
  output$x <- renderPlot(hist(smp()))
  output$y <- renderTable(max(smp()))
  output$z <- renderText(bc())
}
```


### Links
* https://mastering-shiny.org
* https://mastering-shiny.org/basic-reactivity.html
* https://shiny.rstudio.com/tutorial/written-tutorial/lesson6/
* https://mastering-shiny.org/reactive-graph.html
