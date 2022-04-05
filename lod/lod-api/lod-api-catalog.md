---
title: "Catalog API Command"
description: "The Catalog command will return all lab series, lab profiles, and delivery regions available to your organization. Lab profiles are generally grouped into series. Depending on your organization, you may have multiple physical delivery regions available to you."
isPublished: true
---

# Catalog

The **Catalog** command will return all lab series, lab profiles, and delivery regions available to your organization. Lab profiles are generally grouped into series. Depending on your organization, you may have multiple physical delivery regions available to you.

## Parameters

|Name|Type|Required|Note
|--- |--- |--- |--- |
|includeAll|Integer|No|This parameter can usually be ignored. When not included (or passed as any value except 1), labs that are not currently available for launch will not be included in catalog results. If you want to include all lab profiles, regardless of whether they are enabled or are developmentally complete, you can pass includeAll=1.|
|LabSeriesID|Integer|No|By providing a LabSeriesID, the response will be filtered so that only lab profiles within the specified lab series will be returned.
|OrganizationID|Integer|No|By providing an OrganizationID, the response will be filtered so that only lab profiles belonging to the specified organization will be returned.

## Response

|Name|Type|Nullable|Note
|--- |--- |--- |--- |
|LabSeries|Array of Lab Series|No|See the LabSeries Type below|
|LabProfiles|Array of Lab Profile|No|See the LabProfile Type below|
|DeliveryRegions|Array of DeliveryRegion|No|See the DeliveryRegion Type below|
|Status|Integer|No|Indicates the status of the API request
||||0 = Error
||||1 = Success|
|Error|String|Yes|In the event of an error, this will contain a detailed error message.|

### LabSeries

|Name|Type|Nullable|Note
|--- |--- |--- |--- |
|Id|Integer|No|The unique identifier of the lab series|
|Name|String|No|The name of the lab series|
|Description|String|Yes|A brief description of the lab series|
|NumTrainingDays|Integer|No|The number of training days expected to complete the series|
|EnableScheduledArchive|Bool|No|The number of training days expected to complete the series|
|ScheduledArchiveDateTime|Datetime|No|The number of training days expected to complete the series|


### LabProfile

|Name|Type|Nullable|Note
|--- |--- |--- |--- |
|Id|Integer|No|The unique identifier of the lab profile|
|Name|String|No|The name of the lab profile|
|Number|String|No|The lab number (usually to identify a lab within a series, e.g. Module 1, Module 2, etc.)|
|PlatformId|Integer|No|The virtualization platform the lab is run on.|
||||1 = None|
||||2 = Hyper-V|
||||3 = ESX|
||||10 = Azure|
||||11 = AWS|
||||20 = Docker|
|CloudPlatformId|Integer|Yes|The cloud platform the lab is run on.
||||null = None|
||||10 = Azure|
||||11 = AWS|
|Enabled|Boolean|No|Whether the lab is currently enabled for launch.|
|ReasonDisabled|String|Yes|The reason the lab is disabled. Only supplied when the lab is not enabled.|
|DevelopmentStatusId|Integer|No|Indicates the development status of the lab. In general, a lab not marked as Complete should not be launched (though it can be).
||||1 = In Development
||||5 = AwaitingVerification
||||7 = InVerification
||||8 = VerificationFailed
||||10 = Complete|
|Description|String|Yes|A brief description of the lab profile|
|SeriesId|Integer|Yes|The unique identifier of the series the lab profile belongs to|
|Objective|String|Yes|Text describing the objective of the lab|
|Scenario|String|Yes|Text describing the scenario of the lab|
|ExpectedDurationMinutes|Integer|No|The expected number of minutes a user will take to complete the lab|
|DurationMinutes|Integer|No|The maximum number of minutes a lab instance is allowed to run before it expires|
|RAM|Integer|No|The amount of RAM in MB used by the lab|
|HasIntegratedContent|Bool|No|Indicates whether the lab has integrated digital lab (IDL) content|
|ContentVersion|Integer|No|Indicates the content version (only applicable if HasIntegratedContent = true)|
|IsExam|Bool|No|Indicates whether the lab is scored as an exam|
|PremiumPrice|Decimal|No|The consumption cost of the lab when premium experience features are included.|
|BasicPrice|Decimal|No|The consumption cost of the lab when only basic experience features are included.|
|Tags|Array of String|No|A list of tags associated with the lab profile.|
|SharedClassEnvironmentRoleId|Integer|Yes|Indicates the role the lab plays in a shared environment|
||||0 = None. This lab has no shared environment involvement at all. Most labs work this way.)|
||||10 = Shared Environment. This lab provides the shared infrastructure that participant labs will connect into. Typically launched and maintained by an administrator or instructor.|
||||20 = Participant. This lab will connect into shared environments and act as a participant. Typically launched by students.|

### DeliveryRegion

|Name|Type|Nullable|Note
|--- |--- |--- |--- |
|Id|Integer|No|The unique identifier of the delivery region. When specified, Lab on Demand will attempt to launch the lab in the specified delivery region if a suitable host in that region is available and all required storage is available in that region. Delivery regions can be found using the [DeliveryRegions command](lod-api-delivery-regions.md) or [Catalog command](lod-api-catalog.md). Using the ipAddress parameter will result in a more reliable geo-location of the lab for the end user.||
|Name|String|No|The name of the delivery region|
|Description|String|Yes|A brief description of the delivery region|

## Example Usage

```
https://labondemand.com/api/v3/catalog
```

## Example Response

```linenums
{
    "LabSeries": [
        {
            "Id": 1,
            "Name": "Demo Series 1",
            "Description": "A demo lab series",
            "NumTrainingDays": 5
            "EnableScheduledArchive": true,
            "ScheduledArchiveDateTime": "2022-03-07T08:00:00"
        },
        {
            "Id": 2,
            "Name": "Demo Series 2",
            "Description": Another demo lab series,
            "NumTrainingDays": 5
            "EnableScheduledArchive": false,
            "ScheduledArchiveDateTime": null
        }
    ],
    "LabProfiles": [
        {
            "Id": 1,
            "Name": "Demo Lab 1",
            "Number": " Module 1",
            "PlatformId": 2,
            "CloudPlatform": null,
            "SeriesId": 1,
            "Enabled" : true,
            "ReasonDisabled" : null,
            "DevelopmentStatusId" : 10,
            "Description": "A demo lab",
            "Objective": "This is the HTML-formatted objective of the lab",
            "Scenario":" This is the HTML-formatted scenario of the lab",
            "DurationMinutes": 360,
            "ExpectedDurationMinutes":60,
            "Ram": 8192,
            "HasIntegratedContent": true,
            "ContentVersion": 2,
            "IsExam": false,
            "PremiumPrice" : 10.00,
            "BasicPrice" : 8.00,
            "SharedClassEnvironmentRoleId": 0,
            "Tags": [
                "Tag1",
                "Tag2"
            ]
        },
        {
            "Id": 2,
            "Name": "Demo Lab 2",
            "Number": " Module 2",
            "PlatformId": 2,            
            "CloudPlatform": 10,
            "SeriesId": 1,
            "Enabled" : true,
            "ReasonDisabled" : null,
            "DevelopmentStatusId" : 10,
            "Description": "Another demo lab",
            "Objective": "This is the HTML-formatted objective of the lab",
            "Scenario": "This is the HTML-formatted scenario of the lab",
            "DurationMinutes": 360,
            "ExpectedDurationMinutes":60,
            "Ram": 4096,
            "HasIntegratedContent": true,
            "ContentVersion": 2,
            "IsExam": false,
            "PremiumPrice" : 4.00,
            "BasicPrice" : 4.00,
            "SharedClassEnvironmentRoleId": 0,
            "Tags": [
                "Tag1",
                "Tag2"
            ]
        }
    ],
    "DeliveryRegions": [
        {
            "Id": 1,
            "Name": "North America",
            "Description": "North American datacenters"
        },
        {
            "Id": 2,
            "Name": "Australia",
            "Description": null 
        }
    ],
    "Status": 1,
    "Error": null
}
```