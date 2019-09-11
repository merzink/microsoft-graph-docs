---
title: "conditionalAccessApplications resource type"
description: "Represents applications and ACRS tags included in and excluded from the policy scope."
localization_priority: Normal
author: "davidmu1"
ms.prod: "microsoft-identity-platform"
doc_type: resourcePageType
---

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

# conditionalAccessApplications resource type

Represents applications and ACRS tags included in and excluded from the policy scope.

## Properties

| Property | Type | Description |
|:-------- |:---- |:----------- |
| `includeApplications` | String collection | Application IDs in scope of policy unless explicitly excluded. |
| `excludeApplications` | String collection | Application IDs excluded from scope of policy. |
| `includeAuthenticationContext` | String collection | ACRS URIs in scope of policy unless explicitly exclude, or ALL. |

## JSON Representation

The following is a JSON representation of the resource.

<!-- {
  "blockType": "resource",
  "optionalProperties": [
    "includeApplications",
    "excludeApplications",
    "includeAuthenticationContext"
  ],
  "@odata.type": "microsoft.graph.conditionalaccessapplications"
}-->

```JSON
{
  "includeApplications": [ "String" ],
  "excludeApplications": [ "String" ],
  "includeAuthenticationContext": [ "String" ]
}
```

<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!--
{
  "type": "#page.annotation",
  "description": "conditionalaccessapplications resource",
  "keywords": "",
  "section": "documentation",
  "tocPath": "",
  "suppressions": []
}
-->