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
localization_priority: Normal
ms.assetid: ba19fa16-4d2d-4635-ac32-f93e09469546
description: tblADUpdates 包含 Active Directory 網域服務的變更, 這些變更尚未經過後續的 Active Directory 同步處理步驟使用。
ms.openlocfilehash: 3e7788db170539f888923a4600392e19022bbb0e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192754"
---
# <a name="tbladupdates"></a>tblADUpdates
 
tblADUpdates 包含 Active Directory 網域服務的變更, 這些變更尚未經過後續的 Active Directory 同步處理步驟使用。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, 不是 null  <br/> |已變更之物件的主要 GUID。  <br/> |
|prinADPath  <br/> |Nvarchar (384), not null  <br/> |物件的判別名。  <br/> |
|prinAttributesChanged  <br/> |bit、not null  <br/> |如果物件至少有一個屬性已變更, 則為 True。  <br/> |
|prinMembersChanged  <br/> |bit、not null  <br/> |如果成員資格變更, 則為 True。  <br/> |
|prinAffiliationsChanged  <br/> |bit、not null  <br/> |不使用。  <br/> |
|prinDeleted  <br/> |bit、not null  <br/> |如果已刪除物件, 則為 True。  <br/> |
|lastUpdated  <br/> |datetime、not null  <br/> |插入列的時間戳記。  <br/> |
   

