
## Testing and databases - Shiny
### Brief description

There are two testing packages in particular that are frequently used when developing Shiny applications in R: [`testthat`](https://testthat.r-lib.org/), and [`Shinytest`](https://shiny.rstudio.com/articles/testing-overview.html). `Shinytest`'s architecture supports server function tests, and snapshot-based tests in addition to standard unit testing. 

Connecting Shiny applications to a datasource requires no additional platform-specific database connection implementation strategy. Simply using the `DBI` package allows R developers to connect their Shiny application to all the most frequently used DBMSs. 

### Long description

As with any web application, implementing a test framework in your Shiny web app becomes more necessary as your application grows in complexity. While it may be overkill to implement a testing framework for a POC product you are developing yourself, or an MDS lab, when working with collaborators on highly modular activities as is typical in many software dev roles, developing tests for new processes is an integral part of every development task.

There are a handful of testing packages that can be implemented in Shiny apps; below are two of the most common ones.

#### testthat

Developed and maintained by Hadley Wickham, [`testthat`](https://testthat.r-lib.org/) - by its own description - "is the most popular unit testing package for R and is used by thousands of CRAN packages". Implementing `testthat` in your Shiny app requires that you convert your app into a package. A test implemented using `testthat` looks like this:

test_that("as.vector() strips names", {
  x <- c(a = 1, b = 2)
  expect_equal(as.vector(x), c(1, 2))
})

#### shinytest

Produced by developers of RStudio, [`Shinytest`](https://shiny.rstudio.com/articles/testing-overview.html) offers three principal classes of tests:
  1. Unit tests: These are used to test that functions behave as expected.
  2. Server function tests: By running the server function of a Shiny application to simulate a real client session, these tests can be used to test reactive components, and outputs in the server function of your Shiny app.
  3. Snapshot-based tests: While your Shiny application is run in a headless web browser, user actions - such as clicking on buttons and setting inputs to particular values - are simulated. These tests then take snapshots of the state of the application and references those snapshots when evaluating the state of a future iteration of the application.

**Non-sequitur**

Connecting your Shiny application to a data layer can be accomplished in different ways depending on what architecture is used to store application data. The most common data source connections can be made using the [`DBI`](https://dbi.r-dbi.org/) package, including: PostGresql, MSSQL, SQLite, and MongoDB. Check the package website for details on supported database connections, and implementation instructions.


### Links
* https://mastering-shiny.org/scaling-testing.html
* https://shiny.rstudio.com/articles/testing-overview.html
* https://dbi.r-dbi.org/
