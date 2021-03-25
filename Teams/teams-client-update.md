---
title: Teams 更新
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: annaray
search.appverid: MET150
f1.keywords:
- NOCSH
description: 在本文中，您將瞭解更新 Microsoft Teams 桌面用戶端背後的程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 68e26325f4efcc5ffd7731b73e397f1f96579dd5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119242"
---
# <a name="teams-update-process"></a><span data-ttu-id="8b62e-103">Teams 更新程式</span><span class="sxs-lookup"><span data-stu-id="8b62e-103">Teams update process</span></span>

<span data-ttu-id="8b62e-104">Teams Web App 每週更新一次。</span><span class="sxs-lookup"><span data-stu-id="8b62e-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="8b62e-105">透過我們的技術採用計畫與 TAP (，每兩周發佈一次 Teams 桌面) 。</span><span class="sxs-lookup"><span data-stu-id="8b62e-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="8b62e-106">更新通常會在星期二進行。</span><span class="sxs-lookup"><span data-stu-id="8b62e-106">The update usually takes place on a Tuesday.</span></span> <span data-ttu-id="8b62e-107">如果需要重大更新，Teams 會忽略此排程，並儘快發佈更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="8b62e-108">桌面用戶端會自動更新本身。</span><span class="sxs-lookup"><span data-stu-id="8b62e-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="8b62e-109">Teams 會每隔幾個小時在幕後檢查更新、下載更新，然後等待電腦閒置，再以無提示方式安裝更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="8b62e-110">使用者也可以選取應用程式右上方的設定檔下拉式功能表上的檢查更新，以手動下載更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-110">Users can also manually download updates by selecting **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="8b62e-111">如果有可用的更新，系統就會在電腦閒置時下載並以無提示方式安裝更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="8b62e-112">使用者必須登錄，以下載更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-112">Users need to be signed in for updates to be downloaded.</span></span>

<span data-ttu-id="8b62e-113">自 2019 年 7 月 31 日起，Teams 用戶端更新在更新期間會使用較低的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="8b62e-113">Starting July 31, 2019, Teams client updates use lower network bandwidth during the update.</span></span> <span data-ttu-id="8b62e-114">此更新預設為開啟，且不需要系統管理員或使用者執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="8b62e-114">This update is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="8b62e-115">適用于企業的 Microsoft 365 App 更新呢？</span><span class="sxs-lookup"><span data-stu-id="8b62e-115">What about updates to Microsoft 365 Apps for enterprise?</span></span>

<span data-ttu-id="8b62e-116">根據預設，Teams 會安裝新的 Microsoft 365 企業版應用程式安裝，如使用 [Microsoft 365](/DeployOffice/teams-install)企業版 App 部署 Microsoft Teams 中所述。</span><span class="sxs-lookup"><span data-stu-id="8b62e-116">Teams is installed by default with new installations of Microsoft 365 Apps for enterprise as described in [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).</span></span>

<span data-ttu-id="8b62e-117">如上所述，Teams 會遵循自己的更新程式。</span><span class="sxs-lookup"><span data-stu-id="8b62e-117">Teams follows its own update process as outlined above.</span></span> <span data-ttu-id="8b62e-118">Teams 不會遵循其他辦公室應用程式的更新程式，例如 Word 和 Excel。</span><span class="sxs-lookup"><span data-stu-id="8b62e-118">Teams doesn't follow the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="8b62e-119">若要深入瞭解，請參閱 [企業版 Microsoft 365 應用程式更新通道概觀](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="8b62e-119">To learn more, read [Overview of update channels for Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="8b62e-120">VDI 上的 Teams 更新呢？</span><span class="sxs-lookup"><span data-stu-id="8b62e-120">What about updates to Teams on VDI?</span></span>


<span data-ttu-id="8b62e-121">虛擬桌面基礎結構上的 Teams (VDI) 不會以非 VDI Teams 用戶端的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-121">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="8b62e-122">您必須按照在 VDI 上安裝 Teams 的指示，安裝新的 [MSI](teams-for-vdi.md)來更新 VM 映射。</span><span class="sxs-lookup"><span data-stu-id="8b62e-122">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](teams-for-vdi.md).</span></span> <span data-ttu-id="8b62e-123">您必須卸載目前的版本，以更新至較新版本。</span><span class="sxs-lookup"><span data-stu-id="8b62e-123">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="8b62e-124">系統管理員可以部署更新，而不是 Teams 自動更新嗎？</span><span class="sxs-lookup"><span data-stu-id="8b62e-124">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="8b62e-125">Teams 不會提供系統管理員透過任何傳遞機制部署更新的能力。</span><span class="sxs-lookup"><span data-stu-id="8b62e-125">Teams doesn't give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="8b62e-126">維護協定</span><span class="sxs-lookup"><span data-stu-id="8b62e-126">Servicing agreement</span></span>

<span data-ttu-id="8b62e-127">Teams 用戶端是一種新式線上服務，每兩周自動更新一次。</span><span class="sxs-lookup"><span data-stu-id="8b62e-127">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="8b62e-128">由於 Teams 受新式生命週期策略所規範，因此使用者預期會維持在桌面用戶端的最新版本。</span><span class="sxs-lookup"><span data-stu-id="8b62e-128">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="8b62e-129">自動更新可確保使用者擁有最新的功能、增強功能、安全性和服務可靠性。</span><span class="sxs-lookup"><span data-stu-id="8b62e-129">Auto-updates ensure that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="8b62e-130">若要識別桌面用戶端何時過期，如果使用者的目前版本介於 1 到 3 個月之間，以及是否有可用的新版本，則會顯示應用程式內通知。</span><span class="sxs-lookup"><span data-stu-id="8b62e-130">To identify when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="8b62e-131">此 App 內訊息可鼓勵使用者更新至最新版本的 Teams，或在必要時與 IT 系統管理員聯繫以執行這項操作。</span><span class="sxs-lookup"><span data-stu-id="8b62e-131">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="8b62e-132">超過三個月的 Teams 桌面用戶端使用者會看到封鎖頁面，提供現在更新、連至 IT 系統管理員或繼續使用 Teams 網頁版的選項。</span><span class="sxs-lookup"><span data-stu-id="8b62e-132">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="8b62e-133">第一次安裝及/或第一次執行 Teams 時超過 3 個月的桌面用戶端版本，在遇到上述維護資訊之前，有 28 天的寬限期。</span><span class="sxs-lookup"><span data-stu-id="8b62e-133">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="8b62e-134">在此期間，自動更新程式會更新 Teams 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8b62e-134">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="8b62e-135">如果未更新，使用者會看到應用程式內通知，鼓勵他們手動更新至最新版本的 Teams。</span><span class="sxs-lookup"><span data-stu-id="8b62e-135">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams.</span></span> <span data-ttu-id="8b62e-136">系統可能會提示使用者與 IT 系統管理員聯繫以進行更新。</span><span class="sxs-lookup"><span data-stu-id="8b62e-136">The users might be prompted to contact their IT admin to do the update.</span></span> <span data-ttu-id="8b62e-137">這包括使用 Teams 桌面用戶端作為 Microsoft 365 應用程式企業套件一部分的使用者。</span><span class="sxs-lookup"><span data-stu-id="8b62e-137">This includes users using the Teams desktop client as part of the Microsoft 365 Apps for enterprise bundle.</span></span>

<span data-ttu-id="8b62e-138">在進一步通知之前，政府雲端上的 Teams 桌面用戶端目前有此服務協定的例外。</span><span class="sxs-lookup"><span data-stu-id="8b62e-138">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="8b62e-139">有關新版本發行的資訊，請查看 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或前往說明  >  **用戶端** 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="8b62e-139">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
