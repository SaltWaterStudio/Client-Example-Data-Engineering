# Client-Example-Data-Engineering
Data Engineering work done for a client (example of my work)


## Overview of Work
*Note: Client allowed me to put this example up if I blacked out certain information and do not share the code (as it belongs to them).*
### Backstory
Client had 10 years worth of manufacturing data for various products they manufacture stored in a SQL database.  The line was
suppose to be shut down, but the decision was changed to keep it operational.  With yield suffering, they needed a way to look through a database with 80 million
entries and 300 measurement points per part to diagnose when/where problems started to occur.

### Solution
I created a tool in python to be able to select the following filter criteria:
* Time Period
* Product Type
* Lot #
* Serial Number

There is also 2 different types of heat maps discussed below:
**Product Specific:** This heatmap is finding every failing position for the entire product family in the time frame window.  It updates whenever you click
on a new product automatically.
**Serial Number Specific:** This heatmap is finding every failing point for the exact serial number.  It shows which points fail and which ones are close to failing.

Lot yields are automatically calculated and stored right next to the lot # in the 2nd column for an overall health check for each product.

There is also a simulation mode.  This allows you to change specifications to see how it would affect the product/lots as a whole if changed in future designs.  The
yield continues to update even in simulation mode. 

The last main feature is the ability to export to excel all the failures in a product or all the data for a specific lot of parts.  The simulation is taken into account
and will highlight specifications which have a simulated value for easy indentification.

##### Step 1 - Home Screen
The home screen allows you to connect to different databases using ODBC driver.
<img src="pictures/HomeScreen.jpg" height="250">

