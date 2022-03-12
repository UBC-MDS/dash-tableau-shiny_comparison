
## Backend and project structure - Tableau
### Brief description

Given that Tableau is a fully managed data visualization and analysis platform distributed as a SaaS product, virtually all of their products' source code is not available to common users or developers, and so one typically cannot change or develop anything relating to code architecture or organization. This also includes underlying plotting processes. Tableau does however offer a set of [developer tools](https://www.tableau.com/developer/tools), with which an individual could - in principle - develop a Tableau dashboard extension which overrides or overlays front-end components.

### Long description

Tableau is a data visualization and analysis platform, distributed as a fully managed software as a service (SaaS) product. As such, virtually all of their products' source code is not available to common users or developers, and so one typically cannot change or develop anything relating to code architecture or organization. 

There doesn't really exist the concept of integrating external data visualization tools or libraries with a Tableau dashboard within a Tableau environment. Instead, Tableau dashboards, ad hoc reports, etc., are created entirely via GUIs which abstracts away any backend plotting control from the UX. This is common practice for many softwares/tools/products classified as Business Intelligence (BI) tools. And like other BI tools out there, Tableau offers a rich and robust library of data visualization options across all there modes of delivery (i.e. Tableau Desktop, Tableau Server, Tableau Online, etc.)

Tableau does however offer a set of [developer tools](https://www.tableau.com/developer/tools). An individual could, in principle, develop a Tableau dashboard extension which overrides or overlays front-end components (JavaScript, CSS, etc.) if they were tasked with creating embedded Tableau components in - for example - some proprietary web app. This type of project _does_ happen in the real world, but typically comes with a steep cost, complex implementation, and issues with long-term solution management (at least, in the opinion/experience of the author of this little write-up).

[Here are some examples of some of such dashboard extensions](https://extensiongallery.tableau.com/extensions?version=2021.2) which are publically available.

### Links
* https://www.tableau.com/developer/tools
* https://extensiongallery.tableau.com/extensions?version=2021.2
