---
title: 在商務用 Skype Server 中由 Grant CsOUPermission 所做的變更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 若要委派商務用 Skype Server 管理，您可以在指定的組織單位（Ou）中新增許可權，讓「林準備」建立的 RTC 通用群組成員可以存取 Ou，而不會成為網域系統管理員群組的成員。
ms.openlocfilehash: 8342d1801d2df91f940f02e8bfc05c3c5b91c4ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815521"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>在商務用 Skype Server 中由 Grant CsOUPermission 所做的變更
 
若要委派商務用 Skype Server 管理，您可以在指定的組織單位（Ou）中新增許可權，讓「林準備」建立的 RTC 通用群組成員可以存取 Ou，而不會成為網域系統管理員群組的成員。 
  
**Grant CsOuPermission** Cmdlet 會根據下表中的指定，將許可權授與指定 OU 中的物件。
  
## <a name="granting-permission-for-user-objects"></a>授與使用者物件的許可權

當您針對 OU 中的使用者物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。
  
**授與使用者物件的許可權**

|**群組**|**拒絕**|**適用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |閱讀 RTCUserSearchPropertySet  <br/> 閱讀 RTCUserProvisioningPropertySet  <br/> 閱讀 RTCPropertySet  <br/> 閱讀公用資訊  <br/> 閱讀一般資訊  <br/> 閱讀使用者-帳戶限制  <br/> |後代使用者物件  <br/> |
|RTCUniversalUserAdmins  <br/> |撰寫 RTCUserSearchPropertySet  <br/> 撰寫 msExchUCVoiceMailSettings  <br/> 撰寫 RTCUserProvisioningPropertySet  <br/> 撰寫 RTCPropertySet  <br/> 撰寫 proxyAddresses  <br/> |後代使用者物件  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>授與電腦物件的許可權

當您針對 OU 中的電腦物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。
  
**授與電腦物件的許可權**

|**群組**|**拒絕**|**適用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |閱讀公用資訊  <br/> 已驗證閱讀-DNS 主機名稱  <br/> |後代電腦物件  <br/> |
|RTCUniversalUserAdmins  <br/> |閱讀公用資訊  <br/> 已驗證閱讀-DNS 主機名稱  <br/> |後代電腦物件  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授予連絡人或 AppContact 物件的許可權

當您在 OU 上執行連絡人物件或 AppContact 物件的**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。
  
**授與連絡人或 AppContact 物件的許可權**

|**群組**|**拒絕**|**適用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |閱讀 RTCUserSearchPropertySet  <br/> 閱讀 RTCUserProvisioningPropertySet  <br/> 閱讀 RTCPropertySet  <br/> 閱讀公用資訊  <br/> 閱讀一般資訊  <br/> 閱讀個人資訊  <br/> 閱讀使用者-帳戶限制  <br/> |子代連絡人物件  <br/> |
|RTCUniversalUserAdmins  <br/> |撰寫 RTCUserSearchPropertySet  <br/> 撰寫 otherIpPhone  <br/> 寫入 displayName  <br/> 撰寫描述  <br/> 撰寫 Telephonenumber 相同  <br/> 撰寫 msExchUCVoiceMailSettings  <br/> 撰寫 RTCUserProvisioningPropertySet  <br/> 撰寫 RTCPropertySet  <br/> 撰寫 proxyAddresses  <br/> |子代連絡人物件  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>為裝置物件授與許可權

當您針對 OU 中的裝置物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。
  
**針對裝置物件所授的許可權**

|**群組**|**拒絕**|**適用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |閱讀 RTCUserSearchPropertySet  <br/> 閱讀 RTCUserProvisioningPropertySet  <br/> 閱讀 RTCPropertySet  <br/> 閱讀公用資訊  <br/> 閱讀個人資訊  <br/> 閱讀一般資訊  <br/> 閱讀使用者-帳戶限制  <br/> |子代連絡人物件  <br/> |
|RTCUniversalUserAdmins  <br/> |建立子系  <br/> 刪除子系  <br/> 刪除樹  <br/> |資訊  <br/> |
|RTCUniversalUserAdmins  <br/> |寫入 displayName  <br/> 撰寫描述  <br/> 撰寫 Telephonenumber 相同  <br/> |後代使用者物件  <br/> |
|RTCUniversalUserAdmins  <br/> |撰寫 RTCUserSearchPropertySet  <br/> 撰寫 otherIpPhone  <br/> 寫入 displayName  <br/> 撰寫描述  <br/> 撰寫 Telephonenumber 相同  <br/> 撰寫 msExchUCVoiceMailSettings  <br/> 撰寫 RTCUserProvisioningPropertySet  <br/> 撰寫 RTCPropertySet  <br/> 撰寫 proxyAddresses  <br/> |子代連絡人物件  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>授予 InetOrgPerson 物件的許可權

當您針對 OU 上的 InetOrgPerson 物件執行**Grant CsOuPermission** Cmdlet 時，系統會授與群組的許可權，如下表所示。
  
**授與 InetOrgPerson 物件的許可權**

|**群組**|**拒絕**|**適用于**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |閱讀 RTCUserSearchPropertySet  <br/> 閱讀 RTCUserProvisioningPropertySet  <br/> 閱讀 RTCPropertySet  <br/> 閱讀個人資訊  <br/> 閱讀公用資訊  <br/> 閱讀一般資訊  <br/> 閱讀使用者-帳戶限制  <br/> |子代 inetOrgPerson 物件  <br/> |
|RTCUniversalUserAdmins  <br/> |撰寫 RTCUserSearchPropertySet  <br/> 撰寫 RTCUserProvisioningPropertySet  <br/> 撰寫 RTCPropertySet  <br/> 撰寫 proxyAddresses  <br/> |子代 inetOrgPerson 物件  <br/> |
   

