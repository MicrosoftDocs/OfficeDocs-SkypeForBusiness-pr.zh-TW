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
ms.openlocfilehash: 559dcc8a2f5e38c4c35ba7794241e69402a092ef
ms.sourcegitcommit: c573b0be535fcf927ae01d60a7eb8fbf1aec271d
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/30/2020
ms.locfileid: "46526709"
---
# <a name="manage-meeting-settings-in-microsoft-teams"></a><span data-ttu-id="3f3a2-103">在 Microsoft Teams 中管理會議設定</span><span class="sxs-lookup"><span data-stu-id="3f3a2-103">Manage meeting settings in Microsoft Teams</span></span>

<span data-ttu-id="3f3a2-104">身為系統管理員，您可以使用 Teams 會議設定，來控制匿名使用者是否可以加入 Teams 會議、自訂會議邀請，以及如果您要啟用服務品質 (QoS)，則要針對即時流量設定連接範圍。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-104">As an admin, you use Teams meetings settings to control whether anonymous users can join Teams meetings, customize meeting invitations, and if you want to enable Quality of Service (QoS), set port ranges for real-time traffic.</span></span> <span data-ttu-id="3f3a2-105">這些設定適用於使用者在貴組織中排程的所有 Teams 會議。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-105">These settings apply to all Teams meetings that users schedule in your organization.</span></span> <span data-ttu-id="3f3a2-106">您可以在 Microsoft Teams 系統管理中心的 [會議]\*\*\*\*  >  [會議設定]\*\*\*\* 來管理這些設定。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-106">You manage these settings from **Meetings** > **Meeting settings** in the Microsoft Teams admin center.</span></span>

## <a name="allow-anonymous-users-to-join-meetings"></a><span data-ttu-id="3f3a2-107">允許匿名使用者加入會議</span><span class="sxs-lookup"><span data-stu-id="3f3a2-107">Allow anonymous users to join meetings</span></span>

<span data-ttu-id="3f3a2-108">利用匿名加入，任何人都可以按一下會議邀請中的連結，以匿名使用者的身分加入會議。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-108">With anonymous join, anyone can join the meeting as an anonymous user by clicking the link in the meeting invitation.</span></span> <span data-ttu-id="3f3a2-109">若要深入了解，請參閱[在沒有 Teams 帳戶的情況下加入會議](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508)。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-109">To learn more, see [Join a meeting without a Teams account](https://support.office.com/article/join-a-meeting-without-a-teams-account-c6efc38f-4e03-4e79-b28f-e65a4c039508).</span></span>

<span data-ttu-id="3f3a2-110">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="3f3a2-110">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="3f3a2-111">您必須是團隊服務管理員，才能進行這些變更。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-111">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="3f3a2-112">請參閱[使用團隊管理員角色管理團隊](https://docs.microsoft.com/microsoftteams/using-admin-roles)，瞭解如何取得管理員角色和許可權。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-112">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="3f3a2-113">移至系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-113">Go to the admin center.</span></span>

2. <span data-ttu-id="3f3a2-114">在左側導覽中，移至 [會議]\*\*\*\*  >  [會議設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-114">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>

3. <span data-ttu-id="3f3a2-115">在 [參與者]\*\*\*\* 底下，開啟 [匿名使用者可加入會議]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-115">Under **Participants**, turn on **Anonymous users can join a meeting**.</span></span>

    <span data-ttu-id="3f3a2-116">![系統管理中心中會議的參與者設定螢幕擷取畫面](media/meeting-settings-participants.png "Microsoft Teams 系統管理中心中 Teams 會議的參與者設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f3a2-116">![Screenshot of participants settings for meetings in the admin center](media/meeting-settings-participants.png "Screenshot of participants settings for Teams meetings in the Microsoft Teams admin center")</span></span>

> [!CAUTION]
> <span data-ttu-id="3f3a2-117">如果您不想讓匿名使用者加入由組織中的使用者排程的會議，請關閉此設定。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-117">If you don't want anonymous users to join meetings scheduled by users in your organization, turn off this setting.</span></span>

## <a name="customize-meeting-invitations"></a><span data-ttu-id="3f3a2-118">自訂會議邀請</span><span class="sxs-lookup"><span data-stu-id="3f3a2-118">Customize meeting invitations</span></span>

<span data-ttu-id="3f3a2-119">您可以自訂 Teams 會議邀請來滿足組織的需求。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-119">You can customize Teams meeting invitations to meet your organization's needs.</span></span> <span data-ttu-id="3f3a2-120">您可以新增組織的標誌，並提供實用的資訊，例如支援網站和法律免責聲明的連結，以及純文字的頁尾。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-120">You can add your organization's logo and include helpful information, such as links to your support website and legal disclaimer, and a text-only footer.</span></span>

### <a name="tips-for-creating-a-logo-for-meeting-invitations"></a><span data-ttu-id="3f3a2-121">建立會議邀請標誌的秘訣</span><span class="sxs-lookup"><span data-stu-id="3f3a2-121">Tips for creating a logo for meeting invitations</span></span>  

1. <span data-ttu-id="3f3a2-122">建立不超過寬度 188 像素 \* 高度 30 像素 (相當小) 的影像。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-122">Create an image that's no more than 188 pixels wide by 30 pixels tall (it's quite small).</span></span>
2. <span data-ttu-id="3f3a2-123">將影像儲存為 JPG 或 PNG 格式。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-123">Save the image in JPG or PNG format.</span></span>
3. <span data-ttu-id="3f3a2-124">將影像儲存在收到邀請的每個人都可以存取的位置，例如公用網站。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-124">Store the image in a location that everyone receiving the invitation can access, such as a public website.</span></span>

    <span data-ttu-id="3f3a2-125">現在您可以將它新增至會議邀請。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-125">Now you can add it to your meeting invitations.</span></span> <span data-ttu-id="3f3a2-126">請參閱後續的步驟。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-126">See the next steps.</span></span>

### <a name="customize-your-meeting-invitations"></a><span data-ttu-id="3f3a2-127">自訂您的會議邀請</span><span class="sxs-lookup"><span data-stu-id="3f3a2-127">Customize your meeting invitations</span></span>

<span data-ttu-id="3f3a2-128">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="3f3a2-128">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="3f3a2-129">移至系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-129">Go to the admin center.</span></span>
2. <span data-ttu-id="3f3a2-130">在左側導覽中，移至 [會議]\*\*\*\*  >  [會議設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-130">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="3f3a2-131">在 [電子郵件邀請]\*\*\*\* 底下，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f3a2-131">Under **Email invitation**, do the following:</span></span>

    <span data-ttu-id="3f3a2-132">![您可以自訂的會議邀請設定的螢幕擷取畫面](media/meeting-settings-invitation.png "您可以為 Teams 會議自訂的會議邀請設定的螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f3a2-132">![Screenshot of the meeting invitation settings you can customize](media/meeting-settings-invitation.png "Screenshot of the meeting invitation settings that you can customize for Teams meetings")</span></span>

    - <span data-ttu-id="3f3a2-133">**標誌 URL**：輸入儲存標誌所在的 URL。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-133">**Logo URL** Enter the URL where your logo is stored.</span></span>
    - <span data-ttu-id="3f3a2-134">**法律聲明 URL**：如果您的組織有您想要讓其他人有任何法律方面的顧慮時前往的法律網站，請在此輸入其 URL。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-134">**Legal URL** If your organization has a legal website that you want people to go to for any legal concerns, enter the URL here.</span></span>
    - <span data-ttu-id="3f3a2-135">**說明 URL**：如果您的組織有當其他人遇到問題時可前往的支援網站，請在這裡輸入其 URL。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-135">**Help URL** If your organization has a support website that you want people to go to if they run into issues, enter the URL here.</span></span>
    - <span data-ttu-id="3f3a2-136">**頁尾**：輸入要包含做為頁尾的文字。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-136">**Footer** Enter text that you want to include as a footer.</span></span>
4. <span data-ttu-id="3f3a2-137">按一下 [預覽邀請]\*\*\*\* 以查看會議邀請的預覽。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-137">Click **Preview invite** to see a preview of your meeting invitation.</span></span>
5. <span data-ttu-id="3f3a2-138">完成後，按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-138">When you're done, click **Save**.</span></span>
6. <span data-ttu-id="3f3a2-139">等候一小時的時間，讓變更傳播。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-139">Wait an hour or so for the changes to propagate.</span></span> <span data-ttu-id="3f3a2-140">然後排程 Teams 會議，以查看會議邀請的外觀。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-140">Then schedule a Teams meeting to see what the meeting invitation looks like.</span></span>  

## <a name="set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings"></a><span data-ttu-id="3f3a2-141">設定您想要如何處理 Teams 會議的即時媒體流量</span><span class="sxs-lookup"><span data-stu-id="3f3a2-141">Set how you want to handle real-time media traffic for Teams meetings</span></span>

<span data-ttu-id="3f3a2-142"><a name="bknetwork"> </a></span><span class="sxs-lookup"><span data-stu-id="3f3a2-142"><a name="bknetwork"> </a></span></span>

<span data-ttu-id="3f3a2-143">如果您使用的是服務品質（QoS）來設定網路流量的優先順序，您可以為每種媒體流量啟用 QoS 標記和設定埠範圍。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-143">If you're using Quality of Service (QoS)to prioritize network traffic, you can enable QoS markers and set port ranges for each type of media traffic.</span></span> <span data-ttu-id="3f3a2-144">針對不同流量類型設定連接埠範圍，在處理即時媒體中只需一個步驟；如需更多詳細資訊，請參閱 [Teams 中的服務品質 (QoS)](qos-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-144">Setting port ranges for different traffic types is only one step in handling real-time media; see [Quality of Service (QoS) in Teams](qos-in-teams.md) for much more detail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f3a2-145">如果您在 [團隊服務] 的 Microsoft [團隊管理中心] 啟用 [QoS] 或 [變更設定]，您也必須[將 [相符] 設定套用到所有的使用者裝置](QoS-in-Teams-clients.md)和所有內部網路裝置，才能完全實現團隊中的 QoS 變更。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-145">If you enable QoS or change settings in the Microsoft Teams admin center for the Teams service, you'll also need to [apply matching settings to all user devices](QoS-in-Teams-clients.md) and all internal network devices to fully implement the changes to QoS in Teams.</span></span>

 <span data-ttu-id="3f3a2-146">![Microsoft Teams 標誌圖示](media/teams-logo-30x30.png) **使用 Microsoft Teams 系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="3f3a2-146">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>
1. <span data-ttu-id="3f3a2-147">移至系統管理中心。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-147">Go to the admin center.</span></span>
2. <span data-ttu-id="3f3a2-148">在左側導覽中，移至 [會議]\*\*\*\*  >  [會議設定]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-148">In the left navigation, go to **Meetings** > **Meeting settings**.</span></span>
3. <span data-ttu-id="3f3a2-149">在 [網路]\*\*\*\* 底下，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="3f3a2-149">Under **Network**, do the following:</span></span>

    <span data-ttu-id="3f3a2-150">![系統管理中心中會議的會議設定螢幕擷取畫面](media/meeting-settings-network.png "Microsoft Teams 系統管理中心中 Teams 會議的網路設定螢幕擷取畫面")</span><span class="sxs-lookup"><span data-stu-id="3f3a2-150">![Screenshot of the network settings for meetings in the admin center](media/meeting-settings-network.png "Screenshot of the network settings for Teams meetings in the Microsoft Teams admin center")</span></span>

    - <span data-ttu-id="3f3a2-151">若要允許將 DSCP 標記用於 QoS，請開啟 [插入即時媒體流量的服務品質 (QoS) 標記]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-151">To allow DSCP markings to be used for QoS, turn on **Insert Quality of Service (QoS) markers for real-time media traffic**.</span></span> <span data-ttu-id="3f3a2-152">您只能選擇是否使用標記；無法為每個流量類型設定自訂標記。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-152">You only have the option of using markers or not; you can't set custom markers for each traffic type.</span></span> <span data-ttu-id="3f3a2-153">如需有關 DSCP 標記的詳細資訊，請參閱[選取 QoS 實作方法](QoS-in-Teams.md#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-153">See [Select a QoS implementation method](QoS-in-Teams.md#select-a-qos-implementation-method) for more on DSCP markers.</span></span>
        > [!NOTE]
        > <span data-ttu-id="3f3a2-154">DSCP 標記通常是透過來源埠完成，而 UDP 流量預設會以3478的目的地埠路由到傳輸中繼。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-154">DSCP tagging is typically done via Source Ports and UDP traffic will route to Transport Relay with destination port of 3478 by default.</span></span> <span data-ttu-id="3f3a2-155">如果您的公司需要在目的地埠上加上標記，請聯絡支援人員，以便使用 UDP 埠3479（音訊）、3480（影片）和3481（共用）來與傳輸中繼進行通訊。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-155">If your company requires tagging on destination ports, please contact support to enable communication to the Transport Relay with UDP ports 3479 (Audio), 3480 (Video), and 3481 (Sharing).</span></span>
    - <span data-ttu-id="3f3a2-156">若要指定連接埠範圍，請在 [選取各即時媒體流量類型的連接埠範圍]\*\*\*\* 旁選取 [指定連接埠範圍]\*\*\*\*，然後輸入音訊、視訊和螢幕共用的開始和結束連接埠。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-156">To specify port ranges, next to **Select a port range for each type of real-time media traffic**, select  **Specify port ranges**, and then enter the starting and ending ports for audio, video, and screen sharing.</span></span> <span data-ttu-id="3f3a2-157">若要實作 QoS，需要選取此選項。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-157">Selecting this option is required to implement QoS.</span></span>
        > [!IMPORTANT]
        > <span data-ttu-id="3f3a2-158">如果您選取 [自動使用任何可用的連接埠]\*\*\*\*，則會使用 1024 和 65535 之間的可用連接埠。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-158">If you select **Automatically use any available ports**, available ports between 1024 and 65535 are used.</span></span> <span data-ttu-id="3f3a2-159">只有在不實作 QoS 時才使用此選項。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-159">Use this option only when not implementing QoS.</span></span>
        >
        > <span data-ttu-id="3f3a2-160">選取太窄的連接埠範圍會導致通話中斷和通話品質不佳。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-160">Selecting a port range that is too narrow will lead to dropped calls and poor call quality.</span></span> <span data-ttu-id="3f3a2-161">以下應視為最基本的建議。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-161">The recommendations below should be a bare minimum.</span></span>

<span data-ttu-id="3f3a2-162">如果您不確定要在環境中使用的連接埠範圍，使用下列設定應該是良好的起點。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-162">If you're unsure what port ranges to use in your environment, the following settings are a good starting point.</span></span> <span data-ttu-id="3f3a2-163">若要深入了解，請參閱[在 Microsoft Teams 中實作服務品質 (QoS)](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-163">To learn more, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span> <span data-ttu-id="3f3a2-164">以下是 Teams 和 ExpressRoute 所使用的必要 DSCP 標記，以及建議的對應媒體連接埠範圍。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-164">These are the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span>

### <a name="port-ranges-and-dscp-markings"></a><span data-ttu-id="3f3a2-165">連接埠範圍和 DSCP 標記</span><span class="sxs-lookup"><span data-stu-id="3f3a2-165">Port ranges and DSCP markings</span></span>

<span data-ttu-id="3f3a2-166">媒體流量類型</span><span class="sxs-lookup"><span data-stu-id="3f3a2-166">Media traffic type</span></span>| <span data-ttu-id="3f3a2-167">用戶端來源連接埠範圍 \*</span><span class="sxs-lookup"><span data-stu-id="3f3a2-167">Client source port range \*</span></span> |<span data-ttu-id="3f3a2-168">通訊協定</span><span class="sxs-lookup"><span data-stu-id="3f3a2-168">Protocol</span></span>|<span data-ttu-id="3f3a2-169">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="3f3a2-169">DSCP value</span></span>|<span data-ttu-id="3f3a2-170">DSCP 類別</span><span class="sxs-lookup"><span data-stu-id="3f3a2-170">DSCP class</span></span>|
|:---             |:---                         |:---    |:---      |:---      |
|<span data-ttu-id="3f3a2-171">音訊</span><span class="sxs-lookup"><span data-stu-id="3f3a2-171">Audio</span></span>            | <span data-ttu-id="3f3a2-172">50,000-50,019</span><span class="sxs-lookup"><span data-stu-id="3f3a2-172">50,000–50,019</span></span>               |<span data-ttu-id="3f3a2-173">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3f3a2-173">TCP/UDP</span></span> |<span data-ttu-id="3f3a2-174">46</span><span class="sxs-lookup"><span data-stu-id="3f3a2-174">46</span></span>        |<span data-ttu-id="3f3a2-175">快速式轉送 (EF)</span><span class="sxs-lookup"><span data-stu-id="3f3a2-175">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="3f3a2-176">影片</span><span class="sxs-lookup"><span data-stu-id="3f3a2-176">Video</span></span>            | <span data-ttu-id="3f3a2-177">50,020-50,039</span><span class="sxs-lookup"><span data-stu-id="3f3a2-177">50,020–50,039</span></span>               |<span data-ttu-id="3f3a2-178">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3f3a2-178">TCP/UDP</span></span> |<span data-ttu-id="3f3a2-179">34</span><span class="sxs-lookup"><span data-stu-id="3f3a2-179">34</span></span>        |<span data-ttu-id="3f3a2-180">保證式轉送 (AF41)</span><span class="sxs-lookup"><span data-stu-id="3f3a2-180">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="3f3a2-181">應用程式/螢幕共用</span><span class="sxs-lookup"><span data-stu-id="3f3a2-181">Application/Screen Sharing</span></span>| <span data-ttu-id="3f3a2-182">50,040-50,059</span><span class="sxs-lookup"><span data-stu-id="3f3a2-182">50,040–50,059</span></span>      |<span data-ttu-id="3f3a2-183">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="3f3a2-183">TCP/UDP</span></span> |<span data-ttu-id="3f3a2-184">滿</span><span class="sxs-lookup"><span data-stu-id="3f3a2-184">18</span></span>        |<span data-ttu-id="3f3a2-185">保證式轉送 (AF21)</span><span class="sxs-lookup"><span data-stu-id="3f3a2-185">Assured Forwarding (AF21)</span></span>|
| | | | |

<span data-ttu-id="3f3a2-186">\* 您指定的連接埠範圍不能重疊，且必須彼此相接。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-186">\* The port ranges you assign cannot overlap and must be next to each other.</span></span>

<span data-ttu-id="3f3a2-187">在使用 QoS 一段時間後，您將會獲得這三個工作負載相關需求的使用資訊，而且您可以根據自己的特定需求來選擇要進行的變更。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-187">After QoS has been in use for a while, you'll have usage information on the demand for each of these three workloads, and you can choose what changes to make based on your specific needs.</span></span> <span data-ttu-id="3f3a2-188">[通話品質儀表板](turning-on-and-using-call-quality-dashboard.md)對此應該有幫助。</span><span class="sxs-lookup"><span data-stu-id="3f3a2-188">[Call Quality Dashboard](turning-on-and-using-call-quality-dashboard.md) will be helpful with that.</span></span>
