---
title: 在 Microsoft Teams 中設定即時活動設定
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: 瞭解如何管理組織中所舉辦 Teams 即時活動的設定。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8ac5bf29fbbe61b2e2224aeccb2082e31742816b
ms.sourcegitcommit: 4d88637f510a78d5709d1213c3e285d83a022014
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/14/2022
ms.locfileid: "66794161"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>在 Microsoft Teams 中設定即時活動設定

使用 Teams 即時活動設定來設定組織中所舉辦即時活動的設定。 您可以設定支援 URL，並設定協力廠商視訊發佈提供者。 這些設定會套用到您組織中建立的所有即時活動。

您可以在 Microsoft Teams 系統管理中心輕鬆管理這些設定。 在左側導覽中，移至 **[會議**  >  **即時活動設定]**。

![Teams 即時活動設定的螢幕擷取畫面。](../media/teams-live-events-settings-new.png "您可以在 Microsoft Teams 系統管理中心設定的 Teams 即時活動設定螢幕擷取畫面")

## <a name="set-up-event-support-url"></a>設定活動支援 URL

這個 URL 會顯示給即時活動出席者。 為貴組織新增支援 URL，讓出席者能夠在即時活動期間連絡支援服務。

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 **[會議**  >  **即時活動設定]**。
2. 在 **[支援 URL**] 底下，輸入貴組織的支援 URL。

    ![系統管理中心即時活動的支援 URL 設定。](../media/teams-live-events-settings-supporturl.png "Teams 即時活動支援 URL 設定的螢幕擷取畫面")

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

執行下列動作：

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
如需詳細資訊，請參閱 [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true)。
## <a name="configure-a-third-party-video-distribution-provider"></a>設定協力廠商視訊發佈提供者 

如果您透過 Microsoft 影片傳遞合作夥伴購買並設定軟體定義的網路 (SDN) 解決方案或企業內容傳遞網路 (eCDN) 解決方案，請在 Teams 中設定即時活動的提供者。 

### <a name="using-the-microsoft-teams-admin-center"></a>使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 **[會議**  >  **即時活動設定]**。
2. 在 **[協力廠商視訊發佈提供者**] 底下，完成下列動作： 

    ![系統管理中心的協力廠商視訊發佈提供者設定。](../media/teams-live-events-settings-distribution-provider-new.png "即時活動之協力廠商視訊發佈提供者設定的螢幕擷取畫面")

    - **協力廠商通訊提供者** 開啟此開啟以啟用協力廠商視訊發佈提供者。
    - **SDN 提供者名稱** 選擇您正在使用的提供者。
    - **SDN 設定** 輸入 SDN 設定詳細資料。
        
### <a name="using-windows-powershell"></a>使用 Windows PowerShell
從您的提供者連絡人取得授權識別碼或 API 權杖和 API 範本，然後根據您使用的提供者執行下列其中一項：

**Hive** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
**Kollective** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
**Riverbed** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
**Ramp** 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```
**Peer5**
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName peer5 -SdnLicenseId {peer5CustomerId}
```

如需詳細資訊，請參閱 [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps&preserve-view=true)。

> [!NOTE]
> 如果您打算使用外部應用程式或裝置建立即時活動，您也需要[使用Microsoft Stream設定您的 eCDN 提供者](/stream/network-caching)。 

>[!Note]
> 從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](../tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。

>[!Note]
> 您選擇的 eCDN 解決方案受選定之協力廠商提供者的服務條款和隱私權原則所規範，這將會規範您使用 eCDN 提供者的解決方案。 您使用 eCDN 提供者的解決方案將不受 Microsoft 大量授權條款或線上服務條款的規範。 如果您不同意協力廠商提供者的條款，請不要在 Microsoft Teams 中啟用 eCDN 解決方案。

### <a name="related-topics"></a>相關主題
- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的方案](plan-for-teams-live-events.md)
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)
