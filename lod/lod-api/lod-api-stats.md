# Stats

The **Stats** command returns statistics about how many labs are currently active and saved.

## Parameters

none

## Response

|Property|Type|Nullable|Note|
|--- |--- |--- |--- |
|NumActive|Integer|False|The number of currently active labs (starting, running, tearing down, saving, resuming, etc)|
|NumSaved|Integer|False|The number of currently saved labs|

## Example Usage

```
https://labondemand.com/api/v3/1234567890/stats
```

## Example Response

```linenums
{
    "NumActive":571, 
    "NumSaved":451,
    "Status": 1,
    "Error": null 
}
```
