
## Tableau Deployment
### Brief description

For Tableau, the deployment, or in other words, the way to generate a public link for our visualization is called *Publish*. 

There are mainly 4 common methods for publishing the workbooks:
* Tableau Server and Tableau Online
* Tableau Desktop
* Tableau Reader
* Tableau Public

All of them are very convenient and easy processes, which can be finished directly through the user interface. What we need to consider when choosing between those options are: 

* Device types used by your intended audience
* Whether users can install client-based software
* Whether the audience needs to edit or change the workbooks
* Our access to Tableau Server
* Licensing needs and the cost of them
* Security requirements

As for the cost, he publishing itself didn’t need extra payment. But we may need to pay 70 dollars per month for Tableau Creator to get the access of Tableau desktop, Tableau Server and Tableau Online. 

### Long description

For Tableau, the deployment, or in other words, the way to generate a public link for our visualization is called *Publish*. 

There are mainly 4 common methods for publishing the workbooks:

#### Tableau Server and Tableau Online:

Tableau Server is a **paid** product provides browser-based analytics without the need to download software. And Tableau Online is the hosted SaaS version of Tableau Server and can also be used to publish and share dashboards and workbooks.

To publish to Tableau Server or Tableau Online, our server or site administrator must grant you the following capabilities:
* A site role of Creator (formerly Publisher) on the site we are publishing to.
* View and Save capabilities set to allowed on the project into which we publish.

With Tableau Server, content can be shared through the share icon in Tableau Server. 
![Tableau server publish](https://i.ibb.co/ysdYsks/Tableau-Server-and-Tableau-Online.jpg)

The share icon can be used to email a link to the workbook or embed a URL on a web page. Users can then access the published Tableau content via a web browser. Users can also subscribe to workbooks or worksheets published on Tableau Server. These workbooks can be set up for automatic refresh, ensuring the latest view of the data. Also, if end-users are given edit permissions, they can make changes within Tableau Server's web authoring environment.

Besides, the workbooks published on Tableau Server and Tableau Online can be viewed on Tableau Mobile as well, which is designed for mobile devices like ipads and cell phones, helping us to keep a pulse on our data from wherever we are, whenever we need it.

#### Tableau Desktop:

Tableau desktop is a **paid** product that allows content editing, viewing and supports multiple methods for sharing. It is available to download on Windows and Mac, and provides the most comprehensive authoring environment. In Tableau Desktop, users can open Tableau packaged workbooks and connect to workbooks published on Tableau Server. The way to publish is also very easy. We just need to open the workbook we want to publish and select Server > Publish Workbook. 

Compared to Tableau Server, Tableau Desktop has more capabilities. For example, we can change whether the data is embedded in the workbook or published separately, or change how people authenticate with data sources. And there are ways to show or hide sheets, show sheets as tabs and include external files. There is a detailed [tutorial](https://help.tableau.com/current/pro/desktop/en-us/publish_workbooks_howto.htm#choose-how-to-generate-thumbnails-for-workbooks-with-user-filters) on the Tableau official website.
 
#### Tableau Reader：

Tableau Reader is a **free** desktop application that you can use to open and interact with data visualizations built in Tableau Desktop.But for workbooks published on Tableau Server, it can not work. Also, Tableau Reader only works with packaged workbooks (TWBX format). This means the Tableau workbook and the data for the workbook are packaged together into a TWBX file, which could be an issue with security and/or file sizes.

#### Tableau Public：

Tableau Public is a **free** platform to publicly share and explore data visualizations online. Anyone can create visualizations using either Tableau Desktop Professional Edition or the free Public Edition. Visualizations published to Tableau Public are available for anyone to see online. To publish the workbooks, we need to open them in Tableau Desktop, select Server > Tableau Public > Save to Tableau Public, sign in with our Tableau Public account, type a name for the workbook and click Save.

After the workbook is published, we will be redirected to our account on the Tableau Public website. To get a link to share on social media or code to embed in a web page, we just need to display a view, and then click Share at the bottom of the view.

To be conclude, all of them are very convenient and easy processes, which can be finished directly through the user interface. What we need to consider when choosing between those options are: 

* Device types used by your intended audience
* Whether users can install client-based software
* Whether the audience needs to edit or change the workbooks
* Our access to Tableau Server
* Licensing needs and the cost of them
* Security requirements

### Links
* [Publish Data Sources and Workbooks](https://help.tableau.com/current/pro/desktop/en-us/publish_overview.htm)
* [Comprehensive Steps to Publish a Workbook](https://help.tableau.com/current/pro/desktop/en-us/publish_workbooks_howto.htm)
* [Save Workbooks to Tableau Public](https://help.tableau.com/current/pro/desktop/en-us/publish_workbooks_tableaupublic.htm)
* [6 Ways to Publish & Share Tableau Content](https://senturus.com/blog/six-ways-to-publish-share-tableau-content/)
