---
title: 商務用 Skype Server 中 Grant-CsOUPermission 所做的變更
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d744d352-1ad9-4447-8e2b-28e768d2ed1b
description: 若要委派商務用 Skype Server 管理，您可以將許可權新增至指定的組織單位 (ou) ，這樣樹系準備建立的 RTC 通用群組成員才能存取 ou，而不是 Domain Admins 群組的成員。
ms.openlocfilehash: fc537ed927e5eb430b4c379218b4400b6ab12761a272f37bba68a281481c9531
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54349715"
---
# <a name="changes-made-by-grant-csoupermission-in-skype-for-business-server"></a>商務用 Skype Server 中 Grant-CsOUPermission 所做的變更
 
若要委派商務用 Skype Server 管理，您可以將許可權新增至指定的組織單位 (ou) ，這樣樹系準備建立的 RTC 通用群組成員才能存取 ou，而不是 Domain Admins 群組的成員。 
  
**Grant-CsOuPermission** Cmdlet 會依照下表所指定的方式，將許可權授與指定之 OU 中的物件。
  
## <a name="granting-permission-for-user-objects"></a>授與使用者物件的許可權

當您為 OU 上的使用者物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。
  
**使用者物件的授與許可權**

|**Group**|**Permission**|**適用於**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |讀取 RTCUserSearchPropertySet  <br/> 讀取 RTCUserProvisioningPropertySet  <br/> 讀取 RTCPropertySet  <br/> 讀取 Public-Information  <br/> 讀取 General-Information  <br/> 讀取 User-Account-Restrictions  <br/> |子代使用者物件  <br/> |
|RTCUniversalUserAdmins  <br/> |寫入 RTCUserSearchPropertySet  <br/> 寫入 msExchUCVoiceMailSettings  <br/> 寫入 RTCUserProvisioningPropertySet  <br/> 寫入 RTCPropertySet  <br/> 寫入 proxyAddresses  <br/> |子代使用者物件  <br/> |
   
## <a name="granting-permission-for-computer-objects"></a>授與電腦物件的許可權

當您為 OU 上的電腦物件執行 **Grant-CsOuPermission** Cmdlet 時，系統會將群組授與下表所示的許可權。
  
**電腦物件的授與許可權**

|**Group**|**Permission**|**適用於**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |讀取 Public-Information  <br/> 讀取 Validated-DNS-Host-Name  <br/> |子代電腦物件  <br/> |
|RTCUniversalUserAdmins  <br/> |讀取 Public-Information  <br/> 讀取 Validated-DNS-Host-Name  <br/> |子代電腦物件  <br/> |
   
## <a name="granting-permission-for-contact-or-appcontact-objects"></a>授與連絡人或 AppContact 物件的許可權

當您對 OU 上的連絡人物件或 AppContact 物件執行 **Grant-CsOuPermission** Cmdlet 時，會授與下表所示的許可權。
  
**授與連絡人或 AppContact 物件的許可權**

|**Group**|**Permission**|**適用於**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |讀取 RTCUserSearchPropertySet  <br/> 讀取 RTCUserProvisioningPropertySet  <br/> 讀取 RTCPropertySet  <br/> 讀取 Public-Information  <br/> 讀取 General-Information  <br/> 讀取 Personal-Information  <br/> 讀取 User-Account-Restrictions  <br/> |子代連絡人物件  <br/> |
|RTCUniversalUserAdmins  <br/> |寫入 RTCUserSearchPropertySet  <br/> 寫入 otherIpPhone  <br/> 寫入 displayName  <br/> 寫入描述  <br/> 寫入 telephoneNumber  <br/> 寫入 msExchUCVoiceMailSettings  <br/> 寫入 RTCUserProvisioningPropertySet  <br/> 寫入 RTCPropertySet  <br/> 寫入 proxyAddresses  <br/> |子代連絡人物件  <br/> |
   
## <a name="granting-permission-for-device-objects"></a>授與裝置物件的許可權

當您為 OU 上的裝置物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。
  
**對 Device 物件授與的許可權**

|**Group**|**Permission**|**適用於**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |讀取 RTCUserSearchPropertySet  <br/> 讀取 RTCUserProvisioningPropertySet  <br/> 讀取 RTCPropertySet  <br/> 讀取 Public-Information  <br/> 讀取 Personal-Information  <br/> 讀取 General-Information  <br/> 讀取 User-Account-Restrictions  <br/> |子代連絡人物件  <br/> |
|RTCUniversalUserAdmins  <br/> |建立子項  <br/> 刪除子項  <br/> 刪除樹  <br/> |連絡人  <br/> |
|RTCUniversalUserAdmins  <br/> |寫入 displayName  <br/> 寫入描述  <br/> 寫入 telephoneNumber  <br/> |子代使用者物件  <br/> |
|RTCUniversalUserAdmins  <br/> |寫入 RTCUserSearchPropertySet  <br/> 寫入 otherIpPhone  <br/> 寫入 displayName  <br/> 寫入描述  <br/> 寫入 telephoneNumber  <br/> 寫入 msExchUCVoiceMailSettings  <br/> 寫入 RTCUserProvisioningPropertySet  <br/> 寫入 RTCPropertySet  <br/> 寫入 proxyAddresses  <br/> |子代連絡人物件  <br/> |
   
## <a name="granting-permission-for-inetorgperson-objects"></a>授與 InetOrgPerson 物件的許可權

當您為 OU 上的 InetOrgPerson 物件執行 **Grant-CsOuPermission** Cmdlet 時，會將許可權授與下表所示的許可權。
  
**InetOrgPerson 物件的授與許可權**

|**Group**|**Permission**|**適用於**|
|:-----|:-----|:-----|
|RTCHSUniversalServices  <br/> |複製目錄變更  <br/> |僅限這個物件  <br/> |
|RTCUniversalServerReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |清單內容  <br/> 讀取所有屬性  <br/> 讀取權限  <br/> |僅限這個物件  <br/> |
|RTCUniversalUserReadOnlyGroup  <br/> |讀取 RTCUserSearchPropertySet  <br/> 讀取 RTCUserProvisioningPropertySet  <br/> 讀取 RTCPropertySet  <br/> 讀取 Personal-Information  <br/> 讀取 Public-Information  <br/> 讀取 General-Information  <br/> 讀取 User-Account-Restrictions  <br/> |子代 inetOrgPerson 物件  <br/> |
|RTCUniversalUserAdmins  <br/> |寫入 RTCUserSearchPropertySet  <br/> 寫入 RTCUserProvisioningPropertySet  <br/> 寫入 RTCPropertySet  <br/> 寫入 proxyAddresses  <br/> |子代 inetOrgPerson 物件  <br/> |
   

