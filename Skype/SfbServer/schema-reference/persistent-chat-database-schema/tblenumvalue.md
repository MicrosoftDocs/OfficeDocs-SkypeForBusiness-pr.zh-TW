---
title: tblEnumValue
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是包含在節點表格中所使用之屬性的 Visibility 和行為值的硬編碼表格。
---

# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 是包含在節點表格中所使用之屬性的 Visibility 和行為值的硬編碼表格。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|valueID  <br/> |smallint，非 null  <br/> |值的識別碼。  <br/> |
|attributeID:  <br/> |smallint，非 null  <br/> |屬性的識別碼。  <br/> |
|attributeValue  <br/> |nvarchar (256)，非 null  <br/> |值的名稱。  <br/> |
   
**Keys**

|**欄**|**描述**|
|:-----|:-----|
|valueID  <br/> |主索引鍵。  <br/> |
|attributeID:  <br/> |在 tblEnumAttribute.attributeID 表格中查閱的外鍵。  <br/> |
   
**表格值**

|**valueID**|**attributeID:**|**attributeValue**|
|:-----|:-----|:-----|
|第  <br/> |1  <br/> |私人  <br/> |
|3   <br/> |1  <br/> |範圍  <br/> |
|4   <br/> |第  <br/> |正常  <br/> |
|5  <br/> |第  <br/> |禮堂  <br/> |
|6   <br/> |1  <br/> |打開  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblNode](tblnode.md)
