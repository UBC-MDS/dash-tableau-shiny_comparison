
## Topic name (replace)
### Brief description

There are multiple ways to deploy a Shiny app on the web. These include deployment to the cloud through Shinyapps.io, open source virtual private cloud through the Shiny Servers and commercially in a premises/virtual private cloud using RStudio Connect. Shinyapps.io is a flexible and easy to use option to deploy apps as quickly as a few minutes that is hosted in servers operated by R Studio1. Hence it is suitable for hosting prototypes, individual projects but also more  complex projects. It can be used for free to host upto 5 apps, and if there is a need for more, there are tiered paid versions. The open source Shiny server has the advantage that it can run behind private firewalls, can be used to host multiple applications using the same server, each with a unique URL. Again this version is free. The recommended option for commercial deployment is through RStudio Connect, which is a standalone product that supports both Python and R , and can host applications, dashboards and even Jupyter Notebooks3. The servers it is deployed on can be controlled by the organization, whether it is on some server behind a firewall or a VPC. It also includes a whole host of other features including integration with RStudio, easy scale up and web application support.

### Long description

In general, there are two main ways to host Shiny apps on the web: through servers hosted by RStudio or on personal servers. 

Shinyapps.io is a flexible and easy to use cloud based option to deploy apps in  as quickly as a few minutes. It is a software as service package that is hosted in servers operated by R Studio1. It is suitable for hosting prototypes, individual projects and also more complex projects due to its ease of use.  It can be used for free to host upto 5 apps, and if there is a need for more, there are tiered paid versions. Scalability is also very easy as this method is cloud based. However the disadvantage is that there is no firewall protection for the app, so commercial or company specific apps may not be suited for this type of deployment (1). 

The open source Shiny Server package has the advantage that it can run behind private firewalls and can be used to host multiple applications using the same server, each with a unique URL2. The professional version of Shiny Server offers additional features such as access restrictions for the applications, SSL encryption and performance management. Shiny Server open source is free, whereas the professional version is paid (2,3).

The recommended option for commercial deployment is through RStudio Connect, which is a standalone product that supports both Python and R , and can host applications, dashboards and even Jupyter Notebooks3. It is also integrated with Git and provides a user interface. The servers it is deployed on can be controlled by the organization, whether it is on some server behind a firewall or a VPC. It also includes a whole host of other features including integration with RStudio, easy scale up and web application support. It is designed to be used by many users within an organization. It is however only available as a paid version (4). 

### Links
https://shiny.rstudio.com/deploy/. 
https://www.rstudio.com/products/shiny/download-server/  
https://docs.rstudio.com/shiny-server/#introduction  
https://www.rstudio.com/assets/img/RStudio-Connect-12July2021.pdf
