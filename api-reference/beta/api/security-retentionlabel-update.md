---
title: "Update retentionLabel"
description: "Update the properties of a retentionLabel object."
author: "sseth"
ms.localizationpriority: medium
ms.prod: "compliance"
doc_type: apiPageType
---

# Update retentionLabel
Namespace: microsoft.graph.security

[!INCLUDE [beta-disclaimer](../../includes/beta-disclaimer.md)]

Update the properties of a [retentionLabel](../resources/security-retentionlabel.md) object.

To update a [disposition review stage](../resources/security-dispositionreviewstage.md), include the **actionAfterRetentionPeriod** property in the request body with one of the possible values specified.

## Permissions
One of the following permissions is required to call this API. To learn more, including how to choose permissions, see [Permissions](/graph/permissions-reference).

|Permission type|Permissions (from least to most privileged)|
|:---|:---|
|Delegated (work or school account)|RecordsManagement.ReadWrite.All|
|Delegated (personal Microsoft account)|Not supported.|
|Application|RecordsManagement.ReadWrite.All|

## HTTP request

<!-- {
  "blockType": "ignored"
}
-->
``` http
PATCH /security/labels/retentionLabels/{retentionLabelId}

```

## Request headers
|Name|Description|
|:---|:---|
|Authorization|Bearer {token}. Required.|
|Content-Type|application/json. Required.|

## Request body
[!INCLUDE [table-intro](../../includes/update-property-table-intro.md)]


|Property|Type|Description|
|:---|:---|:---|
|actionAfterRetentionPeriod|microsoft.graph.security.actionAfterRetentionPeriod| Specifies the action to be applied on a document with this label after the retention period. The possible values are: `none`, `delete`, `startDispositionReview`, `unknownFutureValue`.|
|behaviorDuringRetentionPeriod|microsoft.graph.security.behaviorDuringRetentionPeriod|Specifies how the behavior of a document with this label should be during the retention period. The possible values are: `doNotRetain`, `retain`, `retainAsRecord`, `retainAsRegulatoryRecord`, `unknownFutureValue`.|
|createdBy|[microsoft.graph.identitySet](/graph/api/resources/identityset)|Represents the user who created the retentionLabel.|
|createdDateTime|DateTimeOffset|Represents the date and time in which the retentionLabel is created.|
|descriptionForAdmins|String|This is an optional property that provides the label information for the admin.|
|descriptionForUsers|String|This is an optional property that provides the label information for the user.|
|displayName|String|Unique string that defines a label name.|
|dispositionReviewStages|[microsoft.graph.security.dispositionReviewStage](../resources/security-dispositionreviewstage.md) collection|Review stages during which reviewers are notified to determine whether a document must be deleted or retained.|
|id|String|Unique ID of the retentionLabel. [entity](/graph/api/resources/entity).|
|isInUse|Boolean|Specifies whether the label is currently being used.|
|lastModifiedBy|[microsoft.graph.identitySet](/graph/api/resources/identityset)|The user who last modified the retentionLabel.|
|lastModifiedDateTime|DateTimeOffset|The latest date time when the retentionLabel was modified.|
|retentionDuration|[microsoft.graph.security.retentionduration](../resources/security-retentionduration.md)|Specifies the number of days to retain the content.|
|retentionTrigger|microsoft.graph.security.retentionTrigger|Specifies whether the retention duration is calculated from the content creation date, labeled date, or last modification date. The possible values are: `dateLabeled`, `dateCreated`, `dateModified`, `dateOfEvent`, `unknownFutureValue`.|
|defaultRecordBehavior|microsoft.graph.security.defaultRecordBehavior|Specifies the locked or unlocked state of a record label when it is created.The possible values are: `startLocked`, `startUnlocked`, `unknownFutureValue`.|
|labelToBeApplied|String|Specifies the replacement label to be applied automatically after the retention period of the current label ends. |



## Response

If successful, this method returns a `200 OK` response code and an updated [microsoft.graph.security.retentionLabel](../resources/security-retentionlabel.md) object in the response body.

## Examples

### Request
<!-- {
  "blockType": "request",
  "name": "update_retentionlabel"
}
-->
``` http
PATCH https://graph.microsoft.com/beta/security/labels/retentionLabels/{retentionLabelId}
Content-Type: application/json
Content-length: 555

{
  "@odata.type": "#microsoft.graph.security.retentionLabel",
  "displayName": "String",
  "behaviorDuringRetentionPeriod": "String",
  "actionAfterRetentionPeriod": "String",
  "retentionTrigger": "String",
  "retentionDuration": {
    "@odata.type": "microsoft.graph.security.retentionDuration"
  },
  "isInUse": "Boolean",
  "descriptionForAdmins": "String",
  "descriptionForUsers": "String",
  "createdBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "labelToBeApplied": "String",
  "defaultRecordBehavior": "String"
}
```


### Response
>**Note:** The response object shown here might be shortened for readability.
<!-- {
  "blockType": "response",
  "truncated": true,
  "@odata.type": "microsoft.graph.security.retentionLabel"
}
-->
``` http
HTTP/1.1 200 OK
Content-Type: application/json

{
  "@odata.type": "#microsoft.graph.security.retentionLabel",
  "id": "64a99fb4-07be-0481-8746-44c15c0eef1f",
  "displayName": "String",
  "behaviorDuringRetentionPeriod": "String",
  "actionAfterRetentionPeriod": "String",
  "retentionTrigger": "String",
  "retentionDuration": {
    "@odata.type": "microsoft.graph.security.retentionDuration"
  },
  "isInUse": "Boolean",
  "descriptionForAdmins": "String",
  "descriptionForUsers": "String",
  "createdBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "createdDateTime": "String (timestamp)",
  "lastModifiedBy": {
    "@odata.type": "microsoft.graph.identitySet"
  },
  "lastModifiedDateTime": "String (timestamp)",
  "labelToBeApplied": "String",
  "defaultRecordBehavior": "String"
}
```

