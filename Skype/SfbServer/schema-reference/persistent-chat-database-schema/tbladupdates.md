---
title: tblADUpdates
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
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含 Active Directory 網域服務的變更，這些變更尚未經過後續的 Active Directory 同步處理步驟使用。
ms.openlocfilehash: 6d50e065bd10e11383f606b2a4dfed0d5584cd1e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814681"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含 Active Directory 網域服務的變更，這些變更尚未經過後續的 Active Directory 同步處理步驟使用。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，不是 null  <br/> |已變更之物件的主要 GUID。  <br/> |
|prinADPath  <br/> |Nvarchar （384），not null  <br/> |物件的判別名。  <br/> |
|prinAttributesChanged  <br/> |bit、not null  <br/> |如果物件至少有一個屬性已變更，則為 True。  <br/> |
|prinMembersChanged  <br/> |bit、not null  <br/> |如果成員資格變更，則為 True。  <br/> |
|prinAffiliationsChanged  <br/> |bit、not null  <br/> |不使用。  <br/> |
|prinDeleted  <br/> |bit、not null  <br/> |如果已刪除物件，則為 True。  <br/> |
|lastUpdated  <br/> |datetime、not null  <br/> |插入列的時間戳記。  <br/> |
   

