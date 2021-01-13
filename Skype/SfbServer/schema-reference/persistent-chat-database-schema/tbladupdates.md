---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。
ms.openlocfilehash: 16bb393eb57e7aaf8d3fea7001157eaabbe70c52
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821383"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含後續 Active Directory 同步步驟尚未處理的 Active Directory 網域服務變更。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，非 null  <br/> |已變更之物件的主體 GUID。  <br/> |
|prinADPath  <br/> |Nvarchar (384) ，非 null  <br/> |物件的辨別名稱。  <br/> |
|prinAttributesChanged  <br/> |位元，非 null  <br/> |True 是表示如果物件的至少一個屬性已變更。  <br/> |
|prinMembersChanged  <br/> |位元，非 null  <br/> |True 是表示如果成員資格變更。  <br/> |
|prinAffiliationsChanged  <br/> |位元，非 null  <br/> |不會使用。  <br/> |
|prinDeleted  <br/> |位元，非 null  <br/> |True 是表示如果物件已刪除。  <br/> |
|lastUpdated  <br/> |datetime，非 null  <br/> |插入列時的時間戳記。  <br/> |
   

