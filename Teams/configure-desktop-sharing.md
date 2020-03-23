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
description: 設定會議原則，讓使用者在 Teams 聊天或會議中共用桌面
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366aaeb4f48670ae04d4b53d21196ef2d9e81fb4
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825541"
---
<a name="configure-desktop-sharing-in-microsoft-teams"></a><span data-ttu-id="26cc4-103">在 Microsoft Teams 中設定桌面共用</span><span class="sxs-lookup"><span data-stu-id="26cc4-103">Configure desktop sharing in Microsoft Teams</span></span>
============================================

<span data-ttu-id="26cc4-104">桌面共用可讓使用者在會議或聊天時顯示螢幕畫面或應用程式。</span><span class="sxs-lookup"><span data-stu-id="26cc4-104">Desktop sharing lets users present a screen or app during a meeting or chat.</span></span> <span data-ttu-id="26cc4-105">系統管理員可以在 Microsoft Teams 中設定螢幕畫面分享，讓使用者共用整個畫面、應用程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="26cc4-105">Admins can configure screen sharing in Microsoft Teams to let users share an entire screen, an app, or a file.</span></span> <span data-ttu-id="26cc4-106">您可以讓使用者授與或要求控制權、允許 PowerPoint 共用、新增白板，並允許共用筆記。</span><span class="sxs-lookup"><span data-stu-id="26cc4-106">You can let users give or request control, allow PowerPoint sharing, add a whiteboard, and allow shared notes.</span></span> <span data-ttu-id="26cc4-107">您也可以設定匿名或外部使用者是否可以要求共用畫面的控制權。</span><span class="sxs-lookup"><span data-stu-id="26cc4-107">You can also configure whether anonymous or external users can request control of the shared screen.</span></span>

<span data-ttu-id="26cc4-108">若要設定螢幕畫面分享，請建立新的會議原則，然後將它指派給您要管理的使用者。</span><span class="sxs-lookup"><span data-stu-id="26cc4-108">To configure screen sharing, you create a new meetings policy and then assign it to the users you want to manage.</span></span>

<span data-ttu-id="26cc4-109">**在 [Microsoft Teams 系統管理中心](https://admin.teams.microsoft.com/)**</span><span class="sxs-lookup"><span data-stu-id="26cc4-109">**In the [Microsoft Teams admin center](https://admin.teams.microsoft.com/)**</span></span>

1. <span data-ttu-id="26cc4-110">選取**會議** > **會議原則**。</span><span class="sxs-lookup"><span data-stu-id="26cc4-110">Select **Meetings** > **Meeting policies**.</span></span>

    ![顯示已選取會議原則的螢幕擷取畫面](media/configure-desktop-sharing-image1.png)

2. <span data-ttu-id="26cc4-112">在**會議原則** 頁面上，選取**新原則**。</span><span class="sxs-lookup"><span data-stu-id="26cc4-112">On the **Meeting policies** page, select **New policy**.</span></span>

    ![顯示已選取會議原則的訊息](media/configure-desktop-sharing-image2.png)

3. <span data-ttu-id="26cc4-114">為您的原則指定唯一的標題，然後輸入簡短的描述。</span><span class="sxs-lookup"><span data-stu-id="26cc4-114">Give your policy a unique title and enter a brief description.</span></span>

4. <span data-ttu-id="26cc4-115">在 **內容共用**底下，從下拉式清單中選擇 **螢幕畫面分享模式**：</span><span class="sxs-lookup"><span data-stu-id="26cc4-115">Under **Content sharing**, choose a **Screen sharing mode** from the drop-down list:</span></span>

   - <span data-ttu-id="26cc4-116">**整個螢幕**：讓使用者共用整個桌面。</span><span class="sxs-lookup"><span data-stu-id="26cc4-116">**Entire screen** – lets users share their entire desktop.</span></span>
   - <span data-ttu-id="26cc4-117">**單一應用程式**：讓使用者將螢幕畫面分享限制在單一使用中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="26cc4-117">**Single application** – lets users limit screen sharing to a single active application.</span></span>
   - <span data-ttu-id="26cc4-118">**已停用**：關閉螢幕畫面分享。</span><span class="sxs-lookup"><span data-stu-id="26cc4-118">**Disabled** – Turns off screen sharing.</span></span>

    ![顯示共用模式選項的螢幕擷取畫面](media/configure-desktop-sharing-image3.png)

5. <span data-ttu-id="26cc4-120">開啟或關閉下列設定：</span><span class="sxs-lookup"><span data-stu-id="26cc4-120">Turn the following settings on or off:</span></span>

    - <span data-ttu-id="26cc4-121">**允許參與者授與或要求控制權**：讓小組成員可以授與或要求簡報者的桌面或應用程式控制權。</span><span class="sxs-lookup"><span data-stu-id="26cc4-121">**Allow a participant to give or request control** – lets members of the team give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="26cc4-122">**允許外部參與者授與或要求控制**：可讓來賓與外部 (同盟) 使用者對簡報者的桌面或應用程式授與或要求控制權。</span><span class="sxs-lookup"><span data-stu-id="26cc4-122">**Allow an external participant to give or request control** – lets guests and external (federated) users give or request control of the presenter’s desktop or application.</span></span>
    - <span data-ttu-id="26cc4-123">**允許 PowerPoint 分享**：讓使用者建立可讓 PowerPoint 簡報上傳並共用的會議。</span><span class="sxs-lookup"><span data-stu-id="26cc4-123">**Allow PowerPoint sharing** - lets users create meetings that allow PowerPoint presentations to be uploaded and shared.</span></span>
    - <span data-ttu-id="26cc4-124">**允許使用白板**：讓使用者共用白板。</span><span class="sxs-lookup"><span data-stu-id="26cc4-124">**Allow whiteboard** – lets users share a whiteboard.</span></span>
    - <span data-ttu-id="26cc4-125">**允許共用的筆記**：讓使用者記共用筆記。</span><span class="sxs-lookup"><span data-stu-id="26cc4-125">**Allow shared notes** – lets users take shared notes.</span></span>

6. <span data-ttu-id="26cc4-126">按一下 [儲存]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="26cc4-126">Click **Save**.</span></span>

## <a name="use-powershell-to-configure-shared-desktop"></a><span data-ttu-id="26cc4-127">使用 PowerShell 來設定共用桌面</span><span class="sxs-lookup"><span data-stu-id="26cc4-127">Use PowerShell to configure shared desktop</span></span>

<span data-ttu-id="26cc4-128">您也可以使用 [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) Cmdlet 來控制桌面共用。</span><span class="sxs-lookup"><span data-stu-id="26cc4-128">You can also use the [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) cmdlet to control desktop sharing.</span></span> <span data-ttu-id="26cc4-129">設定下列參數：</span><span class="sxs-lookup"><span data-stu-id="26cc4-129">Set the following parameters:</span></span>

- <span data-ttu-id="26cc4-130">描述</span><span class="sxs-lookup"><span data-stu-id="26cc4-130">Description</span></span>
- <span data-ttu-id="26cc4-131">ScreenSharingMode</span><span class="sxs-lookup"><span data-stu-id="26cc4-131">ScreenSharingMode</span></span>
- <span data-ttu-id="26cc4-132">AllowParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="26cc4-132">AllowParticipantGiveRequestControl</span></span>
- <span data-ttu-id="26cc4-133">AllowExternalParticipantGiveRequestControl</span><span class="sxs-lookup"><span data-stu-id="26cc4-133">AllowExternalParticipantGiveRequestControl</span></span>
- <span data-ttu-id="26cc4-134">AllowPowerPointSharing</span><span class="sxs-lookup"><span data-stu-id="26cc4-134">AllowPowerPointSharing</span></span>
- <span data-ttu-id="26cc4-135">AllowWhiteboard</span><span class="sxs-lookup"><span data-stu-id="26cc4-135">AllowWhiteboard</span></span>
- <span data-ttu-id="26cc4-136">AllowSharedNotes</span><span class="sxs-lookup"><span data-stu-id="26cc4-136">AllowSharedNotes</span></span>

<span data-ttu-id="26cc4-137">[深入瞭解如何使用 csTeamsMeetingPolicy Cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="26cc4-137">[Learn more about using the csTeamsMeetingPolicy cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps).</span></span>

