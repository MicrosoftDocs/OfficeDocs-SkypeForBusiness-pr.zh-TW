---
title: 在 Microsoft Teams 中設定桌面共用
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何設定會議策略，讓使用者在聊天或會議中Teams桌面。
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 35db312d7a4530f05db3cbad59d1b2b29a4e3847
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856462"
---
# <a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="1bd97-103">在 Microsoft Teams 中設定桌面共用</span><span class="sxs-lookup"><span data-stu-id="1bd97-103">Configure desktop sharing in Microsoft Teams</span></span>

<span data-ttu-id="1bd97-104">桌面共用可讓使用者在會議或聊天時顯示螢幕畫面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bd97-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="1bd97-105">系統管理員可以在 Microsoft Teams 中設定螢幕畫面共用，讓使用者共用整個畫面、應用程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="1bd97-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="1bd97-106">您可以讓使用者授與或要求控制權、允許 PowerPoint 共用、新增白板，並允許共用筆記。</span><span class="sxs-lookup"><span data-stu-id="1bd97-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="1bd97-107">您也可以設定匿名或外部使用者是否可以要求共用畫面的控制權。</span><span class="sxs-lookup"><span data-stu-id="1bd97-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span> <span data-ttu-id="1bd97-108">Teams 會議的外部參與者可依如下分類：</span><span class="sxs-lookup"><span data-stu-id="1bd97-108">External participants in Teams meetings can be categorized as follows:</span></span>

- <span data-ttu-id="1bd97-109">匿名使用者</span><span class="sxs-lookup"><span data-stu-id="1bd97-109">Anonymous user</span></span>
- <span data-ttu-id="1bd97-110">來賓使用者</span><span class="sxs-lookup"><span data-stu-id="1bd97-110">Guest users</span></span>
- <span data-ttu-id="1bd97-111">B2B 使用者</span><span class="sxs-lookup"><span data-stu-id="1bd97-111">B2B user</span></span>
- <span data-ttu-id="1bd97-112">同盟使用者</span><span class="sxs-lookup"><span data-stu-id="1bd97-112">Federated user</span></span>

<span data-ttu-id="1bd97-113">若要設定螢幕畫面共用，請建立新的會議原則，然後將它指派給您要管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="1bd97-113">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="1bd97-114">**在 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="1bd97-114">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="1bd97-115">選取 [會議] > [會議原則]。</span><span class="sxs-lookup"><span data-stu-id="1bd97-115">Select **Meetings** > **Meeting policies**.</span></span>

    ![已選取會議政策](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="1bd97-117">在會議 **政策頁面上\*\*\*\*，選取** 新增 。</span><span class="sxs-lookup"><span data-stu-id="1bd97-117">On the **Meeting policies** page, select **Add**.</span></span>

    ![會議政策訊息](media/addMeeting.png)

3. <span data-ttu-id="1bd97-119">為您的原則指定唯一的標題，然後輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="1bd97-119">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="1bd97-120">在 [內容共用] 底下，從下拉式清單中選擇 [螢幕畫面分享模式]：</span><span class="sxs-lookup"><span data-stu-id="1bd97-120">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="1bd97-121">**整個螢幕**：讓使用者共用整個桌面。</span><span class="sxs-lookup"><span data-stu-id="1bd97-121">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="1bd97-122">**單一應用程式**：讓使用者將螢幕畫面分享限制在單一使用中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bd97-122">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="1bd97-123">**已停用**：關閉螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="1bd97-123">**Disabled** – Turns off screen sharing.</span></span>

    ![共用模式選項](media/configure-desktop-sharing-image3.png)

  > [!Note]
  > <span data-ttu-id="1bd97-125">您不需要啟用通話策略，使用者才能從聊天使用螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="1bd97-125">You don't have to enable the calling policy in order for users to use screen share from chat.</span></span> <span data-ttu-id="1bd97-126">不過，他們的音訊會關閉，直到他們自行取消靜音。</span><span class="sxs-lookup"><span data-stu-id="1bd97-126">However, their audio is turned off until they unmute themselves.</span></span> <span data-ttu-id="1bd97-127">此外，共用螢幕的使用者可以按一下 [ **新增音訊** > 以啟用音訊。</span><span class="sxs-lookup"><span data-stu-id="1bd97-127">In addition, the user sharing the screen can click **Add Audio** to enable audio.</span></span> <span data-ttu-id="1bd97-128">如果通話政策已停用，使用者將無法從聊天會話將音訊新增到螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="1bd97-128">If the calling policy is disabled, users won't be able to add audio to the screen share from a chat session.</span></span>

5. <span data-ttu-id="1bd97-129">開啟或關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="1bd97-129">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="1bd97-130">**允許參與者提供或要求控制權** ，讓小組成員提供或要求控制簡報者的桌面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="1bd97-130">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="1bd97-131">**允許外部參與者提供或要求控制權** - 這是每個使用者的政策。</span><span class="sxs-lookup"><span data-stu-id="1bd97-131">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="1bd97-132">不論會議召集人的設定為何，無論組織是否為使用者設定此選項，都無法控制外部參與者可以執行的動作。</span><span class="sxs-lookup"><span data-stu-id="1bd97-132">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="1bd97-133">此參數會根據分享者在其組織的會議原則中所設定的內容，是否可以授與外部參與者控制或要求控制分享者的螢幕畫面。</span><span class="sxs-lookup"><span data-stu-id="1bd97-133">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="1bd97-134">**允許 PowerPoint 分享**：讓使用者建立可讓 PowerPoint 簡報上傳並共用的會議。</span><span class="sxs-lookup"><span data-stu-id="1bd97-134">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="1bd97-135">**允許使用白板**：讓使用者共用白板。</span><span class="sxs-lookup"><span data-stu-id="1bd97-135">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="1bd97-136">**允許共用記事**：讓使用者記共用記事。</span><span class="sxs-lookup"><span data-stu-id="1bd97-136">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="1bd97-137">按一下 [儲存]。</span><span class="sxs-lookup"><span data-stu-id="1bd97-137">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="1bd97-138">使用 PowerShell 來設定共用桌面</span><span class="sxs-lookup"><span data-stu-id="1bd97-138">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="1bd97-139">您也可以使用 [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) Cmdlet 來控制桌面共用。</span><span class="sxs-lookup"><span data-stu-id="1bd97-139">You can also use the [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="1bd97-140">設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="1bd97-140">Set the following parameters:</span></span>

- <span data-ttu-id="1bd97-141">描述</span><span class="sxs-lookup"><span data-stu-id="1bd97-141">Description</span></span>
- <span data-ttu-id="1bd97-142">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="1bd97-142">ScreenSharingMode</span></span>
- <span data-ttu-id="1bd97-143">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="1bd97-143">AllowPrivateCalling</span></span>
- <span data-ttu-id="1bd97-144">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="1bd97-144">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="1bd97-145">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="1bd97-145">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="1bd97-146">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="1bd97-146">AllowPowerPointSharing</span></span>
- <span data-ttu-id="1bd97-147">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="1bd97-147">AllowWhiteboard</span></span>
- <span data-ttu-id="1bd97-148">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="1bd97-148">AllowSharedNotes</span></span>

<span data-ttu-id="1bd97-149">[深入了解如何使用 csTeamsMeetingPolicy Cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) (英文)。</span><span class="sxs-lookup"><span data-stu-id="1bd97-149">[Learn more about using the csTeamsMeetingPolicy cmdlet](/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>