---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含的群組成員資格變更 (新增及移除的成員，) 後來的 Active Directory 網域服務同步步驟尚未處理。
ms.openlocfilehash: 884f1450b74300ad2915c27b524dc0419c97062d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743159"
---
# <a name="tblprincipalmemberdifference"></a>tblPrincipalMemberDifference
 
tblPrincipalMemberDifference 包含的群組成員資格變更 (新增及移除的成員，) 後來的 Active Directory 網域服務同步步驟尚未處理。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，非 null  <br/> |已變更群組的主體 GUID。  <br/> |
|memberADPath  <br/> |nvarchar(256)  <br/> |成員的辨別名稱。  <br/> |
|memberRemoved  <br/> |bit，非 null  <br/> |False 表示已新增成員；True 表示已移除成員。  <br/> |
   
**機碼**

|**欄**|**描述**|
|:-----|:-----|
|\<prinGuid, memberADPath\>  <br/> |主索引鍵。  <br/> |
   

