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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.invitationurls
- ms.teamsadmincenter.meetingsettings.network.ports
- ms.teamsadmincenter.meetingsettings.overview
ms.collection:
- M365-collaboration
description: 了解如何管理使用者在您組織中排程的 Teams 會議設定。
ms.openlocfilehash: 1d7aed894724a09f1b3cc352ef3e280cf3ead310
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086159"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="7710e-103">在 Microsoft Teams 中管理會議設定</span><span class="sxs-lookup"><span data-stu-id="7710e-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="7710e-104">身為系統管理員，您可以使用 Teams 會議設定，來控制匿名使用者是否可以加入 Teams 會議、自訂會議邀請，以及如果您要啟用服務品質 (QoS)，則要針對即時流量設定連接範圍。</span><span class="sxs-lookup"><span data-stu-id="7710e-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="7710e-105">這些設定適用於使用者在貴組織中排程的所有 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="7710e-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="7710e-106">您可以在 Microsoft Teams 系統管理中心的 [會議]\*\*\*\*  >  [會議設定]\*\*\*\* 來管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="7710e-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="7710e-107">允許匿名使用者加入會議</span><span class="sxs-lookup"><span data-stu-id="7710e-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="7710e-108">利用匿名加入，任何人都可以按一下會議邀請中的連結，以匿名使用者的身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="7710e-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="7710e-109">若要深入了解，請參閱[在沒有 Teams 帳戶的情況下加入會議](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。</span><span class="sxs-lookup"><span data-stu-id="7710e-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="7710e-110">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="7710e-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7710e-111">移至系統管理中心 <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="7710e-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/?linkid=867439" target="_blank">https://admin.teams.microsoft.com</a>.</span></span>

2. <span data-ttu-id="7710e-112">在左側導覽中，移至 [會議]\*\*\*\*  >  [會議設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7710e-112">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="7710e-113">在 [參與者]\*\*\*\* 底下，開啟 [匿名使用者可加入會議]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7710e-113">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="7710e-114">![系統管理中心中會議的參與者設定螢幕擷取畫面](media/meeting-settings-participants.png "Microsoft Teams 系統管理中心中 Teams 會議的參與者設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="7710e-114">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="7710e-115">如果您不想讓匿名使用者加入由組織中的使用者排程的會議，請關閉此設定。</span><span class="sxs-lookup"><span data-stu-id="7710e-115">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="7710e-116">自訂會議邀請</span><span class="sxs-lookup"><span data-stu-id="7710e-116">Customize meeting invitations</span></span>

<span data-ttu-id="7710e-117">您可以自訂 Teams 會議邀請來滿足組織的需求。</span><span class="sxs-lookup"><span data-stu-id="7710e-117">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="7710e-118">您可以新增組織的標誌，並提供實用的資訊，例如支援網站和法律免責聲明的連結，以及純文字的頁尾。</span><span class="sxs-lookup"><span data-stu-id="7710e-118">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="7710e-119">建立會議邀請標誌的秘訣</span><span class="sxs-lookup"><span data-stu-id="7710e-119">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="7710e-120">建立不超過寬度 188 像素 \* 高度 30 像素 (相當小) 的影像。</span><span class="sxs-lookup"><span data-stu-id="7710e-120">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="7710e-121">將影像儲存為 JPG 或 PNG 格式。</span><span class="sxs-lookup"><span data-stu-id="7710e-121">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="7710e-122">將影像儲存在收到邀請的每個人都可以存取的位置，例如公用網站。</span><span class="sxs-lookup"><span data-stu-id="7710e-122">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="7710e-123">現在您可以將它新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="7710e-123">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="7710e-124">請參閱後續的步驟。</span><span class="sxs-lookup"><span data-stu-id="7710e-124">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="7710e-125">自訂您的會議邀請</span><span class="sxs-lookup"><span data-stu-id="7710e-125">Customize your meeting invitations</span></span>

<span data-ttu-id="7710e-126">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="7710e-126">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="7710e-127">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7710e-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>..</span></span>
2. <span data-ttu-id="7710e-128">在左側導覽中，移至 [會議]\*\*\*\*  >  [會議設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7710e-128">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="7710e-129">在 [電子郵件邀請]\*\*\*\* 底下，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7710e-129">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="7710e-130">![您可以自訂的會議邀請設定的螢幕擷取畫面](media/meeting-settings-invitation.png "您可以為 Teams 會議自訂的會議邀請設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="7710e-130">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="7710e-131">**標誌 URL**：輸入儲存標誌所在的 URL。</span><span class="sxs-lookup"><span data-stu-id="7710e-131">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="7710e-132">**法律聲明 URL**：如果您的組織有您想要讓其他人有任何法律方面的顧慮時前往的法律網站，請在此輸入其 URL。</span><span class="sxs-lookup"><span data-stu-id="7710e-132">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="7710e-133">**說明 URL**：如果您的組織有當其他人遇到問題時可前往的支援網站，請在這裡輸入其 URL。</span><span class="sxs-lookup"><span data-stu-id="7710e-133">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="7710e-134">**頁尾**：輸入要包含做為頁尾的文字。</span><span class="sxs-lookup"><span data-stu-id="7710e-134">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="7710e-135">按一下 [預覽邀請]\*\*\*\* 以查看會議邀請的預覽。</span><span class="sxs-lookup"><span data-stu-id="7710e-135">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="7710e-136">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7710e-136">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="7710e-137">等候一小時的時間，讓變更傳播。</span><span class="sxs-lookup"><span data-stu-id="7710e-137">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="7710e-138">然後排程 Teams 會議，以查看會議邀請的外觀。</span><span class="sxs-lookup"><span data-stu-id="7710e-138">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="7710e-139">設定您想要如何處理 Teams 會議的即時媒體流量</span><span class="sxs-lookup"><span data-stu-id="7710e-139">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="7710e-140"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="7710e-140"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="7710e-141">如果您使用的是服務品質（QoS）來設定網路流量的優先順序，您可以為每種媒體流量啟用 QoS 標記和設定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="7710e-141">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="7710e-142">針對不同流量類型設定連接埠範圍，在處理即時媒體中只需一個步驟；如需更多詳細資訊，請參閱 [Teams 中的服務品質 (QoS)](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="7710e-142">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7710e-143">如果您在 [團隊服務] 的 Microsoft [團隊管理中心] 啟用 [QoS] 或 [變更設定]，您也必須[將 [相符] 設定套用到所有的使用者裝置](QoS-in-Teams-clients.md)和所有內部網路裝置，才能完全實現團隊中的 QoS 變更。</span><span class="sxs-lookup"><span data-stu-id="7710e-143">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="7710e-144">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="7710e-144">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="7710e-145">移至系統<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>。</span><span class="sxs-lookup"><span data-stu-id="7710e-145">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>
2. <span data-ttu-id="7710e-146">在左側導覽中，移至 [會議]\*\*\*\*  >  [會議設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7710e-146">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="7710e-147">在 [網路]\*\*\*\* 底下，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7710e-147">Under **Network**, do the following:</span></span>

    <span data-ttu-id="7710e-148">![系統管理中心中會議的會議設定螢幕擷取畫面](media/meeting-settings-network.png "Microsoft Teams 系統管理中心中 Teams 會議的網路設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="7710e-148">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="7710e-149">若要允許將 DSCP 標記用於 QoS，請開啟 [插入即時媒體流量的服務品質 (QoS) 標記]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="7710e-149">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="7710e-150">您只能選擇是否使用標記；無法為每個流量類型設定自訂標記。</span><span class="sxs-lookup"><span data-stu-id="7710e-150">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="7710e-151">如需有關 DSCP 標記的詳細資訊，請參閱[選取 QoS 實作方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="7710e-151">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="7710e-152">開啟 [插入即時媒體流量的服務品質 (QoS) 標記]\*\*\*\*，將啟用使用 UDP 連接埠 3479 (音訊)、3480 (視訊) 和 3481 (共用) 對傳輸轉送的通訊。</span><span class="sxs-lookup"><span data-stu-id="7710e-152">Turning on **Insert Quality of Service (QoS) markers for real-time media traffic** will also enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video) and 3481 (Sharing).</span></span>
    - <span data-ttu-id="7710e-153">若要指定連接埠範圍，請在 [選取各即時媒體流量類型的連接埠範圍]\*\*\*\* 旁選取 [指定連接埠範圍]\*\*\*\*，然後輸入音訊、視訊和螢幕共用的開始和結束連接埠。</span><span class="sxs-lookup"><span data-stu-id="7710e-153">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="7710e-154">若要實作 QoS，需要選取此選項。</span><span class="sxs-lookup"><span data-stu-id="7710e-154">Selecting this option is required to implement QoS.</span></span>
        > [!IMPORTANT]
        > <span data-ttu-id="7710e-155">如果您選取 [自動使用任何可用的連接埠]\*\*\*\*，則會使用 1024 和 65535 之間的可用連接埠。</span><span class="sxs-lookup"><span data-stu-id="7710e-155">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="7710e-156">只有在不實作 QoS 時才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="7710e-156">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="7710e-157">選取太窄的連接埠範圍會導致通話中斷和通話品質不佳。</span><span class="sxs-lookup"><span data-stu-id="7710e-157">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="7710e-158">以下應視為最基本的建議。</span><span class="sxs-lookup"><span data-stu-id="7710e-158">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="7710e-159">如果您不確定要在環境中使用的連接埠範圍，使用下列設定應該是良好的起點。</span><span class="sxs-lookup"><span data-stu-id="7710e-159">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="7710e-160">若要深入了解，請參閱[在 Microsoft Teams 中實作服務品質 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="7710e-160">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="7710e-161">以下是 Teams 和 ExpressRoute 所使用的必要 DSCP 標記，以及建議的對應媒體連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="7710e-161">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="7710e-162">連接埠範圍和 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="7710e-162">Port ranges and DSCP markings</span></span>

<span data-ttu-id="7710e-163">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="7710e-163">Media traffic type</span></span>| <span data-ttu-id="7710e-164">用戶端來源連接埠範圍 \*</span><span class="sxs-lookup"><span data-stu-id="7710e-164">Client source port range \*</span></span> |<span data-ttu-id="7710e-165">通訊協定</span><span class="sxs-lookup"><span data-stu-id="7710e-165">Protocol</span></span>|<span data-ttu-id="7710e-166">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="7710e-166">DSCP value</span></span>|<span data-ttu-id="7710e-167">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="7710e-167">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="7710e-168">音訊</span><span class="sxs-lookup"><span data-stu-id="7710e-168">Audio</span></span>            | <span data-ttu-id="7710e-169">50,000-50,019</span><span class="sxs-lookup"><span data-stu-id="7710e-169">50,000–50,019</span></span>               |<span data-ttu-id="7710e-170">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7710e-170">TCP/UDP</span></span> |<span data-ttu-id="7710e-171">46</span><span class="sxs-lookup"><span data-stu-id="7710e-171">46</span></span>        |<span data-ttu-id="7710e-172">快速式轉送 (EF)</span><span class="sxs-lookup"><span data-stu-id="7710e-172">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="7710e-173">影片</span><span class="sxs-lookup"><span data-stu-id="7710e-173">Video</span></span>            | <span data-ttu-id="7710e-174">50,020-50,039</span><span class="sxs-lookup"><span data-stu-id="7710e-174">50,020–50,039</span></span>               |<span data-ttu-id="7710e-175">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7710e-175">TCP/UDP</span></span> |<span data-ttu-id="7710e-176">34</span><span class="sxs-lookup"><span data-stu-id="7710e-176">34</span></span>        |<span data-ttu-id="7710e-177">保證式轉送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="7710e-177">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="7710e-178">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="7710e-178">Application/Screen Sharing</span></span>| <span data-ttu-id="7710e-179">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="7710e-179">50,040–50,059</span></span>      |<span data-ttu-id="7710e-180">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="7710e-180">TCP/UDP</span></span> |<span data-ttu-id="7710e-181">滿</span><span class="sxs-lookup"><span data-stu-id="7710e-181">18</span></span>        |<span data-ttu-id="7710e-182">保證式轉送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="7710e-182">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="7710e-183">\* 您指定的連接埠範圍不能重疊，且必須彼此相接。</span><span class="sxs-lookup"><span data-stu-id="7710e-183">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="7710e-184">在使用 QoS 一段時間後，您將會獲得這三個工作負載相關需求的使用資訊，而且您可以根據自己的特定需求來選擇要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="7710e-184">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="7710e-185">[通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)對此應該有幫助。</span><span class="sxs-lookup"><span data-stu-id="7710e-185">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
