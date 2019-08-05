---
title: 管理會議設定
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sonua
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1keywords:
- ms.teamsadmincenter.meetingsettings.overview
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: 瞭解如何在您的組織中管理使用者排程的小組會議設定。
ms.openlocfilehash: 10edd2b0b1b665a126fa7528f4b1e24bf88f4fe5
ms.sourcegitcommit: 3197f3ffca2b2315be9fd0c702ccc8c87383c893
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/19/2019
ms.locfileid: "36184137"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="ec55a-103">在 Microsoft 團隊中管理會議設定</span><span class="sxs-lookup"><span data-stu-id="ec55a-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="ec55a-104">在管理員中, 您可以使用 [團隊會議] 設定來控制匿名使用者是否可以加入團隊會議、自訂會議邀請, 以及如果您想要啟用服務品質 (QoS), 請設定即時流量的埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ec55a-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="ec55a-105">這些設定適用于使用者在貴組織中排程的所有小組會議。</span><span class="sxs-lookup"><span data-stu-id="ec55a-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="ec55a-106">您可以在 Microsoft 團隊系統管理中心中管理**會議** > **會議設定**中的這些設定。</span><span class="sxs-lookup"><span data-stu-id="ec55a-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="ec55a-107">允許匿名使用者加入會議</span><span class="sxs-lookup"><span data-stu-id="ec55a-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="ec55a-108">透過匿名加入, 任何人都可以按一下會議邀請中的連結, 以匿名使用者身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="ec55a-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span>

<span data-ttu-id="ec55a-109">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="ec55a-109">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ec55a-110">在左側導覽中, 移至 [**會議** > **會議設定**]。</span><span class="sxs-lookup"><span data-stu-id="ec55a-110">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="ec55a-111">開啟 [**參與者**] 底下的 [**匿名使用者可以加入會議**]。</span><span class="sxs-lookup"><span data-stu-id="ec55a-111">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="ec55a-112">系統![管理中心會議參與者設定的螢幕擷取畫面](media/meeting-settings-participants.png "Microsoft 團隊管理中心的團隊會議參與者設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="ec55a-112">![Screen shot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screen shot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

<span data-ttu-id="ec55a-113">如果您不希望匿名使用者加入您組織中的使用者排程的會議, 請關閉此設定。</span><span class="sxs-lookup"><span data-stu-id="ec55a-113">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="ec55a-114">自訂會議邀請</span><span class="sxs-lookup"><span data-stu-id="ec55a-114">Customize meeting invitations</span></span>

<span data-ttu-id="ec55a-115">您可以自訂小組會議邀請, 以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ec55a-115">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="ec55a-116">您可以新增貴組織的標誌, 並包含有用的資訊, 例如支援網站的連結和法律免責聲明, 以及純文字的頁尾。</span><span class="sxs-lookup"><span data-stu-id="ec55a-116">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="ec55a-117">建立會議邀請標誌的秘訣</span><span class="sxs-lookup"><span data-stu-id="ec55a-117">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="ec55a-118">建立寬度188不超過30圖元的影像 (相當小)。</span><span class="sxs-lookup"><span data-stu-id="ec55a-118">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="ec55a-119">將影像儲存為 JPG 或 PNG 格式。</span><span class="sxs-lookup"><span data-stu-id="ec55a-119">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="ec55a-120">將影像儲存在您組織中的每個人都可以存取的中央位置, 例如網路共用。</span><span class="sxs-lookup"><span data-stu-id="ec55a-120">Store the image in a central location that everyone in your organization can access, such as a network share.</span></span>

    <span data-ttu-id="ec55a-121">現在, 您可以將它新增到會議邀請。</span><span class="sxs-lookup"><span data-stu-id="ec55a-121">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="ec55a-122">請參閱後續步驟。</span><span class="sxs-lookup"><span data-stu-id="ec55a-122">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="ec55a-123">自訂會議邀請</span><span class="sxs-lookup"><span data-stu-id="ec55a-123">Customize your meeting invitations</span></span>

<span data-ttu-id="ec55a-124">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="ec55a-124">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ec55a-125">在左側導覽中, 移至 [**會議** > **會議設定**]。</span><span class="sxs-lookup"><span data-stu-id="ec55a-125">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="ec55a-126">在 [**電子郵件邀請**] 底下, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ec55a-126">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="ec55a-127">![您可以自訂之會議邀請設定的螢幕擷取畫面](media/meeting-settings-invitation.png "您可以針對團隊會議自訂之會議邀請設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="ec55a-127">![Screen shot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screen shot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="ec55a-128">**標誌 URL**輸入您的標誌儲存位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="ec55a-128">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="ec55a-129">**合法 URL**如果您的組織有您希望其他人出於任何法律考慮的法律網站, 請在這裡輸入 URL。</span><span class="sxs-lookup"><span data-stu-id="ec55a-129">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="ec55a-130">說明**URL**如果您的組織有您希望其他人在遇到問題時要移至的支援網站, 請在這裡輸入 URL。</span><span class="sxs-lookup"><span data-stu-id="ec55a-130">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="ec55a-131">\*\*\*\* 頁尾輸入要納入頁尾的文字。</span><span class="sxs-lookup"><span data-stu-id="ec55a-131">**Footer** Enter text that you want to include as a footer.</span></span>
3. <span data-ttu-id="ec55a-132">等候一小時或如此, 以傳播所做的變更。</span><span class="sxs-lookup"><span data-stu-id="ec55a-132">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="ec55a-133">然後排程小組會議, 看看會議邀請看起來的樣子。</span><span class="sxs-lookup"><span data-stu-id="ec55a-133">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="ec55a-134">設定您想要處理團隊會議即時媒體流量的方式</span><span class="sxs-lookup"><span data-stu-id="ec55a-134">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="ec55a-135"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="ec55a-135"></span></span>

<span data-ttu-id="ec55a-136">如果您使用的是服務品質[(QoS)](qos-in-teams.md)來設定網路流量的優先順序, 您可以啟用 QoS 標記, 而且您可以為每種媒體流量設定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ec55a-136">If you're using Quality of Service [(QoS)](qos-in-teams.md) to prioritize network traffic, you can enable QoS markers and you can set port ranges for each type of media traffic.</span></span>

 <span data-ttu-id="ec55a-137">![](media/teams-logo-30x30.png) **使用 microsoft [團隊管理中心**] 顯示 Microsoft 團隊標誌的圖示</span><span class="sxs-lookup"><span data-stu-id="ec55a-137">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="ec55a-138">在左側導覽中, 移至 [**會議** > **會議設定**]。</span><span class="sxs-lookup"><span data-stu-id="ec55a-138">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
2. <span data-ttu-id="ec55a-139">在 [**網路**] 底下, 執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="ec55a-139">Under **Network**, do the following:</span></span>

    <span data-ttu-id="ec55a-140">系統![管理中心的會議網路設定的螢幕擷取畫面](media/meeting-settings-network.png "Microsoft 團隊系統管理中心之團隊會議的網路設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="ec55a-140">![Screen shot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screen shot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="ec55a-141">若要允許將 DSCP 標記用於 QoS, 請開啟**即時媒體流量的 [插入服務品質 (QoS)] 標記**。</span><span class="sxs-lookup"><span data-stu-id="ec55a-141">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="ec55a-142">您只能選擇是否要使用標記;您無法針對每種流量類型設定自訂標記。</span><span class="sxs-lookup"><span data-stu-id="ec55a-142">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="ec55a-143">如需 DSCP 標記的詳細資訊, 請參閱[選取 QoS 實現方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="ec55a-143">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
    - <span data-ttu-id="ec55a-144">若要指定埠範圍, 請在 [**選取即時媒體流量的每個類型的埠範圍**] 旁, 選取 [**指定埠範圍**], 然後輸入音訊、影片和螢幕共用的起始和結束埠。</span><span class="sxs-lookup"><span data-stu-id="ec55a-144">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="ec55a-145">需要選取此選項才能實現 QoS。</span><span class="sxs-lookup"><span data-stu-id="ec55a-145">Selecting this option is required to implement QoS.</span></span>
    > [!IMPORTANT]
    > <span data-ttu-id="ec55a-146">如果您選取 [**自動使用任何可用的埠**], 則會使用1024和65535之間的可用埠。</span><span class="sxs-lookup"><span data-stu-id="ec55a-146">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="ec55a-147">只有在未實現 QoS 時才使用這個選項。</span><span class="sxs-lookup"><span data-stu-id="ec55a-147">Use this option only when not implementing QoS.</span></span>
    >
    > <span data-ttu-id="ec55a-148">選取太窄的埠範圍, 將會導致呼叫中斷和通話品質不佳。</span><span class="sxs-lookup"><span data-stu-id="ec55a-148">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="ec55a-149">下列建議最小。</span><span class="sxs-lookup"><span data-stu-id="ec55a-149">The recommendations below should be a bare minimum.</span></span>

 <span data-ttu-id="ec55a-150">如果您不確定要在您的環境中使用的埠範圍, 下列設定就是良好的起點。</span><span class="sxs-lookup"><span data-stu-id="ec55a-150">If you are unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="ec55a-151">若要深入瞭解, 請參閱[在 Microsoft 團隊中實施服務品質 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="ec55a-151">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="ec55a-152">這些是所需的 DSCP 標記, 以及團隊和 ExpressRoute 所使用的建議對應媒體埠範圍。</span><span class="sxs-lookup"><span data-stu-id="ec55a-152">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

<span data-ttu-id="ec55a-153">_埠範圍和 DSCP 標記_</span><span class="sxs-lookup"><span data-stu-id="ec55a-153">_Port ranges and DSCP markings_</span></span>

<span data-ttu-id="ec55a-154">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="ec55a-154">Media traffic type</span></span>| <span data-ttu-id="ec55a-155">用戶端來源埠範圍\*</span><span class="sxs-lookup"><span data-stu-id="ec55a-155">Client source port range \*</span></span> |<span data-ttu-id="ec55a-156">通訊協定</span><span class="sxs-lookup"><span data-stu-id="ec55a-156">Protocol</span></span>|<span data-ttu-id="ec55a-157">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="ec55a-157">DSCP value</span></span>|<span data-ttu-id="ec55a-158">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="ec55a-158">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="ec55a-159">音訊</span><span class="sxs-lookup"><span data-stu-id="ec55a-159">Audio</span></span>            | <span data-ttu-id="ec55a-160">50000–50019</span><span class="sxs-lookup"><span data-stu-id="ec55a-160">50,000–50,019</span></span>               |<span data-ttu-id="ec55a-161">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ec55a-161">TCP/UDP</span></span> |<span data-ttu-id="ec55a-162">46</span><span class="sxs-lookup"><span data-stu-id="ec55a-162">46</span></span>        |<span data-ttu-id="ec55a-163">加急轉移 (EF)</span><span class="sxs-lookup"><span data-stu-id="ec55a-163">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="ec55a-164">顯示器</span><span class="sxs-lookup"><span data-stu-id="ec55a-164">Video</span></span>            | <span data-ttu-id="ec55a-165">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="ec55a-165">50,020–50,039</span></span>               |<span data-ttu-id="ec55a-166">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ec55a-166">TCP/UDP</span></span> |<span data-ttu-id="ec55a-167">34</span><span class="sxs-lookup"><span data-stu-id="ec55a-167">34</span></span>        |<span data-ttu-id="ec55a-168">有保證的轉寄 (AF41)</span><span class="sxs-lookup"><span data-stu-id="ec55a-168">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="ec55a-169">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="ec55a-169">Application/Screen Sharing</span></span>| <span data-ttu-id="ec55a-170">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="ec55a-170">50,040–50,059</span></span>      |<span data-ttu-id="ec55a-171">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ec55a-171">TCP/UDP</span></span> |<span data-ttu-id="ec55a-172">滿</span><span class="sxs-lookup"><span data-stu-id="ec55a-172">18</span></span>        |<span data-ttu-id="ec55a-173">有保證的轉寄 (AF21)</span><span class="sxs-lookup"><span data-stu-id="ec55a-173">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="ec55a-174">\*您指定的埠範圍不能重疊, 且必須彼此相鄰。</span><span class="sxs-lookup"><span data-stu-id="ec55a-174">\* The port ranges you assign cannot overlap and must be adjacent to each other.</span></span>

<span data-ttu-id="ec55a-175">設定不同流量類型的埠範圍只是處理即時媒體的一個步驟;如需更多詳細資訊, 請參閱[小組中的服務品質 (QoS)](qos-in-teams.md) 。</span><span class="sxs-lookup"><span data-stu-id="ec55a-175">Setting port ranges for different traffic types is only one step in handling real time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span> <span data-ttu-id="ec55a-176">如果您在 Microsoft 團隊系統管理中心啟用或變更設定, 您將需要[將相符的設定套用到所有的使用者裝置](QoS-in-Teams-clients.md)和內部網路裝置, 才能完全實現團隊中的 QoS 變更。</span><span class="sxs-lookup"><span data-stu-id="ec55a-176">If you enable or change settings in the Microsoft Teams admin center, you will need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and internal network devices to fully implement the changes to QoS in Teams.</span></span>

<span data-ttu-id="ec55a-177">當 QoS 已用於一段時間之後, 您就會在每個這三個工作負載的需求上取得使用量資訊, 而且您可以根據自己的特定需求, 選擇要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="ec55a-177">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="ec55a-178">[通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)將會對您有所説明。</span><span class="sxs-lookup"><span data-stu-id="ec55a-178">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
