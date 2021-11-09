---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 表格是一種硬式編碼的表格，其中含有節點表格中所用的可見度及行為屬性。
ms.openlocfilehash: a2d2fa1eacac79784e20f137a037d672fa9eaa87
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856440"
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
