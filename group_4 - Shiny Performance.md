---
editor_options: 
  markdown: 
    wrap: 72
---

## Shiny Performance and Examples

### Brief description

To increase the performance one has to act smart, and do all the
redundant works before hand.

This is possible in following the **basics**:

1\) Writing codes in piecemeal and in functions(snippets)

2\) Using optimized algorithms to cure the bottlenecks

3\) Using DRY principle

Doing **caching** when ever possible:

1\) Caching the API results

2\) Caching the plots

**Scheduling** redundant and back-end work.

**Other Avenues**: please refer to the section below.

### Long description

#### Part1:

How could we improve the performance of this dashboard?

##### Basics:

The overall dashboards contains many parts(chunks), we should always
focus on writing in piecemeal, and each part should be written in
function. To improve the overall performance, we should find the part of
of the overall dashboard that is running slow. Then we should take that
part/snippet, try to find the bottleneck and if possible optimize it.

1)  Use faster functions, algorithms and use hashing as much as possible
    and less loops(basically reduce the Big O)

For Example: sum_value \<- 0 for (i in 1:100) { sum_value \<- sum_value
+ i \^ 2 }

vs

sum_value \<- sum((1:100) \^ 2)

2)  We should always follow the "DRY"(do not repeat yourself) principle.

There are other techniques discussed below:

##### Caching:

The basic idea is to record the input to and output from every call to a
function. When the function is called with a set of inputs it has
already seen, it gives the output without recomputing, saving huge
amount of time. Here we can use package like `memoise`. Memoise saves
the results of new invocations of functions while reusing the answers
from previous invocations of those functions.

The cache can be shared across multiple users, hence only the first
users need to wait for output, everyone else can use the same cache for
a speedy result. There are following three function that we can use for
caching:

1\. cache_mem - storing cache in RAM (default)

2\. cache_filesystem(path) - storing cache on the local disk

3\. cache_s3(s3_bucket) - storage in the AWS S3 file database

We can use caching while pulling data through API or making humongous
plots.

Caching the API results: There are times when we refer to some data and
procure it from APIs. Each time Rshiny has to hit the server to procure
the data, this takes a lot of time. Caching APIs saves a lot of time.

Caching plots: We can cache the plots so that the next time we load it,
it will save us sometime.

##### Scheduling:

Scheduling a job separately when there is not much traffic, will save a
lot of time. So when we call the Rshiny, it just have to work on a
pre-cleaned data. Do a lot of pre-rendered work before hand rather than
calling everything in the dashboard will save a lot of computing time.

##### Other Avenues:

1.  Breaking the app into different tabs, rather than keeping everything
    in one.
2.  Taking user input, before running some big plots (sometime it might
    not be possible that users dont want it at all)
3.  Setting the user expectation by outrightly stating the running time

#### Part2:

Provide an extensive list of examples of relevant apps (published or in
galleries or repos). Why are they relevant and given what criteria? Do
you find more apps for industry or academia?

-   [French_Electricity](http://shinyapps.dreamrs.fr/rte-data/)
-   [Paris_Metro](http://shinyapps.dreamrs.fr/ratp-traffic/)
-   [Rshiny_Example_Blog](https://benhay.es/posts/building-shiny-dashboards/)
-   [Rshiny_Gallery](https://shiny.rstudio.com/gallery/)
-   [Rshiny_Github_Repo](https://github.com/rstudio/shiny-examples)

Why are they relevant and given what criteria? Do you find more apps for
industry or academia?

In the examples, either in the repos or in dashboards, we can find a lot
of reference for our work, and learn from them either in optimizing the
codes, or having a good interface.

The apps are used both in industries as well as in academia. Like the
few link shared were of the French Electricity, French Traffic while
others were from Finance & Healthcare Industry.

### Links

-   [Mastering_Rshiny](https://mastering-shiny.org/performance.html#improve-performance)
-   [Keynote_by_CTO_RStudio](https://www.rstudio.com/resources/rstudioconf-2019/shiny-in-production-principles-practices-and-tools/)
-   [Youtube_video](https://www.youtube.com/watch?v=YVZdP4qtMHg&ab_channel=AndrewCouch)
-   [4_ways_improve_performance](https://www.rstudio.com/blog/4-tips-to-make-your-shiny-dashboard-faster/)
