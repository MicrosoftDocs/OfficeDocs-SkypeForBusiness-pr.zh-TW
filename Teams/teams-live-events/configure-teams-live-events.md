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
ms.openlocfilehash: 222e7e51fcf87e0e76c3ab18f33357f7489a1ce1
ms.sourcegitcommit: a6425a536746e129ab8bda3984b5ae63fb316192
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/07/2020
ms.locfileid: "42558593"
---
# <a name="configure-live-event-settings-in-microsoft-teams"></a><span data-ttu-id="eea52-103">在 Microsoft 團隊中設定即時事件設定</span><span class="sxs-lookup"><span data-stu-id="eea52-103">Configure live event settings in Microsoft Teams</span></span>

<span data-ttu-id="eea52-104">使用 [團隊即時事件] 設定來設定貴組織中的即時事件設定。</span><span class="sxs-lookup"><span data-stu-id="eea52-104">Use Teams live events settings to configure settings for live events that are held in your organization.</span></span> <span data-ttu-id="eea52-105">您可以設定支援 URL，並設定協力廠商的影片發佈提供者。</span><span class="sxs-lookup"><span data-stu-id="eea52-105">You can set up a support URL and configure a third-party video distribution provider.</span></span> <span data-ttu-id="eea52-106">這些設定適用于您組織中建立的所有即時事件。</span><span class="sxs-lookup"><span data-stu-id="eea52-106">These settings apply to all live events that are created in your organization.</span></span> 

<span data-ttu-id="eea52-107">您可以在 Microsoft 團隊系統管理中心輕鬆管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="eea52-107">You can easily manage these settings in the Microsoft Teams admin center.</span></span> <span data-ttu-id="eea52-108">在左側導覽中，移至 [**會議** > **即時事件] 設定**。</span><span class="sxs-lookup"><span data-stu-id="eea52-108">In the left navigation, go to **Meetings** > **Live events settings**.</span></span> 

<span data-ttu-id="eea52-109">![小組 [即時事件] 設定的螢幕擷取畫面](../media/teams-live-events-settings.png "您可以在 Microsoft 團隊系統管理中心設定的小組即時事件設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="eea52-109">![Screen shot of Teams live events settings](../media/teams-live-events-settings.png "Screen shot of Teams live events settings that you can configure in the Microsoft Teams admin center")</span></span> 

## <a name="set-up-event-support-url"></a><span data-ttu-id="eea52-110">設定事件支援 URL</span><span class="sxs-lookup"><span data-stu-id="eea52-110">Set up event support URL</span></span>

<span data-ttu-id="eea52-111">此 URL 會顯示在 [即時事件] 出席者中。</span><span class="sxs-lookup"><span data-stu-id="eea52-111">This URL is shown to live event attendees.</span></span> <span data-ttu-id="eea52-112">新增貴組織的支援 URL，讓出席者在即時事件期間取得聯絡支援的方式。</span><span class="sxs-lookup"><span data-stu-id="eea52-112">Add the support URL for your organization to give attendees a way to contact support during a live event.</span></span>

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft [小組標誌] 的圖示](../media/teams-logo-30x30.png) <span data-ttu-id="eea52-114">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="eea52-114">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="eea52-115">在左側導覽中，移至 [**會議** > **即時事件設定**]。</span><span class="sxs-lookup"><span data-stu-id="eea52-115">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="eea52-116">在 [**支援 url**] 底下，輸入您組織的支援 url。</span><span class="sxs-lookup"><span data-stu-id="eea52-116">Under **Support URL**, enter your organization's support URL.</span></span> 

    <span data-ttu-id="eea52-117">![系統管理中心的即時事件支援 URL 設定](../media/teams-live-events-settings-supporturl.png "小組即時事件之支援 URL 設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="eea52-117">![Support URL setting for live events in the admin center](../media/teams-live-events-settings-supporturl.png "Screen shot of support URL setting for Teams live events")</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="eea52-118">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eea52-118">Using Windows PowerShell</span></span>
<span data-ttu-id="eea52-119">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="eea52-119">Run the following:</span></span>
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -SupportURL “{your URL}” 
```
<span data-ttu-id="eea52-120">如需詳細資訊，請參閱[設定 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="eea52-120">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>
## <a name="configure-a-third-party-video-distribution-provider"></a><span data-ttu-id="eea52-121">設定協力廠商的影片發佈提供者</span><span class="sxs-lookup"><span data-stu-id="eea52-121">Configure a third-party video distribution provider</span></span> 

<span data-ttu-id="eea52-122">如果您是透過 Microsoft video 傳遞合作夥伴購買及設定軟體定義的網路（SDN）方案或企業內容傳遞網路（eCDN）方案，請在團隊中設定即時事件的提供者。</span><span class="sxs-lookup"><span data-stu-id="eea52-122">If you purchased and set up a software defined network (SDN) solution or enterprise content delivery network (eCDN) solution through a Microsoft video delivery partner, configure the provider for live events in Teams.</span></span> 

### <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![顯示 Microsoft [小組標誌] 的圖示](../media/teams-logo-30x30.png) <span data-ttu-id="eea52-124">使用 Microsoft 團隊系統管理中心</span><span class="sxs-lookup"><span data-stu-id="eea52-124">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="eea52-125">在左側導覽中，移至 [**會議** > **即時事件設定**]。</span><span class="sxs-lookup"><span data-stu-id="eea52-125">In the left navigation, go to **Meetings** > **Live event settings**.</span></span>
2. <span data-ttu-id="eea52-126">在**協力廠商的 [視頻發佈提供者**] 下，完成下列動作：</span><span class="sxs-lookup"><span data-stu-id="eea52-126">Under **Third-party video distribution providers**, complete the following:</span></span> 

    <span data-ttu-id="eea52-127">![系統管理中心中的協力廠商影片發佈提供者設定](../media/teams-live-events-settings-distribution-provider.png "即時事件之協力廠商影片發佈提供者設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="eea52-127">![Third-party video distribution provider settings in the admin center](../media/teams-live-events-settings-distribution-provider.png "Screen shot of the third-party video distribution provider settings for live events")</span></span>

    - <span data-ttu-id="eea52-128">**使用協力廠商的發行提供者**開啟此，以啟用協力廠商的影片發佈提供者。</span><span class="sxs-lookup"><span data-stu-id="eea52-128">**Use a third-party distribution provider** Turn this on to enable the third-party video distribution provider.</span></span>
    - <span data-ttu-id="eea52-129">**SDN 提供者名稱**選擇您正在使用的提供者。</span><span class="sxs-lookup"><span data-stu-id="eea52-129">**SDN provider name** Choose the provider you're using.</span></span>
    - <span data-ttu-id="eea52-130">**提供者授權金鑰**輸入您從提供者連絡人取得的授權 ID。</span><span class="sxs-lookup"><span data-stu-id="eea52-130">**Provider license key** Enter the license ID that you got from your provider contact.</span></span>
    - <span data-ttu-id="eea52-131">**SDN API 範本 URL**輸入您從提供者連絡人取得的 API 範本 URL。</span><span class="sxs-lookup"><span data-stu-id="eea52-131">**SDN API template URL** Enter the API template URL that you got from your provider contact.</span></span>

### <a name="using-windows-powershell"></a><span data-ttu-id="eea52-132">使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eea52-132">Using Windows PowerShell</span></span>
<span data-ttu-id="eea52-133">根據您所使用的提供者，從提供者連絡人取得授權識別碼或 API 權杖及 API 範本，然後執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="eea52-133">Get the license ID or API token and API template from your provider contact, and then run one of the following, depending on the provider you're using:</span></span>

<span data-ttu-id="eea52-134">**一兩**</span><span class="sxs-lookup"><span data-stu-id="eea52-134">**Hive**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName hive -SdnLicenseId {license ID GUID provided by Hive} -SdnApiTemplateUrl “{API template URL provided by Hive}”
```
<span data-ttu-id="eea52-135">**Kollective**</span><span class="sxs-lookup"><span data-stu-id="eea52-135">**Kollective**</span></span> 
```PowerShell
Set-CsTeamsMeetingBroadcastConfiguration -AllowSdnProviderForBroadcastMeeting $True -SdnProviderName kollective -SdnApiTemplateUrl "{API template URL provided by Kollective}" -SdnApiToken {API token GUID provided by Kollective}
```
<span data-ttu-id="eea52-136">如需詳細資訊，請參閱[設定 CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="eea52-136">For more information, see [Set-CsTeamsMeetingBroadcastConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingbroadcastconfiguration?view=skype-ps).</span></span>

> [!NOTE]
> <span data-ttu-id="eea52-137">如果您打算使用外部應用程式或裝置建立即時事件，您也需要[使用 Microsoft Stream 來設定 eCDN 提供者](https://docs.microsoft.com/stream/network-caching)。</span><span class="sxs-lookup"><span data-stu-id="eea52-137">If you plan to create live events using an external app or device, you'll also need to [configure your eCDN provider with Microsoft Stream](https://docs.microsoft.com/stream/network-caching).</span></span> 

### <a name="related-topics"></a><span data-ttu-id="eea52-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="eea52-138">Related topics</span></span>
- [<span data-ttu-id="eea52-139">什麼是 Teams 即時活動？</span><span class="sxs-lookup"><span data-stu-id="eea52-139">What are Teams live events?</span></span>](what-are-teams-live-events.md)
- [<span data-ttu-id="eea52-140">Teams 即時活動的方案</span><span class="sxs-lookup"><span data-stu-id="eea52-140">Plan for Teams live events</span></span>](plan-for-teams-live-events.md)
- [<span data-ttu-id="eea52-141">設定 Teams 即時活動</span><span class="sxs-lookup"><span data-stu-id="eea52-141">Set up for Teams live events</span></span>](set-up-for-teams-live-events.md)