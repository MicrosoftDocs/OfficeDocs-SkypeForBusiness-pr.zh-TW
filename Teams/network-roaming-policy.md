---
title: 網路漫遊原則
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Priority
search.appverid: MET150
ms.custom: ''
ms.collection:
- M365-collaboration
- m365initiative-meetings
description: 瞭解如何管理 Teams 網路漫遊原則設定。
ms.openlocfilehash: 684bb9f30abb6a474582d83614d0e259ed44b21a
ms.sourcegitcommit: 4af3638637456f21bc97f510ed9d2f7ff2da07e2
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/19/2022
ms.locfileid: "63660719"
---
# <a name="manage-video-and-media-settings-with-the-network-roaming-policy"></a>使用網路漫遊原則管理視訊和媒體設定

除了使用會議原則管理視訊和媒體設定之外，現在您還可以用 TeamsNetworkRoamingPolicy，動態控制 Microsoft Teams 用戶端所用的下列屬性使用： 

- IP 影片
- 媒體位元速率

此原則可讓您將設定指派給網路站台。 Teams 用戶端會根據所連線的網路站台動態提取設定。 當 Teams 用戶端從已指派漫遊原則的網路站台中登入時，將會使用該原則。 如果沒有指派任何原則，將會使用會議原則中設定的值。 有關會議原則音訊和視訊設定的詳細資訊，請參閱 [音訊和視訊的會議原則設定](meeting-policies-audio-and-video.md)。

## <a name="configure-the-teamsnetworkroamingpolicy"></a>設定 TeamsNetworkRoamingPolicy

若要設定 TeamsNetworkRoamingPolicy，請使用下列 PowerShell Cmdlet：

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)

TeamsNetworkRoamingPolicy 包含下列參數：

- AllowIPVideo - 此設定可控制是否能在使用者主持的會議及在使用者啟動的一對一和群組通話中開啟視訊。

- MediaBitRateKb - 此設定會決定使用者通話和會議中的音訊、視訊及視訊應用程式共用傳輸的平均媒體位元速率總計。

在您設定好該原則之後，使用 [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite) Cmdlet 將其指派給一或多個網路站台，方法如下：

```PowerShell
 Set-CsTenantNetworkSite -NetworkRoamingPolicy
 ``` 
 
 若要從網路站台移除原則，請使用下列 Cmdlet：
 
 ```PowerShell
 Set-CsTenantNetworkSite -NetworkRoamingPolicy $null
 ```

若要為未啟用企業語音的使用者啟用網路漫遊原則，您也必須在 TeamsMeetingPolicy 中啟用 AllowNetworkConfigurationSettingsLookup 設定。 此設定預設為關閉。

有關建立網路站台的詳細資訊，請參閱 [雲端語音功能的網路設定](cloud-voice-network-settings.md)。 

## <a name="examples"></a>範例

```PowerShell
New-CsTeamsNetworkRoamingPolicy -Identity LowBandwidthSite -AllowIPVideo $false -MediaBitRateKb 1000
```

```PowerShell
Set-CsTenantNetworkSite -Identity Burlington -NetworkRoamingPolicy LowBandwidthSite
```

## <a name="supported-clients"></a>支援的用戶端

- Windows 
- MacOS 電腦版

## <a name="known-issues"></a>已知的問題

在 Teams Online PowerShell v 2.0.0 中指定 New-和 Get-CsTeamsNetworkRoamingPolicy 時，您會看到額外顯示的資料。


## <a name="related-topics"></a>相關主題

- [Get-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/get-csteamsnetworkroamingpolicy)
- [New-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/new-csteamsnetworkroamingpolicy)
- [Set-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/set-csteamsnetworkroamingpolicy)
- [Remove-CsTeamsNetworkRoamingPolicy](/powershell/module/skype/remove-csteamsnetworkroamingpolicy)
- [Set-CsTenantNetworkSite](/powershell/module/skype/set-cstenantnetworksite)
