## Callable Functions ##

> Users can make a variety of calls to internal functions
> when the sforce\_connector XLA is installed in excel,
here is a short list. You can find these
fairly easily by browsing the functions within the sforce\_connector source


Excel - Tools / Macros / Visual Basic Editor (or Alt-F11)
MS VB, Project Explorer -- sforce\_connector / Modules / s\_force


Many of the functions in this module are meant to be used inernally, but most of those that are reasonably used as a formula is, within an Excel Cell, have comments in the code explaining their usage.

A quick browse gives the following functions. Note that whenever "ID" appears, it refers to one of the salesforce 18 (or 15) character internal ids.

These functions take a string such as "Account" or a cell address such as "A3" and pass these values to the sforce API in a query or search API call, returning the results to the cell which contains the foumula, the most interesting value to return to a worksheet cell is the object ID, because this can be used to query the rest of the data for a given record.

---


<pre>
sfUserName(user id) </pre>
> given an sf user ID , returns the user's first name + last name.   Very useful for owner, last modified by, etc.

---


<pre>sfUserId(fullname)</pre>
> given a (first name + last name), returns the User ID

---

<pre>FixID(id)</pre>
> given either a 15 or 18 character ID, returns an 18 character one


---

<pre>
QuarterNum(date-value)</pre>
> returns the number of the quarter (e.g. 4 for Nov 15th)


---

<pre>
NextQuarter(date-value)</pre>
> returns the first day of the next quarter (e.g. 1/1/2005 for Nov 15th 04)


---

<pre>
fixidcol() </pre>
> if assigned to a macro, will fix all the ids (see FixID, above) for an entire column


---

<pre>soql_table(tablename, querystring)</pre>
> Tricky: returns an ID if the query returns one hit.  The querystring must be in the sytax of the SOQL Where clause.
Example:
<pre>soql_table("Contact","FirstName = 'Scot' and LastName = 'Stoney' ")</pre>


---


<pre>
sflookup(tablename, name)</pre>
> returns the ID for the table based on a search value; it matches most fields

---


<pre>
sfemail(email, Optional findfirst)</pre>
> returns the Contact ID based on a search for the email address.
> > If a second argument is specified, it will return the first match even if more than 1 are found


---

<pre>
sfcontact(firstname, Optional lastname) </pre>

> a short-cut to sflookup. It is the equivalent of:
> > sflookup("Contact", firstname + " " + lastname) with some argument checking


---


<pre>
sfaccount(accountname) </pre> <p>a short-cut to sflookup. It is the equivalent of:<br>
<blockquote>sflookup("Account", accountname) with the removal of some common suffixes such as "Corp".</blockquote>

<hr />
<h3>Build your own</h3>
If you want to build more of these yourself, you'll probably want to look at how each of these calls sflookup_w and the values which you can pass to the salesforce.search function.<br>
<br>
<br>
<br>
<br>
<br>
<br>
<br>
</p>
## Joining Tables ##