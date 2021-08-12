---
title: 設定商務用 Skype Server 2015 壓力和效能工具的原則
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 11/11/2015
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 7e1435e2-d073-4265-8067-ebcb5bf28835
description: 商務用 Skype Server 2015 應力和效能工具的原則設定。
ms.openlocfilehash: 0a7e93e0e6a25195b1e9723ce6eb31b4c9f9fbd200d390f225a2be29c4106b0a
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333185"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>設定商務用 Skype Server 2015 壓力和效能工具的原則
 
商務用 Skype Server 2015 應力和效能工具的原則設定。
  
在執行壓力和效能工具之前，您可以在商務用 Skype Server 2015 中設定數個原則及其他區域：
  
- [封存原則](configuring-policies.md#ArchivingPolicy)
    
- [會議原則](configuring-policies.md#ConferencingPolicy)
    
- [連絡人原則](configuring-policies.md#ContactsPolicy)
    
- [同盟原則](configuring-policies.md#FederationPolicy)
    
- [通話許可控制原則](configuring-policies.md#CACPolicy)
    
- [語音路由規則](configuring-policies.md#VoiceRoutingRules)
    
- [會議助理應用程式](configuring-policies.md#ConfAttendantApp)
    
- [伺服器呼叫駐留服務](configuring-policies.md#ServerCallParkServ)
    
- [緊急通話](configuring-policies.md#EmergencyCalls)
    
- [設定回應群組應用程式](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>封存原則
<a name="ArchivingPolicy"> </a>

如果您已在商務用 Skype Server 拓撲中部署封存伺服器，則可以查看 ArchivingPolicy.ps1 腳本。 如果您需要進一步協助，請參閱封存和 Web 會議 Cmdlet。
  
## <a name="conferencing-policy"></a>會議原則
<a name="ConferencingPolicy"> </a>

若為會議，我們有 MeetingPolicy.ps1 腳本。 如果您需要進一步協助，請參閱 Web 會議 Cmdlet。
  
## <a name="contacts-policy"></a>連絡人原則
<a name="ContactsPolicy"> </a>

ContactsPolicy.ps1 腳本將會是您需要複習的範例。 如果您需要進一步參考，IM 和目前狀態 Cmdlet 會有所説明。
  
## <a name="federation-policy"></a>同盟原則
<a name="FederationPolicy"> </a>

同盟的範例腳本是 FederationPolicy.ps1。 若您需要深入瞭解，請複查 Cmdlet，將會是 Edge Server、同盟和外部存取。
  
## <a name="call-admission-control-policy"></a>通話許可控制原則
<a name="CACPolicy"> </a>

您可以參照此原則的 BandwidthPolicy.ps1。 通話許可控制 Cmdlet 也會有進一步的資訊。
  
## <a name="voice-routing-rules"></a>語音路由規則
<a name="VoiceRoutingRules"> </a>

您需要語音路由的 RoutingRules.ps1 範例腳本。 當您設定這些規則時，請記下電話內容 (，也就是/Location 設定檔或/SimpleName) 和內部/外部區功能變數代碼，如此一來，您就可以在建立使用者時進行指定。 您也需要在 LyncPerfTool 設定 (期間特別針對 PSTN UC 和 UC-PSTN) 。
  
例如，在 RoutingRules.ps1 範例中對 **get-csdialplan 指令程式** 的呼叫中，SimpleName 參數應該用於下列 UserProfileGenerator.exe 中的 microsoft.rtc.management.writableconfig.policy.voice.locationprofile 值：
  
![商務用 Skype 載入設定工具、語音案例] 索引標籤、[交談] 的高級設定。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
如需詳細資訊，您可以複查企業語音 Cmdlet。
  
## <a name="conference-attendant-application"></a>會議助理應用程式
<a name="ConfAttendantApp"> </a>

請先複查 ConferenceAutoAttendantConfiguration.ps1 腳本。 您會想記下 ConferencingAutoAttendant 的電話號碼 (1121111111 預設) ，所以您可以將它輸入 LyncPerfTool 設定工具進行設定產生，如下所示：
  
![語音案例] 索引標籤顯示會議的負載層級和電話號碼。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
您會在會議和電話撥入式會議 Cmdlet 中找到更多詳細資料。
  
## <a name="server-call-park-service"></a>伺服器呼叫駐留服務
<a name="ServerCallParkServ"> </a>

這實際上會預設為停用。 您可以在需要測試時，複查 CallParkConfiguration.ps1 範例腳本。 此外，視需要取出通話駐留應用程式 Cmdlet。
  
## <a name="emergency-calls"></a>緊急通話
<a name="EmergencyCalls"> </a>

您必須執行下列步驟，為緊急通話設定壓力和效能測試：
  
1. 設定緊急通話的語音路由。 您可以使用 RoutingRules.ps1 腳本，然後查看批註「 **路由 E911 至 PSTN** 」，以取得如何設定此語音路由的範例。
    
    > [!CAUTION]
    > RoutingRules.ps1 的範例命令具有數位模式，其中包含數位119，而不是911。 您應避免使用 911 (或實際的本機緊急號碼，) 以避免在負載測試期間意外呼叫本機緊急操作員。 請記住，此設定只是用於類比目的！ 
  
2. 填寫 UserProvisioningTool 中的 [ **位置資訊服務配置** ] 索引標籤上的值以設定位址，如下圖所示：
    
     ![使用者布建工具，顯示位址、子網、交換器和埠的數目。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 當您已在 UserProvisioningTool 中輸入內容時，請按一下 [ **產生 .lis 的 Config Files** ] 按鈕。
    
4. 現在會產生壓力和效能工具 (Wap) 的埠、子網、交換器和無線存取點的 CSV 檔案。 設定 Location 資訊服務 (.LIS) 使用 LisConfiguration.ps1 腳本時，您可以使用 CSV 檔案進行輸入。 若要這麼做，您必須將 Locations0.xml 檔案移至與壓力和效能工具可執行檔 (LyncPerfTool.exe) 相同的資料夾。 這可讓您執行位置設定檔 (撥號對應表) 案例。
    
## <a name="configuring-response-group-application"></a>設定回應群組應用程式
<a name="ConfigResponseGroupApp"> </a>

範例腳本是 ResponseGroupConfiguration.ps1。 還有其他的回應群組應用程式 Cmdlet 可供您複查，以取得進一步的設定詳細資料。 下列圖表會顯示部分設定的詳細資料：
  
![回應群組 config 工具，顯示用於測試的現有工作流程。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

