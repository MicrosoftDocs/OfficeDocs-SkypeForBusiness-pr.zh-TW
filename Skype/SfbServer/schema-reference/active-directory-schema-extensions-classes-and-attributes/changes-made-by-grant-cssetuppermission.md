---
title: 商務用 Skype Server 中 Grant-CsSetupPermission 所做的變更
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: c5801f48-14e3-4fdd-8f14-d52e7af07a57
description: 若要委派設定，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 ou 中 RTCUniversalServerAdmins 群組的成員，以在不是 domain Admins 群組成員的情況下，在指定的網域中安裝商務用 Skype Server。
---

# <a name="changes-made-by-grant-cssetuppermission-in-skype-for-business-server"></a>商務用 Skype Server 中 Grant-CsSetupPermission 所做的變更
 
若要委派設定，您可以將許可權授與特定 Active Directory 組織單位 (OU) 的 RTCUniversalServerAdmins 通用群組，啟用該 ou 中 RTCUniversalServerAdmins 群組的成員，以在不是 domain Admins 群組成員的情況下，在指定的網域中安裝商務用 Skype Server。 
  
**Grant-CsSetupPermission** Cmdlet 會授與組織單位上的 RTCUniversalServerAdmins 群組許可權，如下表所指定：
  
**授與 OU 中物件的許可權**

|**許可權適用于：**|**授與的許可權：**|
|:-----|:-----|
|RTCUniversalServerAdmins  <br/> | 特殊存取權： <br/>  讀取 servicePrincipalName <br/>  寫入 servicePrincipalName <br/>  刪除樹 <br/>  複製目錄變更 <br/> |
|子代 serviceConnectionPoint 物件  <br/> | 特殊存取權： <br/>  讀取權限 <br/>  寫入權限 <br/>  建立子項 <br/>  刪除子項 <br/>  清單內容 <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-Server 物件  <br/> | 特殊存取權： <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-WebComponents 物件  <br/> | 特殊存取權： <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-MCU 物件  <br/> | 特殊存取權： <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-MediationServer 物件  <br/> | 特殊存取權： <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-ApplicationServer 物件  <br/> | 特殊存取權： <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代 msRTCSIP-ConnectionPoint 物件  <br/> | 特殊存取權： <br/>  Write 屬性 <br/>  Read 屬性 <br/>  刪除樹 <br/> |
|子代電腦物件  <br/> | ServiceConnectionPoint 的特殊存取權： <br/>  建立子物件 <br/>  刪除子物件 <br/>  刪除樹 <br/>  公用資訊的特殊存取權： <br/>  Read 屬性 <br/>  DNS 主機名稱的特殊存取權： <br/>  Read 屬性 <br/> |
   

