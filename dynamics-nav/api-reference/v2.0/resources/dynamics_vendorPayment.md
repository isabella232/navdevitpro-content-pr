---
title: vendorPayment resource type | Microsoft Docs
description: A vendor payment object in Dynamics 365 Business Central.
author: SusanneWindfeldPedersen
ms.service: "dynamics365-business-central"
ms.topic: article
ms.devlang: na
ms.tgt_pltfrm: na
ms.workload: na
ms.date: 12/22/2020
ms.author: solsen
---

# vendorPayment resource type

[!INCLUDE[api_v2_note](../../includes/api_v2_note.md)]

Represents a vendor payment in [!INCLUDE[d365fin_long_md](../../includes/d365fin_long_md.md)].

> [!NOTE]  
> For information about enabling APIs for [!INCLUDE[navnow](../../includes/navnow_md.md)] see [Enabling the APIs for Dynamics 365 Business Central](../enabling-apis-for-dynamics-nav.md).

## Methods
| Method | Return Type|Description |
|:--------------------|:-----------|:-------------------------|
|[GET vendorPayment](../api/dynamics_vendorPayment_Get.md)|vendorPayment|Gets a vendor payment object.|
|[DELETE vendorPayment](../api/dynamics_vendorPayment_Delete.md)|none|Deletes a vendor payment object.|
|[POST vendorPayment](../api/dynamics_vendorPayment_Create.md)|vendorPayment|Creates a vendor payment object.|
|[PATCH vendorPayment](../api/dynamics_vendorPayment_Update.md)|vendorPayment|Updates a vendor payment object.|




## Navigation

| Navigation |Return Type| Description | 
 |:----------|:----------|:-----------------|
|[customerPaymentJournal](dynamics_customerpaymentjournal.md)|customerPaymentJournal |Gets the customerpaymentjournal of the vendorPayment.|
|[vendor](dynamics_vendor.md)|vendor |Gets the vendor of the vendorPayment.|
|[dimensionSetLines](dynamics_dimensionsetline.md)|dimensionSetLines |Gets the dimensionsetlines of the vendorPayment.|
|[vendorPaymentJournal](dynamics_vendorpaymentjournal.md)|vendorPaymentJournal |Gets the vendorpaymentjournal of the vendorPayment.|


## Properties

| Property           | Type   |Description     |
|:-------------------|:-------|:---------------|
|id|GUID|The unique ID of the item. Non-editable.|
|journalId|GUID|The ID of the journal.|
|journalDisplayName|string|The display name of the journal that this line belongs to. Read-Only.|
|lineNumber|integer|The vendor payment item line number.|
|vendorId|GUID|The unique ID of vendor.|
|vendorNumber|string|Specifies vendor's number.|
|postingDate|date|The date that the vendor payment   is posted.|
|documentNumber|string|Specifies a document number for the vendor payment.|
|externalDocumentNumber|string|Specifies an external document number for the vendor payment.|
|amount|decimal|Specifies the total amount (including VAT) that the vendor payment consists of.|
|appliesToInvoiceId|GUID|The unique ID of the invoice that the vendor payment is related to.|
|appliesToInvoiceNumber|string|The number of the invoice that the vendor payment is related to.|
|description|string|Specifies the description of the vendor payment.|
|comment|string|A user specified comment on the vendor payment.|
|lastModifiedDateTime|datetime|The last datetime the vendor payment was modified. Read-Only.|


## JSON representation

Here is a JSON representation of the vendorPayment resource.


```json
{
   "id": "GUID",
   "journalId": "GUID",
   "journalDisplayName": "string",
   "lineNumber": "integer",
   "vendorId": "GUID",
   "vendorNumber": "string",
   "postingDate": "date",
   "documentNumber": "string",
   "externalDocumentNumber": "string",
   "amount": "decimal",
   "appliesToInvoiceId": "GUID",
   "appliesToInvoiceNumber": "string",
   "description": "string",
   "comment": "string",
   "lastModifiedDateTime": "datetime"
}
```
## See also

[GET vendorPayment](../api/dynamics_vendorPayment_Get.md)   
[DELETE vendorPayment](../api/dynamics_vendorPayment_Delete.md)   
[POST vendorPayment](../api/dynamics_vendorPayment_Create.md)   
[PATCH vendorPayment](../api/dynamics_vendorPayment_Update.md)   
