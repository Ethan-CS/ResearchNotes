Tags : #RSE #DataPipelineProject
Zettel :  20220716-1515
Status : #triage 

-----

# Initial planning

-----

### Questions & thoughts:

From first discussion with Jess, this is the outline of my task for this project:

Data Pipeline project
- **Website** should include
	- Text, explaining project
	- 3 kinds of data e.g. info about a shop that sells food:
		- Numeric, e.g. distance from home (10 mins, 1.5 miles)
		- Free text (careful here - SQL injection!!) e.g. name of location
		- Category (drop-down), e.g. type of location (farm, corner shop, ...)
		- Extra options (not required for submitting data), maybe several entries:
			- Goods sold?
			- How much for?
- **Backend** stores info -probably a database
- Some way of **displaying** acquired data
- Ethan should start considering tools to use in creating all this

Of course, this is potentially ambitious with time allocation - Jess assured me that even a Microsoft Pages survey-type system, as a rough proof-of-concept, would be sufficient.



-----
 
**Consider:**

- Which tools am I going to use?
	- Building webpage - Java? Which package(s) are suitable for this?
	- Storing data - database? Not too familiar with these, but better than naive (CSV) alternatives
	- Displaying data - another Java implementation?
