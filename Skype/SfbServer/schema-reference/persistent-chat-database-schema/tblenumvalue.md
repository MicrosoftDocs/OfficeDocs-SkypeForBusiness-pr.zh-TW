---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一種硬編碼資料表，其中包含在節點資料表中使用之屬性的可見度及行為值。
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814601"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 是一種硬編碼資料表，其中包含在節點資料表中使用之屬性的可見度及行為值。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|valueID  <br/> |Smallint，not null  <br/> |值的識別碼。  <br/> |
|attributeID  <br/> |Smallint，not null  <br/> |屬性識別碼。  <br/> |
|attributeValue  <br/> |Nvarchar （256），not null  <br/> |值的名稱。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|valueID  <br/> |主鍵。  <br/> |
|attributeID  <br/> |在 tblEnumAttribute attributeID 資料表中使用 [查閱] 的外鍵。  <br/> |
   
**資料表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|2  <br/> |1  <br/> |私有  <br/> |
|3  <br/> |1  <br/> |討論  <br/> |
|4  <br/> |2  <br/> |標準  <br/> |
|500  <br/> |2  <br/> |auditorium  <br/> |
|6  <br/> |1  <br/> |開啟  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblNode](tblnode.md)
