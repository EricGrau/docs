---
title: "Launch API Command"
description: "The Launch command will launch a specified lab for a specified user. "
isPublished: false
---

# Launch

!INSTRUCTIONS[](https://raw.githubusercontent.com/LearnOnDemandSystems/docs/master/lod/lod-api/api-deprecate-message.md)

<!--
The **Launch** command will launch a specified lab for a specified user. 

## Parameters

|Name|Type|Required|Note|
|--- |--- |--- |--- |
|labId|Integer|Yes|The ID of the lab profile|
|userId|String|Yes|The ID you use to identify the user in your external system.|
|firstName|String|Yes|The user’s first name|
|lastName|String|Yes|The user’s last name|
|email|String|No|The user’s email address|
|classId|String|No|An optional parameter used to associate the lab with a class (see [GetOrCreateClass](lod-api-get-or-create-class.md). This is the unique identifier of the class as it is represented in your organization.|
|canBeMarkedComplete|Integer|No|An optional parameter used to specify if the lab can be marked as complete by the student. 1 = true, 2 = false. If not specified, defaults to 1 (true).|
|tag|String|No|An optional parameter that can be used for tagging the lab instance with your own custom data.|
|ipAddress|String|No|When specified, Lab on Demand will attempt to launch the lab in the closest available delivery region. You should provide the IP address of the user that is taking the lab, not the IP address of your system. IPv4 and IPv6 address are supported.|
|regionId|Integer|No|When specified, Lab on Demand will attempt to launch the lab in the specified delivery region if a suitable host in that region is available and all required storage is available in that region. Delivery regions can be found using the [DeliveryRegions command](lod-api-delivery-regions.md) or [Catalog command](lod-api-catalog.md). Using the ipAddress parameter will result in a more reliable geo-location of the lab for the end user.|
|roleId|Integer|No|Allows you specify the role(s) to assign to the user. You may pass multiple instances of this parameter to specify multiple roles. Roles are used for specialized integration purposes and are not needed in typical integration scenarios. Role IDs will be provided by Skillable when appropriate.|
|variable-name|string|No|Allows you to set the values of named variables used within the lab instance.|
|maxSavedLabs|Integer|No|The max number of labs an individual user may save. This is capped by the number configured on your API consumer.|
|maxSaveDays|Integer|No|The max number of days an individual user may save their lab. This is capped by the number configured on your API consumer.|
|maxActiveLabs|Integer|No|The max number of concurrent lab instances is capped by the number configured on your API consumer.|
|lang|String|No|Allows you to override the lab client UI language. Please note this only affects the lab client UI elements such as menus, tabs, and dialogs. The lab instructions and content are not affected.|
| | | | en = English |
| | | | es = Spanish |
| | | | fr = French  |
| | | | pt = Portuguese  |
| | | | ja = Japanese  |
| | | | zh = Chinese  |
| | | | ko = Korean  |

## Response

|Property|Type|Nullable|Notes|
|---|---|---|---|
|Result| Integer | False | 0 = Error 
||  |  | 1 = Success
||  |  | 2 = User has too many active labs
||  |  | 3 = Insufficient host resources
||  |  | 5 = API integration has too many active labs
||  |  | 6 = User has a saved instance of this lab
||  |  | 7 = API integration doesn't have enough available RAM
||  |  | 10 = User doesn't have enough available RAM
||  |  | 20 = User's organization has too many active labs
||  |  | 30 = User's organization doesn't have enough available RAM
||  |  | 40 = Lab profile has too many active instances
||  |  | 50 = Lab organization doesn't have enough available RAM
||  |  | 60 = Lab organization has too many active instances
||  |  | 70 = Lab series has too many active instances
||  |  | 80 = Lab series doesn't have enough available RAM
||  |  | 90 = Too many labs within the specified class are currently active for another lab to be launched.
||  |  | 100 = User has launched the maximum number of instances of this lab profile.
||  |  | 110 = This lab is not currently available for launch via API. It is awaiting security review.
||  |  | 120 = Lab instance is not in the correct state to perform the requested action.
||  |  | 130 = This lab is not currently available for launch via API. It is awaiting security review.
||  |  | 140 = The request is invalid or contains invalid parameters.
||  |  | 150 = The participant lab instance cannot be launched because the shared class environment is not currently available.
||  |  | 160 = The lab cannot be launched because the user is required to provide additional information.
|Url|String|False|A URL where the lab can be viewed by the user|
|LabInstanceId|Long|False|The Id assigned to the new lab instance|
|Expires|Long|False|When the lab will expire (in Unix epoch time)|
|Status|Integer|No|Indicates the status of the API request
||||0 = Error
||||1 = Success|
|Error|String|False|In the event of an error, this will contain a detailed error message.|

## Example Usage

Imagine… You have a user named Joe Smith. His ID in your system is 555. His email address is joe.smith@email.com. You want to launch a lab with an ID of 100.

```
https://labondemand.com/api/v3/launch?labid=100&userid=555&firstname=Joe&lastname=Smith&email=joe.smith@email.com
```

## Example Response

```linenums
{
    "Result":1,
    "Url":"https://labondemand.com/console/setup/1b4909d6-0dbe-43db-9ab9-74ee4f913c4e",
    "LabInstanceId":3896477,
    "Expires": 1337977153,
    "Status": 1,
    "Error": null
}
```
-->