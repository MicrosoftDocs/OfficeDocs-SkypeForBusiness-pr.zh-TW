---
title: tblPrincipalMemberDifference
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
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference 包含的群組成員資格變更 (新增及移除的成員，) 後來的 Active Directory 網域服務同步步驟尚未處理。
ms.openlocfilehash: c1d5a0d492d228b5a8292fde608fbd66c3b586c393aba8eb5bc0fbbddd45a5e2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54276578"
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
   

