# SFMC Save actions
SFMC Save actions is a module integrating Salesforce Marketing Cloud (SFMC) into Sitecore forms so you can push data from a Sitecore form into SFMC __without developing code__ and with a __intuitive and integrated UI__ for configuration of the field mapping.
## User manual
Before the data arrives in SFMC, the module requires two steps
* A one-time setup _by the developer_
* Creation and configuration of a binding _by the marketeer or content editor_

## Setup
For setting up the module one must download and install the Sitecore module package and publish following items:

> /sitecore/system/Settings/Forms/Submit Actions/Send to SFMC

After that one must configure the salesforce authentication parameters. This is done by adding following code (and replacing the XXX with your auth details) to the configSections part of the web.config:

``` xml
<section name="fuelSDK" type="FuelSDK.FuelSDKConfigurationSection, FuelSDK" />
```
And adding following to the web.config

``` xml
<fuelSDK appSignature="none" clientId="XXX" clientSecret="XXX" useOAuth2Authentication="true" authEndPoint="XXX" restEndPoint="XXX" soapEndPoint="XXX" accountId="XXX"
```

## Creation and configuration of a binding
First you'll need to add the "Send to SFMC" submit action to submit actions of the form you want to send the data to SFMC.

Then, when you open the dashboard application you will be shown a list page. This page will list all the currently configured bindings. Press the  create button to create a new one.

The newly opened page will look like this:

On the top of the page, forms will be listed in the dropdown as well as the existing data extensions from SFMC. As soon as you select a data extension the lower part will be adjusted accordingly to show each data extension column. As soon as a form is selected the dropdowns on each row will be filled with the fields of the selected form. You have the option as well to trigger an event in SFMC as soon as the form is submitted.

Then for each data extension column you'll need to select a field from the dropdown. Fields are grouped:

* __Calculated fields__: values are calculated at submit time e.g. timestamp
* __Form fields__: values are the data the user filled in
* __Engagement data__
* __Xdb__

When you save the binding, don't forget to publish it by using the appropriate button.

##  Changelog
| Version        | Release notes |
| ------------- |:-------------:|
| 1.0.0     |  Initial release |
| 1.1.0      | Added Guid calculated field      |
| 1.2.0 | Form labels are wider <br>Master db is used for editing, Web for reading     |
| 1.2.1 | Adding "SC" prefix to guids      |

## Suported versions
SC 9.1+
## Contributors
* [Alex Dhaenens]( https://github.com/AlexDhaenens )
* [Onur Kapçik @onurkapcik]( https://github.com/Poseid10ur)

## Special thanks
* The Reference
* Arnaud Geyskens
