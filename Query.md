# Query Menu #

## Table Layout ##

To communicate with the Sforce API, the data to represent a table must be arranged within an Excel Worksheet following a few simple rules which are seen here:<br />
<img src='http://sforce.sourceforge.net/excel/layout.gif' />

**Table Name**, shown in Green (cell "A1" )

**Header Row**, shown in Blue ( cells "A2:D2")

Region, or **Current Region** defines the layout of a single table, which is an area of cells containing values surrounded by one or more blank rows and blank columns, you may have multiple regions / tables on one worksheet






## Filtering the Query ##

**Query Filters** are placed in the cells in Row 1, starting in cell B1 thru Z1, A query consists of a Field, Operator, Value , one in each of three cells, these are used to construct a _where clause_ for SOQL.<br />

<img src='http://sforce.sourceforge.net/excel/query.gif' />

In this example the field is account name and the operator is like and the value to look for is "3M". Multiple query filters may be place in the cells to the right of this first query.

To query for an empty value , use an empty cell in the filter

To construct an "OR" query, you may use comma seperated values in the value cell, for example "3M,Abbott" in cell D1 would generate the following string to SOQL:
where ( name like '%3M%' or name like '%Abbott%' )

Valid operators for cell C1 include all SOQL operators and a few more including: equals, contains, not equals,greater than, less than these are converteed into their SOQL versions "=,like,!=,>,<"

Also available are begins with, ends with, regexp which construct strings to pass to SOQL with wildcards, or in the case of regexp you pass in the wildcards. Example:
Account Name | regexp | "3M%"
will construct the following SOQL: name like '3M%'

## Running a Query ##

Once the table area is constructed, with a table name and a row of column headers, and blank columns as a boundary for the region, you must now place the current selection somewhere within this area, this is done by clicking on one of the cells within the region. You may now select the connector menu item Query Table Data.

The query runs and draws its results into the region just below the header row, progress on drawing the results are placed in the application status bar in the lower left of the Microsoft Excel window.

If no data is returned a small message box will indicate this.