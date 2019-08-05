---
title: tblADCookie
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含目前的輕型目錄存取通訊協定 (LDAP) 同步處理 cookie。
ms.openlocfilehash: d75b1dc90d36aa0535fdac62b9e1a7061694cc76
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192759"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie 包含目前的輕型目錄存取通訊協定 (LDAP) 同步處理 cookie。
  
**分欄**

|**左欄**|**類型**|**說明**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID, 不是 null  <br/> |受監視之網域的主要 GUID。  <br/> |
|prinDCHost  <br/> |Nvarchar (255)  <br/> |用於 Active Directory 網域服務同步處理之目前網網域控制站的完整功能變數名稱 (FQDN)。有資訊值。  <br/> |
|adcContent  <br/> |image (二進位)  <br/> |Active Directory 同步處理 cookie。  <br/> |
|lastUpdated  <br/> |datetime  <br/> |含有資料列更新時間的時間戳記。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |[時間], 直到列鎖定變更為止。 這是軟體互鎖機制的一部分, 可確保一次只有其中一個聊天服務進行 Active Directory 同步處理。  <br/> |
   
**鍵**

|**欄 (s)**|**說明**|
|:-----|:-----|
|prinGuid  <br/> |主鍵。  <br/> |
|prinGuid  <br/> |PrinGuid 表格中的 [查閱] 外鍵。  <br/> |
   

