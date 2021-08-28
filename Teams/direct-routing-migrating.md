---
title: 移轉至直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 瞭解從線上連線和商務用 Skype直接路由Teams需要哪些內容。
ms.openlocfilehash: 71776c18dc6ec802c19f9dfc94c51b2b714bc210
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/26/2021
ms.locfileid: "58599748"
---
# <a name="migrate-to-direct-routing"></a>移轉至直接路由

本文將說明從線上和商務用 Skype直接路由Microsoft Teams需要哪些內容。 本文涵蓋從下列移移： 
 
- 電話系統 Online (方案Teams商務用 Skype方案)  
- 電話系統 Online 商務用 Skype Server (內部署 PSTN 連線商務用 Skype連線)   
- 電話系統 Online 版雲端連接器版本與內部部署 PSTN 連線 (使用商務用 Skype連線) 


除了這些組組步驟之外，系統還需要在會話邊界控制器 (SBC) 將通話路由至新路由。 這已超出本檔的範圍。 詳細資訊請參閱您的 SBC 廠商檔。  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a>各種 PSTN 連接選項的使用者配置結束狀態 

下表顯示已布備所選 PSTN 連接選項的使用者的結束狀態，電話系統。 只會顯示與語音相關的屬性。

|使用者物件屬性 |具有通話方案的電話系統|電話系統透過內部部署 PSTN 連接商務用 Skype Server|電話系統透過雲端連接器使用內部部署 PSTN 連接|電話系統直接路由使用內部部署 PSTN 連接|
|---|---|---|---|---|
|用戶端|商務用 Skype或Teams |商務用 Skype |商務用 Skype |Teams|
|許可證|SkypeBusiness Online</br>方案 2</br></br>MCOProfessional 或 MCOSTANDARD) </br></br></br>電話系統 (MCOEV) </br></br></br>通話方案</br>Teams|SkypeBusiness Online 方案 2 (MCOProfessional 或 MCOSTANDARD) </br></br></br>電話系統 (MCOEV) |SkypeBusiness Online 方案 2 (MCOProfessional 或 MCOSTANDARD) </br></br></br>電話系統 (MCOEV) |SkypeBusiness Online 方案 2 (MCOProfessional 或 MCOSTANDARD</br></br></br>電話系統 (MCOEV) </br></br>Teams|
OnPremLineURI |N/A|電話號碼必須從內部部署 AD 同步。 |電話號碼可以在內部部署 Active Directory 或 Azure Active Directory。|電話號碼可以在內部部署 Active Directory 或 Azure Active Directory。 不過，如果組織有內部部署商務用 Skype，則必須從內部部署 Active Directory 同步該號碼。|
|LineURI|PSTN 通話電話號碼|從 OnPremLineURI 參數自動設定|從 OnPremLineURI 參數自動設定|從 OnPremLineURI 參數自動設定|
|EnterpriseVoiceEnabled|真|真|真|真|
|HostedVoiceMail |真|真|真|真|
|VoicePolicy|BusinessVoice|HybridVoice|HybridVoice|HybridVoice|
|HostedVoiceMailPolicy |BusinessVoice|BusinessVoice|BusinessVoice|BusinessVoice|
|VoiceRoutingPolicy|有值|有值|有值|不適用|
|OnlineVoiceRoutingPolicy|$Null|$Null|$Null|有值|
|TeamsUpgradePolicy<sup>1</sup>|TeamsOnly， SfBOnly|$Null|$Null|TeamsOnly|
|TeamsCallingPolicy</br>AllowPrivateCalling|真|不適用|N/A|真|
|TeamsCallingPolicy</br>AllowGroupCalling|真|不適用|N/A|真|
||||||

<sup>1</sup> 選擇 TeamsUpgradePolicy 的合適模式取決於案例。 請閱讀移移和互通性指南中不同模式的語音體驗，適用于使用 Teams[和](migration-interop-guidance-for-teams-with-skype.md)商務用 Skype。

Microsoft 最近更新了「Microsoft Teams系統管理中心」 (也稱為「新式入口網站」) ，以反映以共存模式為基礎的新管理模式。 在新式入口網站中，設定 TeamsUpgradePolicy 現在也會自動將 TeamsInteropPolicy 設定為一致值，因此 TeamsInteropPolicy 不會再在使用者介面中公開。 不過，使用 PowerShell 的系統管理員仍必須將 TeamsUpgradePolicy 和 TeamsInteropPolicy 設定在一起，以確保正確的路由。 轉換至 TeamsUpgradePolicy 之後，就不再需要設定 TeamsInteropPolicy。

如需詳細資訊，請參閱與 Teams 一起使用 商務用 Skype 的組織移[商務用 Skype。](migration-interop-guidance-for-teams-with-skype.md)

## <a name="migrating-from-calling-plans"></a>從通話方案移移

有關從通話方案移移的資訊，請參閱：

- [設定通話方案](/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [Set-CsOnlineVoice 使用者](/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [Get-CsOnlineLisLocation](/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
建議您移除先前已配置的授權計畫資訊，如下所示：
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a>使用內部Office 365 電話系統 PSTN 連接從 商務用 Skype Server

有關在 電話系統使用內部部署 PSTN 商務用 Skype Server從用戶端移商務用 Skype Server，請參閱下列內容：

- [規劃](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [部署](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

建議您移除先前配置的語音路由資訊，如下所示：

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> 如果已配置全域 CsVoiceRoutingPolicy，建議您移除與此全域原則相關聯的任何 PSTN 使用方式。 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a>透過雲端連接器Office 365 電話系統內部部署 PSTN 連接從用戶端移移 

> [!Important]
> 雲端連接器版本將于 2021 年 7 月 31 日與 商務用 Skype一起淘汰。 一旦貴組織升級至 Teams，瞭解如何使用直接路由將內部部署電話網絡Teams[網路](direct-routing-landing-page.md)。

有關透過雲端連接器使用內部電話系統 PSTN 從內部部署 PSTN 進行移電話系統，請參閱下列內容：

- [規劃](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [部署](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [使用者組組](/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

建議您移除先前配置的語音路由資訊，如下所示：
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a>相關連結

[適用于使用應用程式與Teams之組織的移商務用 Skype](migration-interop-guidance-for-teams-with-skype.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Get-CsTeamsUpgradePolicy](/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[New-CsTeamsUpgradePolicy](/powershell/module/skype/New-CsTeamsUpgradePolicy)

[Remove-CsTeamsUpgradePolicy](/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[Set-CsTeamsUpgradePolicy](/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[Get-CsTeamsUpgradeConfiguration](/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[Set-CsTeamsUpgradeConfiguration](/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)