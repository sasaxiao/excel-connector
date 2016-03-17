## Excel Connector Configuration ##

> The force.com excel connector relies on the Office Toolkit v4.0 COM object. This is provided by Salesforce.com to communicate with the Force.com API via SOAP at the API level 16.0.   Therefore, you must ensure that you have the Office Toolkit configured on your system before the VBA code in the excel connector can perform it's magic.

### Why two versions ? ###
> The Enterprise Edition (and Unlimited) enjoy API access and the source code is visible for your modifications.  The PE version contains a secured id to allow it to support API access for this client.  The source code is not visible in this version. Download the correct one for your edition, or you may see a message about "API not enabled".

## Install Force.com Office Toolkit ##
  1. install Office Toolkit from developer.force.com or the on this page [featured downloads](http://code.google.com/p/excel-connector/downloads/detail?name=SForce_Office_Toolkit_MSI.zip&can=2&q=)

## Install Excel Connector XLA ##
> The sforce\_connect.xla is an Excel Add-In and **not intended to be opened directly** by clicking on the XLA file.  To Install the XLA file into Excel:
  1. Launch Excel
  1. Click on the Tools menu bar
  1. Click on -> Add-Ins...
  1. Click on the Browse button, locate the Add-In file from the directory where you unpacked the ZIP file
  1. select the add-in and click OK to load it.

## Macro Security ##
> When the Add-In is loaded you may see a message about Macro Security, you must have a security setting which will allow you to run Macros to access the functionality in the Force.com Excel Connector.  Note: the Add-In is not a signed macro file, so your may need to adjust your security settings to Medium or Low, unless you sign the file yourself. to check your settings click on the following links in Excel

> Tools --> Macro --> Security Level

> Detailed instructions for setting security level may be found in the Microsoft Office help documentation


### Success ###
> When the Connector menu bar appears, then the install is complete and you are ready to access Login and the Force.com API.  Use your normal login and password.  You may also need your security token.

### Why no installer ###
I never built an installer, but check out this solution by Acumen.

The Excel Connector Quickinstaller, developed by Acumen Solutions, is available at  http://code.google.com/p/excel-connector-quickinstaller





### Changes ###
| ee\_1602 |  removes a dll dependency for win7 users ( i think) |
|:---------|:----------------------------------------------------|
| pe\_winter11 |  profesional edition update to latest office toolkit    |