## Testing and Connecting to Databases

### Brief description

The Tableau suite offers a variety of paid dashboard visualization solutions, as well as a some limited read-only and limited-sharing options. Hence, when it comes to testing, a variety of paid testing solutions are available to meet the need for a range of custom use-specific testing scripts, though Tableau offers free  testing solutions for load and capacity management for assessing scability needs. As for connectivity to external databases, Tableau offers a wide array of solutions to seamlessly leverage external data by accessing and retrieving it using a clearly outlined processes listed on its website, tailored to many common data storage options. 

### Long description

#### Testing

When it comes to load and capacity testing, TabJolt provides an open-source solution that can be downloaded directly from its GitHub repository (https://github.com/tableau/tabjolt), helping users assess scalability and capacity needs given application-specific requirements. This is the default Tableau-recommended solution for such testing, which allows the user to select representative workbooks, model expected usage, and assess generated results. 

In addition, a number of automated Tableau testing products are available on the market to perform a wide variety of tests, such has performance testing, stress testing, functional testing, and upgrade testing, among others. Two examples of popular such products include DataGaps and Wisdom (formerly known as Kinesis) These are subscription-based rather than open source products, much like Tableau itself.

#### Connecting to Databases

The process to connecting to databases using Tableau varies slightly depending if it is done via Tableau Desktop, Tableau Server, or Tableau Online. To facilitate connecting to data through either Tableau product, Tableau’s Data Management Add-on leverages Tableau Catalog, which includes virtual connections as a central access point to data. In addition, Tableau Prep Builder is a powerful tool to connect directly to published data sources that can be used in conjunction with Tableau Catalog. 

When using Tableau Desktop, the process of connecting to a database is simple. The user simply has to navigate to `Connect`, `Access`, and `Sign In` via the Tableau UI, and select the needed table data by dragging it to the Canvas or by using an SQL query, and select the appropriate sheet tab. More specific database connection instructions for Tableau Server and Tableau Online can be found in on the Tableau website.

### Links
- https://github.com/tableau/tabjolt
- https://help.tableau.com/current/blueprint/en-us/bp_load_testing.htm
- https://www.datagaps.com/bi-testing-tools/bi-validator/automate-tableau-testing/
- https://wiiisdom.com/wiiisdom-ops/?utm_source=youtube&utm_medium=kinesislauncheng
- https://help.tableau.com/current/pro/desktop/en-us/examples_access.htm#:~:text=Start%20Tableau%20and%20under%20Connect,and%20then%20enter%20the%20password.
- https://help.tableau.com/current/pro/desktop/en-us/examples_tableauserver.htm
