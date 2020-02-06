---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必須從 Active Directory 網域服務更新的主體。
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813571"
---
# <a name="tblprincipalmeta"></a>tblPrincipalMeta
 
tblPrincipalMeta 包含必須從 Active Directory 網域服務更新的主體。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinID  <br/> |int，not null  <br/> |Principal ID。  <br/> |
|prinAffiliationsDirty  <br/> |bit、not null  <br/> |如果必須重新整理承擔者隸屬關係，則為 True。  <br/> |
|prinAttributesDirty  <br/> |bit、not null  <br/> |如果必須重新整理主體屬性，則為 True。  <br/> |
|prinDeleted  <br/> |bit、not null  <br/> |如果主體已遭刪除，則為 True。  <br/> |
|tryCount  <br/> |int  <br/> |嘗試從目前已發生過的 AD DS 重新整理主體的次數。  <br/> |
|lastTry  <br/> |datetime  <br/> |從最新嘗試重新整理主體的時間戳記。 如果尚未嘗試重新整理，則可以是 null。  <br/> |
|nextTry  <br/> |datetime  <br/> |下一次排程重新整理的時間戳記。 如果沒有排程進一步的重新整理，就可以是 null。  <br/> |
   
**鍵**

|**左欄**|**說明**|
|:-----|:-----|
|prinID  <br/> |主鍵。  <br/> |
|prinID  <br/> |在 tblPrincipal prinID 資料表中使用 [查閱] 的外鍵。  <br/> |
   

