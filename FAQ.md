## Frequently Answered Questions ##

Moved xla file to a different folder and now connector won't work.

**Question**

I got the excel connector installed properly yesterday. But I noticed that I had saved it to a temporary folder, so I moved the .xla file to a different folder. Once I did that, whenever I tried to open the .xla file, it says that "the file could not be found. Check the spelling of the file name, and verify that the file location is correct." How can I uninstall, and reinstall all over again?

**Answer**

Yes, if you move the file you may have to uninstall the entry in the Add-In list of Excel and re-install it from the new location. This sounds easy, but it can be tricky because Excel thinks the old file exists until you really clear out the toolbar and entry from the add-in folder
I use steps like this:
> Open Excel
> click Tools, Add-Ins
> uncheck the sforce\_connect checkbox, click OK
> close Excel
> Open Excel again, if the "sforce\_connector" menu bar is still there, right click on the tool bar area of excel, uncheck the sforce Connector check box
> close Excel
> open Excel
> If the bar is gone and the Add-INs list is showing the add-in as unchecked or gone then you can re-install the add-in using the new file location of the XLA, see the install instructions Installation Guide for details on the install.

I wish i could tell you a better way to do this, but these steps work most of the time.