---
title: 在 Microsoft Teams 中設定即時活動設定
author: cichur
ms.author: v-cichur
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
- m365initiative-meetings
- m365initiative-meetings-enabler
- enabler-strategic
description: 瞭解如何管理貴組織中舉辦的 Teams 即時活動的設定。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.liveevents.settings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9749484344d969671e8a0195de3386a57388d275
ms.sourcegitcommit: 950387da2a2c094b7580bcf81ae5d8b6dfba0d6b
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/08/2021
ms.locfileid: "51637875"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="aea8d-103">在 Microsoft Teams 中設定即時活動設定</span><span class="sxs-lookup"><span data-stu-id="aea8d-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="aea8d-104">使用 Teams 即時活動設定來設定貴組織中舉辦的即時活動設定。</span><span class="sxs-lookup"><span data-stu-id="aea8d-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="aea8d-105">您可以設定支援 URL，並設定協力廠商視音訊發佈提供者。</span><span class="sxs-lookup"><span data-stu-id="aea8d-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="aea8d-106">這些設定適用于在貴組織中建立的所有即時活動。</span><span class="sxs-lookup"><span data-stu-id="aea8d-106">These settings apply to all live events that are created in your organization.</span></span>

<span data-ttu-id="aea8d-107">您可以在 Microsoft Teams 系統管理中心輕鬆管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="aea8d-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="aea8d-108">在左側流覽中，前往 **會議**  >  **Live 事件設定**。</span><span class="sxs-lookup"><span data-stu-id="aea8d-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span>

<span data-ttu-id="aea8d-109">![Teams 即時活動設定螢幕擷取畫面](../media/teams-live-events-settings.png "您可以在 Microsoft Teams 系統管理中心設定 Teams 即時活動設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="aea8d-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span>

## <a name="set-up-event-support-url"></a><span data-ttu-id="aea8d-110">設定活動支援 URL</span><span class="sxs-lookup"><span data-stu-id="aea8d-110">Set up event support URL</span></span>

<span data-ttu-id="aea8d-111">此 URL 會顯示給即時活動出席者。</span><span class="sxs-lookup"><span data-stu-id="aea8d-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="aea8d-112">新增貴組織的支援 URL，讓出席者在即時活動期間與支援人員聯繫。</span><span class="sxs-lookup"><span data-stu-id="aea8d-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png) <span data-ttu-id="aea8d-114&quot;>使用 Microsoft Teams 系統管理中心</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;aea8d-114&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;aea8d-115&quot;>在左側流覽中，前往 **會議**  >  **即時活動設定**。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;aea8d-115&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;aea8d-116&quot;>在 **支援 URL** 下，輸入貴組織的支援 URL。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;aea8d-116&quot;>Under **Support URL**, enter your organization's support URL.</span></span>

    <span data-ttu-id=&quot;aea8d-117&quot;>![系統管理中心即時活動的支援 URL 設定](../media/teams-live-events-settings-supporturl.png &quot;Teams 即時活動支援 URL 設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="aea8d-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="aea8d-118">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aea8d-118">Using Windows PowerShell</span></span>

<span data-ttu-id="aea8d-119">執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="aea8d-119">Run the following:</span></span>

```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}”
```
<span data-ttu-id="aea8d-120">詳細資訊，請參閱 [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aea8d-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="aea8d-121">設定協力廠商視音訊發佈提供者</span><span class="sxs-lookup"><span data-stu-id="aea8d-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="aea8d-122">如果您透過 Microsoft 影片傳遞合作夥伴購買並設定軟體定義的網路 (SDN) 解決方案或企業內容傳遞網路 (eCDN) 解決方案，請設定 Teams 中即時事件的提供者。</span><span class="sxs-lookup"><span data-stu-id="aea8d-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft Teams 標誌的圖示](../media/teams-logo-30x30.png) <span data-ttu-id="aea8d-124&quot;>使用 Microsoft Teams 系統管理中心</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;aea8d-124&quot;>Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id=&quot;aea8d-125&quot;>在左側流覽中，前往 **會議**  >  **即時活動設定**。</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;aea8d-125&quot;>In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id=&quot;aea8d-126&quot;>在 **協力廠商視訊發佈提供者下**，完成下列操作：</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;aea8d-126&quot;>Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id=&quot;aea8d-127&quot;>![系統管理中心的協力廠商視音訊發佈提供者設定](../media/teams-live-events-settings-distribution-provider.png &quot;即時活動的協力廠商視音訊發佈提供者設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="aea8d-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="aea8d-128">**使用協力廠商通訊提供者** 開啟此選項以啟用協力廠商視音訊發佈提供者。</span><span class="sxs-lookup"><span data-stu-id="aea8d-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="aea8d-129">**SDN 提供者名稱** 選擇您使用的提供者。</span><span class="sxs-lookup"><span data-stu-id="aea8d-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="aea8d-130">**提供者授權金鑰** 輸入您從提供者連絡人獲得授權識別碼。</span><span class="sxs-lookup"><span data-stu-id="aea8d-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="aea8d-131">**SDN API 範本 URL** 輸入您從提供者連絡人獲得之 API 範本 URL。</span><span class="sxs-lookup"><span data-stu-id="aea8d-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="aea8d-132">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="aea8d-132">Using Windows PowerShell</span></span>
<span data-ttu-id="aea8d-133">從提供者連絡人取得授權識別碼或 API 權杖和 API 範本，然後根據您使用的提供者執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="aea8d-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="aea8d-134">**蜂巢**</span><span class="sxs-lookup"><span data-stu-id="aea8d-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="aea8d-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="aea8d-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="aea8d-136">**河床**</span><span class="sxs-lookup"><span data-stu-id="aea8d-136">**Riverbed**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName riverbed -SdnApiTemplateUrl "{API template URL provided by Riverbed}" -SdnApiToken {API token GUID provided by Riverbed}
```
<span data-ttu-id="aea8d-137">**斜坡**</span><span class="sxs-lookup"><span data-stu-id="aea8d-137">**Ramp**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName ramp -SdnRuntimeConfiguration "{Configuration provided by RAMP}"
```

<span data-ttu-id="aea8d-138">詳細資訊，請參閱 [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="aea8d-138">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="aea8d-139">如果您打算使用外部 App 或裝置建立即時活動，您也需要使用 Microsoft Stream 設定 [您的 eCDN 提供者](/stream/network-caching)。</span><span class="sxs-lookup"><span data-stu-id="aea8d-139">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](/stream/network-caching).</span></span> 

>[!Note]
> <span data-ttu-id="aea8d-p104">從使用 Microsoft Stream 變更為使用[商務用 OneDrive 和 SharePoint 來進行會議錄製](../tmr-meeting-recording-change.md)，將會採取階段性的方式。推出時您將可以加入此體驗。在 11 月，如果您想要繼續使用 Stream，則必須退出體驗。在 2021 年初的某個時候，我們將要求所有客戶對新會議錄製使用商務用 OneDrive 和 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="aea8d-p104">The change from using Microsoft Stream to [OneDrive for Business and SharePoint for meeting recordings](../tmr-meeting-recording-change.md) will be a phased approach. At launch you'll be able to opt-in to this experience, in November you'll have to opt-out if you want to continue using Stream, and some time in early 2021 we'll require all customers to use OneDrive for Business and SharePoint for new meeting recordings.</span></span>

>[!Note]
> <span data-ttu-id="aea8d-142">您所選擇的 eCDN 解決方案受所選協力廠商提供者的服務條款與隱私權政策所規範，這將規範您對於 eCDN 提供者解決方案的使用。</span><span class="sxs-lookup"><span data-stu-id="aea8d-142">Your chosen eCDN solution is subject to the selected 3rd party provider’s terms of service and privacy policy, which will govern your use of the eCDN provider’s solution.</span></span> <span data-ttu-id="aea8d-143">您對於 eCDN 提供者解決方案的使用不受 Microsoft 大量授權條款或線上服務條款限制。</span><span class="sxs-lookup"><span data-stu-id="aea8d-143">Your use of the eCDN provider’s solution will not be subject to the Microsoft volume licensing terms or Online Services Terms.</span></span> <span data-ttu-id="aea8d-144">如果您不同意協力廠商提供者的條款，請不要在 Microsoft Teams 中啟用 eCDN 解決方案。</span><span class="sxs-lookup"><span data-stu-id="aea8d-144">If you don't agree to the 3rd party provider’s terms, then don't enable the eCDN solution in Microsoft Teams.</span></span>

### <a name="related-topics"></a><span data-ttu-id="aea8d-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="aea8d-145">Related topics</span></span>
- [<span data-ttu-id="aea8d-146">什麼是 Teams 即時活動？</span><span class="sxs-lookup"><span data-stu-id="aea8d-146">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="aea8d-147">Teams 即時活動的方案</span><span class="sxs-lookup"><span data-stu-id="aea8d-147">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="aea8d-148">設定 Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="aea8d-148">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)
