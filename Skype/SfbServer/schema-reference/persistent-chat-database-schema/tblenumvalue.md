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
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一種硬編碼資料表, 其中包含在節點資料表中使用之屬性的可見度及行為值。
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192738"
---
# <a name="tblenumvalue"></a>tblEnumValue
 
tblEnumValue 是一種硬編碼資料表, 其中包含在節點資料表中使用之屬性的可見度及行為值。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|valueID  <br/> |Smallint, not null  <br/> |值的識別碼。  <br/> |
|attributeID  <br/> |Smallint, not null  <br/> |屬性識別碼。  <br/> |
|attributeValue  <br/> |Nvarchar (256), not null  <br/> |值的名稱。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|valueID  <br/> |主鍵。  <br/> |
|attributeID  <br/> |在 tblEnumAttribute attributeID 資料表中使用 [查閱] 的外鍵。  <br/> |
   
**資料表值**

|**valueID**|**attributeID**|**attributeValue**|
|:-----|:-----|:-----|
|pplx-2  <br/> |sr-1  <br/> |私有  <br/> |
|3  <br/> |sr-1  <br/> |討論  <br/> |
|4  <br/> |pplx-2  <br/> |標準  <br/> |
|500  <br/> |pplx-2  <br/> |auditorium  <br/> |
|6  <br/> |sr-1  <br/> |開啟  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblNode](tblnode.md)
