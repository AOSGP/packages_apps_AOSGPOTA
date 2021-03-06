AOSGPOTA
-------
A very simple OTA checker with Android Settings look and feel.

How it works
------------
It parses the OTA xml file that you put in your file hosting and compares the version number with the local one.
If the version is newer, it notifies the user for a new ROM update.

How to use
----------
* Prepare the OTA xml file. Use this [template](https://raw.githubusercontent.com/ResurrectionRemix/OTA/master/akhil.xml).
* Upload it to your file hosting and create a hot link of it
* Copy the [ota_conf template](https://raw.githubusercontent.com/ResurrectionRemix/OTA/master/example%20ota_conf) to the root of AOSGP source, as a text file called "ota_conf" (without the quotes)
* Template is also in https://raw.githubusercontent.com/ResurrectionRemix/packages_apps_ResurrectionOTA/marshmallow/ota_conf
* Replace the "ota_url" with your OTA xml hot link
* Check the xml template, and make your own, on your github, and place the resultant link to the raw file in the ota_conf
* If using the given samples, ota_conf is all setup! Else you will have to setup the version checking, etc.


### Most guys can skip the below part

Define how AOSGPOTA should know about the "version". The version must be parseable to a date.
Usually, the version is a part of a build name. For example, the 20170506 in the aosgp-X-2.0-20150426-athene.
Adjust the OTA configuration according to your build name on how should AOSGPOTA parse the version
Find a key in build.prop that represents the aosgp-X-2.0-20170206-athene.zip and set it in the "version_name"
Set the delimiter in "version_delimiter" to "-"
Set the date format in "version_format" to "yyyyMMdd"
Set the position in "version_position" to "3" (zero based)
Find a key in build.prop that represents your device name and set it in the "device_name"
AOSGPOTA will search this device name in the OTA xml file


Credits
-------
* [RR team](http://http://www.resurrectionremix.com//)
  * For the original base app
* [SlimRoms team](http://Slimroms.net/)
  * For the original idea of the SlimCenter and app icon
* [CommonsWare Android Components](https://github.com/commonsguy/cwac-wakeful)
  * For the wakeful intent service that is used in this app
