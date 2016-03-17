## Joining Tables ##
> <p> Because it is a simple tool the connector does not generate joined table results. Nevertheless there there are several features which will allow you to construct basic joins between two tables. Currently there are three methods which I will describe, these are called refresh, in and on.</li></ul>

<blockquote></p><p>
> <b>Refresh</b> join, to construct a refresh query you must have a normal table of data with IDs present in the worksheet.
> You may think of the refresh type of query as "refresh all the data in this table, using the IDs that you find there".
> To make this into a join of two tables, I use a formula in the second table (column F) which refers to a reference ID in the first table (column C).
> </p><p>The keyword refresh is placed where the normal query filter would be located, see example.
> The sfQuery() macro (called by the connector <b>Query Table Data</b> menu item), will then notice the Refresh keyword and proceed to retrieve the rows of data for the entire table using the valid IDs found in this table.
> This results in an effective join, the only requirement is there be one blank row between the two tables, see column E in this example.

</p>
<p>
An example of this is two tables one of which contains opportunity IDs	and data, in the other you would also like to retrieve the account name and data.
Because the account name is located in a separate table will need to construct a refresh query to return the account name given the account IDs. This is best demonstrated by an example of two tables in one worksheet.


<img src='http://sforce.sourceforge.net/excel/refreshjoin.gif' border='0'>
<hr />
<h3>IN Joins</h3>
To demonstrate an example of the IN join, we will reverse the two tables in the first example, this is to answer the question, what are all the opportunities located at the accounts listed in the first table.  Account will be our first table, and<br>
Opportunity data will be fetched into the second table.<br>
Note, the data will not line up on neat rows which match the first table,<br>
this is because many opportunities may exist at a single account.<br>
<br>
<br>
<img src='http://sforce.sourceforge.net/excel/join_in.gif' border='0'>

<hr />

<h3>"ON" Joins</h3>

This type of join is only useful to find the first one of the objects which match the criteria.  It is useful, for example, to determine if there are any opportunties at a given account, this is not easy to extract with from the reporting engine of Salesforce.com, so may be useful when the question is something like "which Accounts do not have opportunities", sounds like something Marketing would ask for.<br>
<br>
Note the use of the keyword "on" in cell H1, and a string which represents a range in cell I1.  You may also add more filters in the cells that follow, 	J1,K1,L1 to restrict the results to only Open opportunities or any other filter that you would use in a normal query.  The name of this query "on" refers to "show me related data ON the same row", which implies only one result per row, and if there are many we don't care which one.  If this type of query is truly useful is an open question, it may lead to confusion, so use with care.<br>
<br>
<br>
<br>
<img src='http://sforce.sourceforge.net/excel/join_on.gif' border='0'>
<hr />
<h3>More Notes</h3>
If you are interested in using multiple tables on one worksheet there is a menu item that will allow you to run all queries on a worksheet with a single command, this menu item is under <b>Multiple Queries</b> and is called<br>
<b>Run Each Query on Current Sheet</b>, the queries are run left to right order