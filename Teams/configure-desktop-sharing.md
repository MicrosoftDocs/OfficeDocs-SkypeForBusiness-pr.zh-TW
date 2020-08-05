---
title: 在 Microsoft Teams 中設定桌面共用
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
description: 瞭解如何設定會議原則，讓使用者在團隊聊天或會議中共用其桌面。
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34d7780e1d10370b78c11c1a8021381aff71f479
ms.sourcegitcommit: ab094058e3ffa974527fce8a331dad609ac19609
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552589"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="e0e96-103">在 Microsoft Teams 中設定桌面共用</span><span class="sxs-lookup"><span data-stu-id="e0e96-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="e0e96-104">桌面共用可讓使用者在會議或聊天時顯示螢幕畫面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0e96-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="e0e96-105">系統管理員可以在 Microsoft Teams 中設定螢幕畫面共用，讓使用者共用整個畫面、應用程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="e0e96-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="e0e96-106">您可以讓使用者授與或要求控制權、允許 PowerPoint 共用、新增白板，並允許共用筆記。</span><span class="sxs-lookup"><span data-stu-id="e0e96-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="e0e96-107">您也可以設定匿名或外部使用者是否可以要求共用畫面的控制權。</span><span class="sxs-lookup"><span data-stu-id="e0e96-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="e0e96-108">若要設定螢幕畫面共用，請建立新的會議原則，然後將它指派給您要管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="e0e96-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="e0e96-109">**在 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="e0e96-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="e0e96-110">選取 [會議]\*\*\*\* > [會議原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0e96-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![顯示已選取會議原則的螢幕擷取畫面](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="e0e96-112">在 [會議原則]\*\*\*\* 頁面上，選取 [新原則]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0e96-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![顯示已選取會議原則訊息的螢幕擷取畫面](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="e0e96-114">為您的原則指定唯一的標題，然後輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="e0e96-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="e0e96-115">在 [內容共用]\*\*\*\* 底下，從下拉式清單中選擇 [螢幕畫面分享模式]\*\*\*\*：</span><span class="sxs-lookup"><span data-stu-id="e0e96-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="e0e96-116">**整個螢幕**：讓使用者共用整個桌面。</span><span class="sxs-lookup"><span data-stu-id="e0e96-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="e0e96-117">**單一應用程式**：讓使用者將螢幕畫面分享限制在單一使用中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0e96-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="e0e96-118">**已停用**：關閉螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="e0e96-118">**Disabled** – Turns off screen sharing.</span></span>

    ![顯示共用模式選項的螢幕擷取畫面](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="e0e96-120">開啟或關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="e0e96-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="e0e96-121">[**允許參與者授與要求控制**]：讓小組成員可以授與要求控制簡報者的桌面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0e96-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter's desktop or application.</span></span>
    - <span data-ttu-id="e0e96-122">**允許外部參與者授與要求控制權**（這是每個使用者的原則）。</span><span class="sxs-lookup"><span data-stu-id="e0e96-122">**Allow an external participant to give or request control** – This is a per-user policy.</span></span> <span data-ttu-id="e0e96-123">組織是否有此組使用者無論會議召集人已設定的內容，都不會控制外部參與者所能執行的動作。</span><span class="sxs-lookup"><span data-stu-id="e0e96-123">Whether an organization has this set for a user doesn't control what external participants can do, regardless of what the meeting organizer has set.</span></span> <span data-ttu-id="e0e96-124">這個參數會控制外部參與者是否可以受到控制或要求對共用者的螢幕進行控制，這要視共用資源在組織的會議原則中所設定的內容而定。</span><span class="sxs-lookup"><span data-stu-id="e0e96-124">This parameter controls whether external participants can be given control or request control of the sharer's screen, depending on what the sharer has set within their organization's meeting policies.</span></span>
    - <span data-ttu-id="e0e96-125">**允許 PowerPoint 分享**：讓使用者建立可讓 PowerPoint 簡報上傳並共用的會議。</span><span class="sxs-lookup"><span data-stu-id="e0e96-125">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="e0e96-126">**允許使用白板**：讓使用者共用白板。</span><span class="sxs-lookup"><span data-stu-id="e0e96-126">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="e0e96-127">**允許共用記事**：讓使用者記共用記事。</span><span class="sxs-lookup"><span data-stu-id="e0e96-127">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="e0e96-128">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e0e96-128">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="e0e96-129">使用 PowerShell 來設定共用桌面</span><span class="sxs-lookup"><span data-stu-id="e0e96-129">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="e0e96-130">您也可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) Cmdlet 來控制桌面共用。</span><span class="sxs-lookup"><span data-stu-id="e0e96-130">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="e0e96-131">設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="e0e96-131">Set the following parameters:</span></span>

- <span data-ttu-id="e0e96-132">描述</span><span class="sxs-lookup"><span data-stu-id="e0e96-132">Description</span></span>
- <span data-ttu-id="e0e96-133">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="e0e96-133">ScreenSharingMode</span></span>
- <span data-ttu-id="e0e96-134">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="e0e96-134">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="e0e96-135">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="e0e96-135">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="e0e96-136">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="e0e96-136">AllowPowerPointSharing</span></span>
- <span data-ttu-id="e0e96-137">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="e0e96-137">AllowWhiteboard</span></span>
- <span data-ttu-id="e0e96-138">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="e0e96-138">AllowSharedNotes</span></span>

<span data-ttu-id="e0e96-139">[深入了解如何使用 csTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) (英文)。</span><span class="sxs-lookup"><span data-stu-id="e0e96-139">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

