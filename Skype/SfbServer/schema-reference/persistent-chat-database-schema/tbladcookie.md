---
title: tblADCookie
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
ms.assetid: 0a9102c4-47aa-40ea-8a0d-20e72ab09848
description: tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。
ms.openlocfilehash: 770900c7ad5e31173a9e62ea3eb5a8c711afca98
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/04/2021
ms.locfileid: "60743169"
---
# <a name="tbladcookie"></a>tblADCookie
 
tblADCookie 包含目前的輕量型目錄存取通訊協定 (LDAP) 同步處理 Cookie。
  
**Columns**

|**欄**|**類型**|**描述**|
|:-----|:-----|:-----|
|prinGuid  <br/> |GUID，非 null  <br/> |受監控網域的主體 GUID。  <br/> |
|prinDCHost  <br/> |nvarchar(255)  <br/> |用於 Active Directory 網域服務同步處理的目前網域控制站 (FQDN) 的完整功能變數名稱。具有資訊性值。  <br/> |
|adcContent  <br/> |影像 (二進位)  <br/> |Active Directory 同步處理 Cookie。  <br/> |
|lastUpdated  <br/> |datetime  <br/> |含有列更新時間的時間戳記。  <br/> |
|lockedUntil  <br/> |datetime  <br/> |鎖定列以進行變更的時間。這是軟體聯鎖機制的一部分，可確保一次僅有一個聊天服務會進行 Active Directory 同步處理。  <br/> |
   
**Keys**

|**欄 (s)**|**描述**|
|:-----|:-----|
|prinGuid  <br/> |主索引鍵。  <br/> |
|prinGuid  <br/> |在 Principal.prinID 表格中查閱外部索引鍵。  <br/> |
   

