---
title: 在 Microsoft 團隊中設定桌面共用
author: LolaJacobsen
ms.author: Lolaj
manager: serdars
ms.reviewer: jastark
ms.date: 03/22/2019
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 設定會議原則，讓使用者在團隊聊天或會議中共用其桌面
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 99c6e2a5adb9d0f9a4b4e3f6f17b7484bda96a74
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/15/2019
ms.locfileid: "37516883"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="d0ddc-103">在 Microsoft 團隊中設定桌面共用</span><span class="sxs-lookup"><span data-stu-id="d0ddc-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="d0ddc-104">桌面共用可讓使用者在會議或聊天期間呈現畫面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="d0ddc-105">系統管理員可以在 Microsoft 團隊中設定螢幕共用，讓使用者共用整個螢幕、應用程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="d0ddc-106">您可以讓使用者提供或要求控制、允許 PowerPoint 共用、新增白板，以及允許共用筆記。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="d0ddc-107">您也可以設定匿名或外部使用者是否可以要求共用畫面的控制權。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="d0ddc-108">若要設定螢幕共用，您需要建立新的會議原則，然後將它指派給您想要管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="d0ddc-109">**在 Microsoft 團隊系統管理中心**</span><span class="sxs-lookup"><span data-stu-id="d0ddc-109">**In the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="d0ddc-110">選取 [**會議** > **會議原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![顯示已選取會議原則的螢幕擷取畫面](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="d0ddc-112">在 [**會議原則**] 頁面上，選取 [**新增原則**]。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![顯示會議原則訊息的螢幕擷取畫面](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="d0ddc-114">為您的原則命名唯一的標題，然後輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="d0ddc-115">在 [**內容共用**] 底下，從下拉式清單中選擇**螢幕共用模式**：</span><span class="sxs-lookup"><span data-stu-id="d0ddc-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="d0ddc-116">**整個畫面**-讓使用者共用其整個桌面。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="d0ddc-117">**單一應用程式**-讓使用者將螢幕共用限制在單一作用中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="d0ddc-118">[**已停用**]-關閉螢幕共用。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-118">**Disabled** – Turns off screen sharing.</span></span>

    ![顯示共用模式選項的螢幕擷取畫面](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="d0ddc-120">開啟或關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="d0ddc-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="d0ddc-121">[**允許參與者授與要求控制**]：讓小組成員可以授與要求控制簡報者的桌面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="d0ddc-122">[**允許外部參與者授與要求控制**]：讓來賓與外部（同盟）使用者提供或要求簡報者的桌面或應用程式的控制權。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="d0ddc-123">[**允許 powerpoint 共用**]：可讓使用者建立可讓 PowerPoint 簡報上傳及共用的會議。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="d0ddc-124">[**允許使用白板**]-讓使用者共用白板。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="d0ddc-125">[**允許共用筆記**]：讓使用者取得共用筆記。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="d0ddc-126">按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="d0ddc-127">使用 PowerShell 來設定共用桌面</span><span class="sxs-lookup"><span data-stu-id="d0ddc-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="d0ddc-128">您也可以使用[CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) Cmdlet 來控制桌面共用。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="d0ddc-129">設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="d0ddc-129">Set the following parameters:</span></span>

- <span data-ttu-id="d0ddc-130">描述</span><span class="sxs-lookup"><span data-stu-id="d0ddc-130">Description</span></span>
- <span data-ttu-id="d0ddc-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="d0ddc-131">ScreenSharingMode</span></span>
- <span data-ttu-id="d0ddc-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d0ddc-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="d0ddc-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="d0ddc-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="d0ddc-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="d0ddc-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="d0ddc-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="d0ddc-135">AllowWhiteboard</span></span>
- <span data-ttu-id="d0ddc-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="d0ddc-136">AllowSharedNotes</span></span>

<span data-ttu-id="d0ddc-137">[深入瞭解如何使用 csTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="d0ddc-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

