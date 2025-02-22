---
title: "GETFILTERS Function (Record)"
description: GETFILTERS Function (Record)
ms.custom: na
ms.date: 06/05/2016
ms.reviewer: na
ms.suite: na
ms.tgt_pltfrm: na
ms.topic: article
ms.prod: "dynamics-nav-2018"
ms.assetid: 6891d81b-9f79-441f-becb-fb71c740a3d8
caps.latest.revision: 11
manager: edupont
---
# GETFILTERS Function (Record)
Gets a string that contains a list of the filters within the current filter group for all fields in a record. In addition, this function also returns the state of the [MARKEDONLY Function \(Record\)](MARKEDONLY-Function--Record-.md).  
  
## Syntax  
  
```  
  
String := Record.GETFILTERS  
```  
  
#### Parameters  
 *Record*  
 Type: Record  
  
 The record from which you want a list of filters.  
  
## Property Value/Return Value  
 Type: Text or code  
  
 This string contains a list of the filters for all fields in *Record*.  
  
## Example 1
 This example requires that you create the following variables and text constant in the **C/AL Globals** window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Str|Text|Not applicable|  
|CustLedgerEntry|Record|Cust. Ledger Entry|  
  
|Text constant|ENU value|  
|-------------------|---------------|  
|Text000|The filters are:\\|  
  
```  
CustLedgerEntry.SETRANGE(Amount, -100, 100);  
CustLedgerEntry.SETRANGE("Posting Date", 010108D, 123108D);  
Str := CustLedgerEntry.GETFILTERS;  
MESSAGE(Text000 + '%1', Str);  
```  
  
 On a computer with the regional format set to English \(United States\), the message window displays the following:  
  
 **The filters are:**  
  
 **Posting Date: 01/01/08..12/31/08, Amount: -100..100**  
  
## Example 2
 This example requires that you create the following variable in the C/AL Globals window.  
  
|Variable name|DataType|Subtype|  
|-------------------|--------------|-------------|  
|Item|Record|Item|  
  
```  
Item.FILTERGROUP(2); // Filter group 2 is applied.  
Item.SETFILTER("No.", '1000..1450'); // A filter is set in filter group 2.  
MESSAGE('Filtergroup 2 filters: ' + Item.GETFILTERS);   
// GETFILTERS prints the filter that is set in filter group 2  
  
Item.FILTERGROUP(0); // Change the current filter group.   
// Now filter group 0 is applied.  
MESSAGE('Filtergroup 0 filter: ' + Item.GETFILTERS);   
// GETFILTERS returns an empty string because there is no filter set   
// in the current filter group (0).  
Item.SETFILTER("No.", '70000..79999'); // Set another filter, now in filter group 0.  
MESSAGE('Now Filtergroup 0 filters: ' + Item.GETFILTERS);   
// GETFILTERS prints the new filter set in the filter group 0.  
```  
  
 The message windows display the following:  
  
 **Filtergroup 2 filters: No.: 1000..1450**  
  
 **Filtergroup 0 filters:**  
  
 **Now Filtergroup 0 filters: No.: 70000..79999**  
  
## See Also  
 [GETFILTER Function \(Record\)](GETFILTER-Function--Record-.md)   
 [SETFILTER Function \(Record\)](SETFILTER-Function--Record-.md)   
 [SETRANGE Function \(Record\)](SETRANGE-Function--Record-.md)   
 [FILTERGROUP Function \(Record\)](FILTERGROUP-Function--Record-.md)   
 [Record Data Type](Record-Data-Type.md)