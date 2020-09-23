---
title: 在 Microsoft 團隊中設定即時事件設定
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 03/11/2019
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
audience: admin
search.appverid: MET150
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解如何管理組織中保留的小組即時事件設定。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: a0e949b2773baa2cc819629133396020dee7d7d7
ms.sourcegitcommit: 3db7c450d3afbc1049e1016d51016442e5764634
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203946"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a>在 Microsoft 團隊中設定即時事件設定

使用 [團隊即時事件] 設定來設定貴組織中的即時事件設定。 您可以設定支援 URL，並設定協力廠商的影片發佈提供者。 這些設定適用于您組織中建立的所有即時事件。

您可以在 Microsoft 團隊系統管理中心輕鬆管理這些設定。 在左側導覽中，移至 [**會議**  >  **即時事件] 設定**。

![小組 [即時事件] 設定的螢幕擷取畫面](../media/teams-live-events-settings.png "您可以在 Microsoft 團隊系統管理中心設定的小組即時事件設定的螢幕擷取畫面")

## <a name="set-up-event-support-url"></a>設定事件支援 URL

此 URL 會顯示在 [即時事件] 出席者中。 新增貴組織的支援 URL，讓出席者在即時事件期間取得聯絡支援的方式。

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 [**會議**  >  **即時事件設定**]。
2. 在 [ **支援 url**] 底下，輸入您組織的支援 url。

    ![系統管理中心的即時事件支援 URL 設定](../media/teams-live-events-settings-supporturl.png "小組即時事件之支援 URL 設定的螢幕擷取畫面")

### <a name="using-windows-powershell"></a>使用 Windows PowerShell

執行下列動作：

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
如需詳細資訊，請參閱 [設定 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。
## <a name="configure-a-third-party-video-distribution-provider"></a>設定協力廠商的影片發佈提供者 

如果您是透過 Microsoft video 傳遞合作夥伴購買及設定軟體定義的網路 (SDN) 方案或企業內容傳遞網路 (eCDN) 解決方案，請在團隊中設定即時事件的提供者。 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png) 使用 Microsoft Teams 系統管理中心

1. 在左側導覽中，移至 [**會議**  >  **即時事件設定**]。
2. 在 **協力廠商的 [視頻發佈提供者**] 下，完成下列動作： 

    ![系統管理中心中的協力廠商影片發佈提供者設定](../media/teams-live-events-settings-distribution-provider.png "即時事件之協力廠商影片發佈提供者設定的螢幕擷取畫面")

    - **使用協力廠商的發行提供者** 開啟此，以啟用協力廠商的影片發佈提供者。
    - **SDN 提供者名稱** 選擇您正在使用的提供者。
    - **提供者授權金鑰** 輸入您從提供者連絡人取得的授權 ID。
    - **SDN API 範本 URL** 輸入您從提供者連絡人取得的 API 範本 URL。

### <a name="using-windows-powershell"></a>使用 Windows PowerShell
根據您所使用的提供者，從提供者連絡人取得授權識別碼或 API 權杖及 API 範本，然後執行下列其中一項操作：

**一兩** 
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

如需詳細資訊，請參閱 [設定 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。

> [!NOTE]
> 如果您打算使用外部應用程式或裝置建立即時事件，您也需要 [使用 Microsoft Stream 來設定 eCDN 提供者](https://docs.microsoft.com/stream/network-caching)。 

>[!Note]
> 使用 Microsoft Stream to [商務用 OneDrive 和 SharePoint for meeting 錄製](../tmr-meeting-recording-change.md) 所做的變更將是一種分階段的方法。 在啟動時，您可以加入宣告此體驗，在11月中，您必須退出宣告，如果您想要繼續使用串流，且在早期2021中有一些時間，我們會要求所有客戶使用商務用 OneDrive 和 SharePoint 進行新的會議錄製。

### <a name="related-topics"></a>相關主題
- [什麼是 Teams 即時活動？](what-are-teams-live-events.md)
- [Teams 即時活動的方案](plan-for-teams-live-events.md)
- [設定 Teams 即時活動](set-up-for-teams-live-events.md)