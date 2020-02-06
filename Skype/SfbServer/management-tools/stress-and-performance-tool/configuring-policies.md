---
title: 設定商務用 Skype Server 2015 應力與效能工具的原則
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 商務用 Skype Server 2015 應力與效能工具的原則設定。
ms.openlocfilehash: bfdf0d9875a37f7f4a1f98aa24cd6fd5c3176a00
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816192"
---
# <a name="configuring-policies-for-the-skype-for-business-server-2015-stress-and-performance-tool"></a>設定商務用 Skype Server 2015 應力與效能工具的原則
 
商務用 Skype Server 2015 應力與效能工具的原則設定。
  
在執行壓力與效能工具之前，您可以在商務用 Skype Server 2015 中設定數個原則和其他區域：
  
- [存檔原則](configuring-policies.md#ArchivingPolicy)
    
- [會議原則](configuring-policies.md#ConferencingPolicy)
    
- [連絡人原則](configuring-policies.md#ContactsPolicy)
    
- [同盟原則](configuring-policies.md#FederationPolicy)
    
- [呼叫許可控制原則](configuring-policies.md#CACPolicy)
    
- [語音路由規則](configuring-policies.md#VoiceRoutingRules)
    
- [會議助理應用程式](configuring-policies.md#ConfAttendantApp)
    
- [伺服器通話駐留服務](configuring-policies.md#ServerCallParkServ)
    
- [緊急通話](configuring-policies.md#EmergencyCalls)
    
- [配置回應群組應用程式](configuring-policies.md#ConfigResponseGroupApp)
    
## <a name="archiving-policy"></a>存檔原則
<a name="ArchivingPolicy"> </a>

如果您在商務用 Skype Server 拓撲結構中部署了封存伺服器，您可以查看 ArchivingPolicy. ps1 腳本。 如果您需要進一步協助，請查看 [封存] 和 [Web 會議] Cmdlet。
  
## <a name="conferencing-policy"></a>會議原則
<a name="ConferencingPolicy"> </a>

對於會議，我們有 MeetingPolicy. ps1 腳本。 如果您需要進一步協助，請查看網路會議 Cmdlet。
  
## <a name="contacts-policy"></a>連絡人原則
<a name="ContactsPolicy"> </a>

ContactsPolicy. ps1 腳本將是您需要檢查的範例。 如果您需要進一步參考，IM 和目前狀態 Cmdlet 會有所説明。
  
## <a name="federation-policy"></a>同盟原則
<a name="FederationPolicy"> </a>

同盟的範例腳本是 FederationPolicy. ps1........。 若要查看的 Cmdlet （如果您需要進一步瞭解）將會是 Edge 伺服器、同盟和外部存取。
  
## <a name="call-admission-control-policy"></a>呼叫許可控制原則
<a name="CACPolicy"> </a>

您可以參考此原則的 BandwidthPolicy. ps1。 通話許可控制 Cmdlet 也會有進一步的資訊。
  
## <a name="voice-routing-rules"></a>語音路由規則
<a name="VoiceRoutingRules"> </a>

您需要 RoutingRules. ps1 語音路由範例腳本。 當您設定這些規則時，請記下電話內容（也就是/Location 設定檔或/SimpleName）及內部/外部區功能變數代碼，以便在建立使用者時加以指定。 在 LyncPerfTool 設定期間，您也需要他們（特別是 PSTN UC 與 UC）。
  
例如，RoutingRules. ps1 中的**CsDialPlan** Cmdlet 呼叫中的 SimpleName 參數應該用於 UserProfileGenerator 中下圖中的 LocationProfile 值 ..：
  
![商務用 Skype 負載組態工具、語音案例索引標籤、交談的高級設定。](../../media/59f42e4e-8f1e-4d43-9ae2-9e6026191951.png)
  
如需詳細資訊，您可以查看企業語音 Cmdlet。
  
## <a name="conference-attendant-application"></a>會議助理應用程式
<a name="ConfAttendantApp"> </a>

首先，請複習 ConferenceAutoAttendantConfiguration. ps1 腳本。 您會想記下 ConferencingAutoAttendant 的電話號碼（預設為1121111111），以便將它輸入到 LyncPerfTool 設定工具中以進行配置產生，如下所示：
  
![[語音案例] 索引標籤顯示會議載入等級和電話號碼。](../../media/a3ea5fc0-8b3d-4842-b809-f137f470dbdc.png)
  
您可以在會議和電話撥入式會議 Cmdlet 中找到更多詳細資料。
  
## <a name="server-call-park-service"></a>伺服器通話駐留服務
<a name="ServerCallParkServ"> </a>

預設會停用此功能。 您可以查看 CallParkConfiguration. ps1 範例腳本（如果您需要測試此選項）。 此外，視需要查看通話寄存應用程式 Cmdlet。
  
## <a name="emergency-calls"></a>緊急通話
<a name="EmergencyCalls"> </a>

您需要執行下列步驟來設定緊急通話的壓力與效能測試：
  
1. 設定緊急通話的語音路線。 您可以使用 RoutingRules. ps1 腳本，然後檢查 [**路由 E911 至 PSTN** ] 批註，以取得如何設定此語音路由的範例。
    
    > [!CAUTION]
    > RoutingRules 中的範例命令有一個數位模式，其中包含數位119，而不是911。 您應該避免使用911（或您的實際當地緊急號碼）來避免在負載測試期間意外呼叫本機緊急操作員。 請記住，此設定僅適用于模擬目的！ 
  
2. 透過在 UserProvisioningTool 中的**位置資訊服務 [配置**] 索引標籤上填入值來設定位址，如下圖所示：
    
     ![[使用者供給] 工具，顯示位址數量、子網、切換和埠數。](../../media/ebe85a0c-750f-4301-97d4-d158a40ea98a.png)
  
3. 當您在 UserProvisioningTool 中輸入所有專案時，請按一下 [**產生 .lis 使用者配置**檔案] 按鈕。
    
4. 現在會產生用於埠、子網、開關和無線存取點（WAPs）的 CSV 檔案，以及用於壓力與效能工具的 XML 檔案。 將位置資訊服務（.LIS）與 LisConfiguration. ps1 腳本進行設定時，您可以使用 CSV 檔案進行輸入。 若要這樣做，您需要將 Locations0 檔案移至與壓力和效能工具可執行檔（LyncPerfTool）相同的資料夾。 這可讓您執行位置設定檔（撥號方案）案例。
    
## <a name="configuring-response-group-application"></a>配置回應群組應用程式
<a name="ConfigResponseGroupApp"> </a>

範例腳本為 ResponseGroupConfiguration. ps1........。 還有回應群組應用程式 Cmdlet 可供您審查進一步的配置詳細資料。 下列圖表會顯示一些配置詳細資料：
  
![回應群組的 [config] 工具，顯示測試的現有工作流程。](../../media/e218a345-4813-4332-8cff-b48de05017ef.jpg)
  

