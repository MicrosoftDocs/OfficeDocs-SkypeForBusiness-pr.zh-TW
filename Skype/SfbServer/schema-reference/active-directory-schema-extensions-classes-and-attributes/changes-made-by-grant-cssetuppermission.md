---
title: 在商務用 Skype Server 中由 Grant CsSetupPermission 所做的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 若要委派設定, 您可以為特定 Active Directory 組織單位 (OU) 授予 RTCUniversalServerAdmins 通用群組的許可權, 讓該 OU 中的 RTCUniversalServerAdmins 群組成員安裝商務用 Skype Server指定的網域, 而不是網域管理員群組的成員。
ms.openlocfilehash: a7cbf49fa7d34b8a81668c4ec598e3a547c098e9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192919"
---
# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>在商務用 Skype Server 中由 Grant CsSetupPermission 所做的變更
 
若要委派設定, 您可以為特定 Active Directory 組織單位 (OU) 授予 RTCUniversalServerAdmins 通用群組的許可權, 讓該 OU 中的 RTCUniversalServerAdmins 群組成員安裝商務用 Skype Server指定的網域, 而不是網域管理員群組的成員。 
  
CsSetupPermission Cmdlet 會**授**與組織單位上的 RTCUniversalServerAdmins 群組許可權, 如下表所示:
  
**在 OU 中授與物件的許可權**

|**許可權適用于:**|**已授與許可權:**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊存取: <br/>  Read servicePrincipalName <br/>  撰寫 servicePrincipalName <br/>  刪除樹 <br/>  複製目錄變更 <br/> |
|後代 serviceConnectionPoint 物件  <br/> | 特殊存取: <br/>  讀取權限 <br/>  寫入權限 <br/>  建立子系 <br/>  刪除子系 <br/>  清單內容 <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-伺服器物件  <br/> | 特殊存取: <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-WebComponents 物件  <br/> | 特殊存取: <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-MCU 物件  <br/> | 特殊存取: <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-MediationServer 物件  <br/> | 特殊存取: <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-ApplicationServer 物件  <br/> | 特殊存取: <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-ConnectionPoint 物件  <br/> | 特殊存取: <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|後代電腦物件  <br/> | 用於 serviceConnectionPoint 的特殊存取: <br/>  建立子物件 <br/>  刪除子物件 <br/>  刪除樹 <br/>  公用資訊的特殊存取權: <br/>  Read 屬性 <br/>  DNS 主機名稱的特殊存取權: <br/>  Read 屬性 <br/> |
   

