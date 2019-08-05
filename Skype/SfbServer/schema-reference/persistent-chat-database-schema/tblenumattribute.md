---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一種硬編碼資料表, 其中包含在節點資料表中使用的 Visibility 和行為屬性。
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192739"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一種硬編碼資料表, 其中包含在節點資料表中使用的 Visibility 和行為屬性。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|attributeID  <br/> |Smallint, not null  <br/> |屬性識別碼。  <br/> |
|attributeName  <br/> |Nvarchar (256), not null  <br/> |屬性的名稱。  <br/> |
   
**快速鍵**

|**左欄**|**說明**|
|:-----|:-----|
|attributeID  <br/> |主鍵。  <br/> |
   
**資料表值**

|**attributeID**|**attributeName**|
|:-----|:-----|
|sr-1  <br/> |看見.  <br/> |
|pplx-2  <br/> |行為.  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblNode](tblnode.md)
