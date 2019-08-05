---
title: 遷移至直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
appliesto:
- Microsoft Teams
description: 瞭解從商務用 Skype Online 和團隊設定觀點來決定要從商務用 Skype 移植所需的專案。
ms.openlocfilehash: 49980a0364e729fc41e6fe716de336a8a28f85bb
ms.sourcegitcommit: c554b09527817dc3e06b10509f6668b42ccc5cb9
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/17/2019
ms.locfileid: "36184848"
---
# <a name="migrate-to-direct-routing"></a>遷移至直接路由

本文說明從商務用 Skype Online 和 Microsoft 團隊設定觀點遷移到直接路由所需的專案。 本文涵蓋從以下各項進行遷移: 
 
- 含有通話方案的 Office 365 電話系統 (適用于團隊和商務用 Skype Online) 
- 在商務用 Skype Server (適用于商務用 Skype Online) 中使用內部部署 PSTN 連線的 Office 365 Phone 系統  
- 使用雲端連接器版本 (適用于商務用 Skype Online) 進行內部部署 PSTN 連線的 Office 365 Phone 系統

  
除了這些設定步驟之外, 還需要在會話邊界控制器 (SBC) 上進行設定, 以將呼叫路由至新的路線。 超出本檔範圍。 如需詳細資訊, 請參閱您的 SBC 供應商檔。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>針對各種 PSTN 連接選項的使用者預配結束狀態 

下表顯示使用者針對 Office 365 Phone 系統所選取之 PSTN 連線選項所提供之使用者的結束狀態。 只會顯示與語音相關的屬性。

|使用者物件屬性 |含有通話方案的電話系統|具有內部部署 PSTN 連線的電話系統 (透過商務用 Skype Server)|具有內部部署 PSTN 連線的電話系統 (透過雲端連接器)|具有內部部署 PSTN 連線的電話系統 (透過直接路由)|
|---|---|---|---|---|
|端|商務用 Skype 或團隊 |商務用 Skype |商務用 Skype |協同|
|許可證|商務用 Skype Online</br>方案2</br></br>MCOProfessional 或 MCOSTANDARD)</br></br></br>電話系統 (MCOEV)</br></br></br>通話方案</br>協同|商務用 Skype Online 方案 2 (MCOProfessional 或 MCOSTANDARD)</br></br></br>電話系統 (MCOEV)|商務用 Skype Online 方案 2 (MCOProfessional 或 MCOSTANDARD)</br></br></br>電話系統 (MCOEV)|商務用 Skype Online 方案 2 (MCOProfessional 或 MCOSTANDARD</br></br></br>電話系統 (MCOEV)</br></br>協同|
OnPremLineURI |N/A|電話號碼必須從內部部署的 AD 進行同步處理。 |您可以在內部部署的 Active Directory 或 Azure Active Directory 中管理電話號碼。|您可以在內部部署的 Active Directory 或 Azure Active Directory 中管理電話號碼。 不過, 如果組織有內部部署商務用 Skype, 該號碼必須從內部部署的 Active Directory 進行同步處理。|
|LineURI|PSTN 電話號碼|從 OnPremLineURI 參數自動設定|從 OnPremLineURI 參數自動設定|從 OnPremLineURI 參數自動設定|
|EnterpriseVoiceEnabled|滿足|滿足|滿足|滿足|
|HostedVoiceMail |滿足|滿足|滿足|滿足|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|具有值|具有值|具有值|N/A|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|具有值|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly、SfBOnly 或 Islands|$Null|$Null|孤島或 TeamsOnly|
|TeamsInterPolicy<sup>2</sup></br>CallingDefaultClient –請閱讀下列記事。|團隊或 SfB |SfB|SfB|協同|
|TeamsCallingPolicy</br>AllowPrivateCalling|滿足|N/A|N/A|滿足|
|TeamsCallingPolicy</br>AllowGroupCalling|滿足|N/A|N/A|滿足|
||||||

<sup>1</sup>選擇 TeamsUpgradePolicy 的正確模式視情況而定。 請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指南](migration-interop-guidance-for-teams-with-skype.md)中的語音體驗。

<sup>2</sup>如先前所宣告, TeamsInteropPolicy 將會停用 (針對第3季度結束), 且其功能會整合到 TeamsUpgradePolicy 中。 互通性和遷移將使用由 TeamsUpgradePolicy 決定的「共存模式」進行管理, 現在已提供此功能。 選取使用者的模式將會控制來電與聊天的路由, 以及使用者可以在哪個用戶端啟動聊天和通話或排程會議。 TeamsInteropPolicy 將會停用, 但仍需在 phaseout 期間與 TeamsUpgradePolicy 並行設定。  

如此一來, Microsoft 最近更新了「Microsoft 團隊系統管理中心」 (也稱為「現代入口網站」), 以根據共存模式反映新的管理模型。 在現代入口網站中, 設定 TeamsUpgradePolicy 現在會自動將 TeamsInteropPolicy 設定為一致的值, 因此在使用者介面中不會再顯示 TeamsInteropPolicy。 不過, 使用 PowerShell 的管理員仍必須同時設定 TeamsUpgradePolicy 和 TeamsInteropPolicy, 以確保正確地進行路由。 在轉換至 TeamsUpgradePolicy 完成後, 也不需要再設定 TeamsInteropPolicy。

如需詳細資訊, 請參閱[與商務用 Skype 搭配使用團隊之組織的遷移與互通性指導](migration-interop-guidance-for-teams-with-skype.md)方針。

## <a name="migrating-from-calling-plans"></a>從通話方案遷移

如需從通話方案遷移的詳細資訊, 請參閱:

- [設定通話方案](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice 使用者](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [CsOnlineLisLocation](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
建議您移除先前設定的授權方案資訊, 如下所示:
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>在商務用 Skype Server 中使用與內部部署 PSTN 連線的 Office 365 Phone 系統進行遷移

如需從手機系統在商務用 Skype Server 的內部部署 PSTN 連線中進行遷移的詳細資訊, 請參閱下列內容:

- [規劃](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [6.5](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

建議您移除先前設定的語音路由資訊, 如下所示:

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>透過雲端連接器 Edition 透過 Office 365 Phone System 與內部部署 PSTN 連線能力進行遷移 

如需透過雲端連接器從手機系統移植到內部部署 PSTN 連線的詳細資訊, 請參閱下列內容:

- [規劃](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [6.5](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [使用者設定](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

建議您移除先前設定的語音路由資訊, 如下所示:
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>相關連結

[與商務用 Skype 搭配使用團隊之組織的遷移和互通性指南](migration-interop-guidance-for-teams-with-skype.md)

[授與 CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[新-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[移除-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

