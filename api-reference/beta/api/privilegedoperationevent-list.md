---
title: "List privilegedOperationEvents"
description: "filter`` expression."
localization_priority: Normal
---

# List privilegedOperationEvents

> **Important:** APIs under the /beta version in Microsoft Graph are in preview and are subject to change. Use of these APIs in production applications is not supported.

Retrieve a list of [privilegedOperationEvent](../resources/privilegedoperationevent.md) objects, which represent the audit events that are generated by Privileged Identity Management for the role operations. For the details about the audit event, refer [privilegedOperationEvent](../resources/privilegedoperationevent.md). To filter the query results, use the standard OData ``$filter`` expression.


## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

The requestor needs to have one of the following roles: _Privileged Role Administrator_, _Global Administrator_, _Security Administrator_, or _Security Reader_.

 

|Permission type      | Permissions (from least to most privileged)              |
|:--------------------|:---------------------------------------------------------|
|Delegated (work or school account) | Directory.AccessAsUser.All    |
|Delegated (personal Microsoft account) | Not supported.    |
|Application | Not supported. |

## HTTP request
<!-- { "blockType": "ignored" } -->
```http
GET /privilegedOperationEvents
```
## Optional query parameters
This method supports the [OData Query Parameters](https://developer.microsoft.com/graph/docs/concepts/query_parameters) to help customize the response.

## Request headers
| Name      |Description|
|:----------|:----------|
| Authorization  | Bearer {token}. Required. |

## Request body
Do not supply a request body for this method.

## Response

If successful, this method returns a `200 OK` response code and collection of [privilegedOperationEvent](../resources/privilegedoperationevent.md) objects in the response body.

Note that the tenant needs to be registered to PIM. Otherwise, the HTTP 403 Forbidden status code will be returned.
## Examples

### Get audit events for role assignment operations
##### Request
The following example shows a request to get the audit events for the role assignment operations. In this case, ``requestType`` value is ``Assign``.

<!-- { "blockType": "request" } -->
```http
GET https://graph.microsoft.com/beta/privilegedOperationEvents?$filter=requestType%20eq%20'Assign'
```
##### Response
The following example shows the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.privilegedOperationEvent",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 547

{
    "value": [
        {
            "id": "201707240003469369",
            "userId": "2cf9eef8-bc67-4aa4-bb65-75cc9e5c3f80",
            "userName": "admin1",
            "userMail": "admin1@contoso.onmicrosoft.com",
            "roleId": "9360feb5-f418-4baa-8175-e2a00bac4301",
            "roleName": "Directory Writers",
            "expirationDateTime": "0001-01-01T00:00:00Z",
            "creationDateTime": "2017-07-24T18:32:38.7589078Z",
            "requestorId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "requestorName": "admin",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Assign",
            "additionalInformation": null,
            "referenceKey": null,
            "referenceSystem": null
        },
        {
            "id": "201707240003469372",
            "userId": "2cf9eef8-bc67-4aa4-bb65-75cc9e5c3f80",
            "userName": "admin",
            "userMail": "admin1@contoso.onmicrosoft.com",
            "roleId": "95e79109-95c0-4d8e-aee3-d01accf2d47b",
            "roleName": "Guest Inviter",
            "expirationDateTime": "0001-01-01T00:00:00Z",
            "creationDateTime": "2017-07-24T18:33:00.7607701Z",
            "requestorId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "requestorName": "admin",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Assign",
            "additionalInformation": null,
            "referenceKey": null,
            "referenceSystem": null
        }
	]
}
```
### Get audit events for the operations of self role activation and makePermanent
##### Request
The following example shows a request to get the audit events for the operations of self role activation and makePermanent. In this case, ``requestType`` value is ``Activate``.

<!-- { "blockType": "request" } -->
```http
GET https://graph.microsoft.com/beta/privilegedOperationEvents?$filter=requestType%20eq%20'Activate'
```
##### Response
The following example shows the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.privilegedOperationEvent",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 547

{
    "value": [
        {
            "id": "201707240003469811",
            "userId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "userName": "admin1",
            "userMail": "admin1@contoso.onmicrosoft.com",
            "roleId": "44367163-eba1-44c3-98af-f5787879f96a",
            "roleName": "CRM Service Administrator",
            "expirationDateTime": "0001-01-01T00:00:00Z",
            "creationDateTime": "2017-07-24T23:34:41.9661094Z",
            "requestorId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "requestorName": "admin1",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Activate",
            "additionalInformation": "Make permanent admin",
            "referenceKey": null,
            "referenceSystem": null
        },
        {
            "id": "201707240003469814",
            "userId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "userName": "admin1",
            "userMail": "admin1@contoso.onmicrosoft.com",
            "roleId": "95e79109-95c0-4d8e-aee3-d01accf2d47b",
            "roleName": "Guest Inviter",
            "expirationDateTime": "2017-07-25T00:37:07.3402169Z",
            "creationDateTime": "2017-07-24T23:37:08.0052112Z",
            "requestorId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "requestorName": "admin1",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Activate",
            "additionalInformation": "self activate",
            "referenceKey": "",
            "referenceSystem": ""
        }
	]
}
```

### Get audit events for role assignment deactivation
##### Request
The following example shows a request to get the audit events for role assignment deactivation. In this case, ``requestType`` value is ``Deactivate``.

<!-- { "blockType": "request" } -->
```http
GET https://graph.microsoft.com/beta/privilegedOperationEvents?$filter=requestType%20eq%20'Deactivate'
```
##### Response
The following example shows the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.privilegedOperationEvent",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 547

{
    "value": [
        {
            "id": "201707240003469375",
            "userId": "2cf9eef8-bc67-4aa4-bb65-75cc9e5c3f80",
            "userName": "admin1",
            "userMail": "admin1@contoso.onmicrosoft.com",
            "roleId": "95e79109-95c0-4d8e-aee3-d01accf2d47b",
            "roleName": "Guest Inviter",
            "expirationDateTime": "0001-01-01T00:00:00Z",
            "creationDateTime": "2017-07-24T18:33:28.3408971Z",
            "requestorId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "requestorName": "admin1",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Deactivate",
            "additionalInformation": "Make eligible admin",
            "referenceKey": null,
            "referenceSystem": null
        }
	]
}
```
### Get audit events created in a time range
##### Request 
The following example shows a request to get the audit events created in a time range.

<!-- { "blockType": "request" } -->
```http
GET https://graph.microsoft.com/beta/privilegedOperationEvents?$filter=(creationDateTime%20ge%202017-06-25T07:00:00Z)%20and%20(creationDateTime%20le%202017-07-25T17:30:17Z)&$count=true&$orderby=creationDateTime%20desc
```
##### Response
The following example shows the response. Note: The response object shown here may be truncated for brevity. All of the properties will be returned from an actual call.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.privilegedOperationEvent",
  "isCollection": true
} -->
```http
HTTP/1.1 200 OK
Content-type: application/json
Content-length: 547

{
    "@odata.context": "https://graph.microsoft.com/beta/$metadata#privilegedOperationEvents",
    "@odata.count": 2,
    "value": [
        {
            "id": "201707250003471056",
            "userId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "userName": "admin",
            "userMail": "admin@contoso.onmicrosoft.com",
            "roleId": "95e79109-95c0-4d8e-aee3-d01accf2d47b",
            "roleName": "Guest Inviter",
            "expirationDateTime": "2017-07-25T17:38:49.5640383Z",
            "creationDateTime": "2017-07-25T16:38:50.3681771Z",
            "requestorId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "requestorName": "admin",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Activate",
            "additionalInformation": "activate test",
            "referenceKey": "",
            "referenceSystem": ""
        },
        {
            "id": "201707250003469896",
            "userId": "0f693614-c255-4cf5-92fa-74e770c656d8",
            "userName": "admin",
            "userMail": "admin@contoso.onmicrosoft.com",
            "roleId": "95e79109-95c0-4d8e-aee3-d01accf2d47b",
            "roleName": "Guest Inviter",
            "expirationDateTime": "0001-01-01T00:00:00Z",
            "creationDateTime": "2017-07-25T00:37:08.6172407Z",
            "requestorId": "6b61baec-bb80-4a8a-b8bd-fa5ba1f12386",
            "requestorName": "Azure AD PIM",
            "tenantId": "ef73ae8b-cc96-4325-9bd1-dc82594b0b40",
            "requestType": "Deactivate",
            "additionalInformation": "Expired",
            "referenceKey": "",
            "referenceSystem": ""
        }
	]
}
```
<!-- uuid: 8fcb5dbc-d5aa-4681-8e31-b001d5168d79
2015-10-25 14:57:30 UTC -->
<!-- {
  "type": "#page.annotation",
  "description": "List privilegedOperationEvents",
  "keywords": "",
  "section": "documentation",
  "tocPath": ""
}-->