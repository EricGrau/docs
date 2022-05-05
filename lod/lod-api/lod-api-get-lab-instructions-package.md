---
title: "GetLabInstructionsPackage API Command"
description: "The GetLabInstructionsPackage command allows you to download the IDL-MD instructions of a lab as an archived file."
isPublished: false
---

# GetLabInstructionsPackage

The **GetLabInstructionsPackage** command allows you to download the IDL-MD instructions of a lab as an archived file.

## Parameters
|Name|Type|Required|Note|
|--- |--- |--- |--- |
|id|Integer (32-bit)|Yes|The ID of the lab profile that will be the source of the instructions. The profile must be owned by the organization on the API consumer.|


## Response
Instead of providing JSON in the response, the contents of the instructions will be provided as a compressed file.


## Example Usage
Imagine…  A lab profile has an ID = 2393048 and you want to get a package that includes all the content of the instructions.

```
https://labondemand.com/api/v3/GetLabInstructionsPackage?id=2393048
```
