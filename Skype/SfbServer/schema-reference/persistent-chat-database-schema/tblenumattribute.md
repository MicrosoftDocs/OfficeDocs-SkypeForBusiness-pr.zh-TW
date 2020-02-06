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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一種硬編碼資料表，其中包含在節點資料表中使用的 Visibility 和行為屬性。
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814611"
---
# <a name="tblenumattribute"></a>tblEnumAttribute
 
tblEnumAttribute 是一種硬編碼資料表，其中包含在節點資料表中使用的 Visibility 和行為屬性。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|attributeID  <br/> |Smallint，not null  <br/> |屬性識別碼。  <br/> |
|attributeName  <br/> |Nvarchar （256），not null  <br/> |屬性的名稱。  <br/> |
   
**機碼**

|**左欄**|**說明**|
|:-----|:-----|
|attributeID  <br/> |主鍵。  <br/> |
   
**資料表值**

|**attributeID**|**attributeName**|
|:-----|:-----|
|1  <br/> |看見.  <br/> |
|2  <br/> |行為.  <br/> |
   
## <a name="see-also"></a>另請參閱

[tblNode](tblnode.md)
