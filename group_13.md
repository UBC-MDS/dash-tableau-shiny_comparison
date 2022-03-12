
## Backend and project structure
(1) Common plotting libraries (interactive or not) used in this technology. What are the most used libraries for maps? Describe the different ways to organize the app regarding the files used in the project (could the files be splitted in minor finles / modules/ etc)

### Brief description
The common plotting libraries inclusding: [`ggplot2`](non-interactive); [`Plotly`](interactive); [`Lattice`](non-interactive) 
The most used libraries for maps are [`leaflet`] and [`highcharter`]. 

The two key components of every Shiny app: the UI (short for user interface) which defines how your app looks, and the server function which defines how your app works. Shiny have important tools to organize the app: Founctions; Shiny modules. 

### Long description

The common plotting libraries inclusding: ggplot2(non-interactive); Plotly(interactive); Lattice(non-interactive) 
The most used libraries for maps are leaflet and highcharter. 
The two key components of every Shiny app: the UI (short for user interface) which defines how your app looks, and the server function which defines how your app works. Shiny have important tools to organize the app: Founctions; Shiny modules. 

-Functions, allow you to reduce duplication in your UI code, make your server functions easier to understand and test, and allow you to more flexibly organise your app code.


Functions work well for code that is either completely on the server side or completely on the client side. For code that spans both, i.e. whether the server code relies on specific structure in the UI, you’ll need to use the technique: modules

-Shiny modules, make it possible to write isolated, re-usable code, that coordinates front end and back end behaviour. Modules allow you to gracefully separate concerns so that (e.g.) individual pages in your application can operate independently, or repeated components no longer need to be copied and pasted.
To complete

### Links
* https://mastering-shiny.org/action-graphics.html
* https://shiny.rstudio.com/articles/plot-interaction.html
* https://rstudio.github.io/leaflet/
* https://mastering-shiny.org/basic-app.html
* https://mastering-shiny.org/best-practices.html?q=orga#code-organization
* https://mastering-shiny.org/scaling-modules.html#scaling-modules
