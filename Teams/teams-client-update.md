---
title: Teams更新
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
description: 在本文中，您將瞭解更新桌面用戶端Microsoft Teams程式。
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 004c615d2b624f4e5942562e6abfed6e1aebf7cd
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/02/2021
ms.locfileid: "52717894"
---
# <a name="teams-update-process"></a><span data-ttu-id="85ff9-103">Teams更新程式</span><span class="sxs-lookup"><span data-stu-id="85ff9-103">Teams update process</span></span>

<span data-ttu-id="85ff9-104">Teams Web App 每週更新一次。</span><span class="sxs-lookup"><span data-stu-id="85ff9-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="85ff9-105">Teams透過我們的技術採用計畫與 TAP (，每兩周發佈一次桌面用戶端) 。</span><span class="sxs-lookup"><span data-stu-id="85ff9-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="85ff9-106">更新通常會在星期二進行。</span><span class="sxs-lookup"><span data-stu-id="85ff9-106">The update usually takes place on a Tuesday.</span></span> <span data-ttu-id="85ff9-107">如果需要重大更新，Teams會忽略此排程，並儘快發佈更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="85ff9-108">桌面用戶端會自動更新本身。</span><span class="sxs-lookup"><span data-stu-id="85ff9-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="85ff9-109">Teams每隔幾個小時在幕後檢查更新、下載更新，然後等待電腦閒置，再以無提示方式安裝更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="85ff9-110">使用者也可以選取應用程式右上方的設定檔下拉式功能表上的檢查更新，以手動下載更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-110">Users can also manually download updates by selecting **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="85ff9-111">如果有可用的更新，系統就會在電腦閒置時下載並以無提示方式安裝更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="85ff9-112">使用者必須登錄，以下載更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-112">Users need to be signed in for updates to be downloaded.</span></span>

<span data-ttu-id="85ff9-113">自 2019 年 7 月 31 日起，Teams更新期間，用戶端更新會使用較低的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="85ff9-113">Starting July 31, 2019, Teams client updates use lower network bandwidth during the update.</span></span> <span data-ttu-id="85ff9-114">此更新預設為開啟，且不需要系統管理員或使用者執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="85ff9-114">This update is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-microsoft-365-apps-for-enterprise"></a><span data-ttu-id="85ff9-115">更新至Microsoft 365 Apps 企業版？</span><span class="sxs-lookup"><span data-stu-id="85ff9-115">What about updates to Microsoft 365 Apps for enterprise?</span></span>

<span data-ttu-id="85ff9-116">Teams預設會安裝新的 Microsoft 365 Apps 企業版 安裝，如使用 Microsoft Teams[部署 Microsoft 365 Apps 企業版。](/DeployOffice/teams-install)</span><span class="sxs-lookup"><span data-stu-id="85ff9-116">Teams is installed by default with new installations of Microsoft 365 Apps for enterprise as described in [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/DeployOffice/teams-install).</span></span>

<span data-ttu-id="85ff9-117">Teams遵循上述其更新程式。</span><span class="sxs-lookup"><span data-stu-id="85ff9-117">Teams follows its own update process as outlined above.</span></span> <span data-ttu-id="85ff9-118">Teams不會遵循其他辦公室應用程式的更新程式，例如 Word 和 Excel。</span><span class="sxs-lookup"><span data-stu-id="85ff9-118">Teams doesn't follow the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="85ff9-119">若要深入瞭解[，請參閱更新](/DeployOffice/overview-of-update-channels-for-office-365-proplus)通道概觀Microsoft 365 Apps 企業版</span><span class="sxs-lookup"><span data-stu-id="85ff9-119">To learn more, read [Overview of update channels for Microsoft 365 Apps for enterprise](/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="85ff9-120">在 VDI 上Teams更新呢？</span><span class="sxs-lookup"><span data-stu-id="85ff9-120">What about updates to Teams on VDI?</span></span>


<span data-ttu-id="85ff9-121">Teams虛擬桌面基礎結構 (VDI) 上的用戶端不會以非 VDI 用戶端Teams的方式自動更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-121">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="85ff9-122">您必須安裝新的 MSI 以更新 VM 映射，如在[VDI](teams-for-vdi.md)上安裝Teams所述。</span><span class="sxs-lookup"><span data-stu-id="85ff9-122">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](teams-for-vdi.md).</span></span> <span data-ttu-id="85ff9-123">您必須卸載目前的版本，以更新至較新版本。</span><span class="sxs-lookup"><span data-stu-id="85ff9-123">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="85ff9-124">系統管理員可以部署更新，而不是Teams自動更新嗎？</span><span class="sxs-lookup"><span data-stu-id="85ff9-124">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="85ff9-125">Teams無法讓系統管理員透過任何傳遞機制部署更新。</span><span class="sxs-lookup"><span data-stu-id="85ff9-125">Teams doesn't give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="85ff9-126">維護協定</span><span class="sxs-lookup"><span data-stu-id="85ff9-126">Servicing agreement</span></span>

<span data-ttu-id="85ff9-127">做為新式線上服務，Teams用戶端每兩周自動更新一次。</span><span class="sxs-lookup"><span data-stu-id="85ff9-127">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="85ff9-128">由於Teams受新式生命週期政策所規範，因此使用者預期會維持在桌面用戶端的最新版本。</span><span class="sxs-lookup"><span data-stu-id="85ff9-128">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="85ff9-129">自動更新可確保使用者擁有最新的功能、增強功能、安全性和服務可靠性。</span><span class="sxs-lookup"><span data-stu-id="85ff9-129">Auto-updates ensure that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="85ff9-130">若要識別桌面用戶端何時過期，如果使用者的目前版本介於 1 到 3 個月之間，以及是否有可用的新版本，則會顯示應用程式內通知。</span><span class="sxs-lookup"><span data-stu-id="85ff9-130">To identify when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="85ff9-131">此 App 內訊息可鼓勵使用者更新至最新版本Teams或在必要時，與 IT 系統管理員聯繫以執行此操作。</span><span class="sxs-lookup"><span data-stu-id="85ff9-131">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="85ff9-132">超過Teams桌面用戶端的使用者會看到封鎖頁面，提供目前更新、連至 IT 系統管理員或繼續Teams網頁版的選項。</span><span class="sxs-lookup"><span data-stu-id="85ff9-132">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="85ff9-133">Teams雲端上的桌面用戶端目前在此服務協定有例外，直到進一步通知為止。</span><span class="sxs-lookup"><span data-stu-id="85ff9-133">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="85ff9-134">有關新版本發行的資訊，請查看 [訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或前往說明  >  **用戶端** 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="85ff9-134">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
