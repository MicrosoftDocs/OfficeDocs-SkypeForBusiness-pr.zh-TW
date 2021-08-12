---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。
ms.openlocfilehash: 6996c95ca170082ec89ac7d8fd92648b60c933b1fd72515bb7c3974df8cd5e92
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54337581"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|attributeID:  <br/> |smallint，非 null  <br/> |屬性的識別碼。  <br/> |
|attributeName  <br/> |nvarchar (256)，非 null  <br/> |屬性名稱。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|attributeID:  <br/> |主索引鍵。  <br/> |
   
**表格值**

|**attributeID:**|**attributeName**|
|:-----|:-----|
|1  <br/> |可見度。  <br/> |
|第  <br/> |行為。  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblNode](tblnode.md)
