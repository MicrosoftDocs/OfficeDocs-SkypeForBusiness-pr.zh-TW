---
title: 團隊更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 瞭解小組桌面用戶端的更新方式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ace50cc0f9c59375c5a182cf18559b0a449db109
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570253"
---
# <a name="teams-update-process"></a><span data-ttu-id="04447-103">小組更新流程</span><span class="sxs-lookup"><span data-stu-id="04447-103">Teams update process</span></span>

<span data-ttu-id="04447-104">團隊 web app 會每週更新一次。</span><span class="sxs-lookup"><span data-stu-id="04447-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="04447-105">小組的桌面用戶端更新會在經過我們的技術採納計畫（攻絲）嚴格內部測試和驗證之後，每兩周發行一次。</span><span class="sxs-lookup"><span data-stu-id="04447-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="04447-106">這通常會在星期二進行。</span><span class="sxs-lookup"><span data-stu-id="04447-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="04447-107">如果需要重要更新，小組會略過此排程，並在更新推出後立即發行更新。</span><span class="sxs-lookup"><span data-stu-id="04447-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="04447-108">桌面用戶端會自動更新。</span><span class="sxs-lookup"><span data-stu-id="04447-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="04447-109">團隊會在幕後每隔幾小時檢查更新、下載更新，然後等到電腦處於空閒狀態，然後才能自行安裝更新。</span><span class="sxs-lookup"><span data-stu-id="04447-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="04447-110">使用者也可以按一下應用程式右上方的 [檢查**設定檔**] 下拉式功能表上的 [**檢查更新**]，手動下載更新。</span><span class="sxs-lookup"><span data-stu-id="04447-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="04447-111">如果有可用的更新，系統會在電腦空閒時下載並自動安裝。</span><span class="sxs-lookup"><span data-stu-id="04447-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="04447-112">使用者必須登入，才能下載更新。</span><span class="sxs-lookup"><span data-stu-id="04447-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="04447-113">從2019年7月31日起，團隊用戶端更新在更新期間使用明顯較低的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="04447-113">Starting July 31, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="04447-114">此功能預設為開啟，且不需要系統管理員或使用者執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="04447-114">This is turned on by default and requires no action from admins or users.</span></span>

## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="04447-115">Office 365 專業增強版的更新內容是什麼？</span><span class="sxs-lookup"><span data-stu-id="04447-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="04447-116">依[使用 office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/DeployOffice/teams-install)中所述，預設會在新安裝的 Office 365 專業增強版中安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="04447-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="04447-117">團隊會依照上面所述的更新程式，而不是其他辦公室應用程式（例如 Word 和 Excel）的更新程式。</span><span class="sxs-lookup"><span data-stu-id="04447-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="04447-118">若要深入瞭解，請參閱[Office 365 專業增強版更新通道的概覽](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="04447-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="04447-119">VDI 上的小組更新為何？</span><span class="sxs-lookup"><span data-stu-id="04447-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="04447-120">虛擬桌面基礎結構（VDI）上的團隊用戶端不會自動更新非 VDI 團隊用戶端的方式。</span><span class="sxs-lookup"><span data-stu-id="04447-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="04447-121">您必須安裝新的 MSI 來更新 VM 影像，如在[VDI 上安裝小組](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)中所述。</span><span class="sxs-lookup"><span data-stu-id="04447-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="04447-122">您必須卸載目前的版本，才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="04447-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="04447-123">管理員是否可以部署更新，而不是團隊自動更新？</span><span class="sxs-lookup"><span data-stu-id="04447-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="04447-124">團隊不會給予管理員透過任何傳遞機制部署更新的功能。</span><span class="sxs-lookup"><span data-stu-id="04447-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>

## <a name="servicing-agreement"></a><span data-ttu-id="04447-125">服務合約</span><span class="sxs-lookup"><span data-stu-id="04447-125">Servicing agreement</span></span>

<span data-ttu-id="04447-126">作為現代的線上服務，小組用戶端會每兩周自動更新一次。</span><span class="sxs-lookup"><span data-stu-id="04447-126">As a modern online service, the Teams client auto-updates every two weeks.</span></span> <span data-ttu-id="04447-127">由於團隊是由現代的生命週期原則所管理，因此，使用者可能會保持最新版本的桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="04447-127">Because Teams is governed by the Modern Lifecycle Policy, it's expected that users remain on the most up-to-date version of the desktop client.</span></span> <span data-ttu-id="04447-128">這可確保使用者擁有最新的功能、效能增強、安全性和服務可靠性。</span><span class="sxs-lookup"><span data-stu-id="04447-128">This ensures that users have the latest capabilities, performance enhancements, security, and service reliability.</span></span>

<span data-ttu-id="04447-129">若要在桌面用戶端過期時開始協助識別，如果使用者的目前版本在一到三個月之間，且有可用的新版本，就會顯示應用程式內警示。</span><span class="sxs-lookup"><span data-stu-id="04447-129">To begin assisting in identifying when desktop clients fall out of date, an in-app alert will be displayed if the user’s current version is between one and three months old, and if there's a new version available.</span></span> <span data-ttu-id="04447-130">此應用程式內訊息鼓勵使用者更新到最新版本的小組，或視需要向 IT 系統管理員進行更新。</span><span class="sxs-lookup"><span data-stu-id="04447-130">This in-app messaging encourages users to update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="04447-131">在超過三個月之前的小組桌面用戶端上，系統會顯示封鎖頁面，提供立即更新、與 IT 管理員聯繫，或繼續在網路上的小組中的選項。</span><span class="sxs-lookup"><span data-stu-id="04447-131">Users on Teams desktop clients that are more than three months old will see a blocking page that gives the options to update now, reach out to their IT admin, or continue to Teams on the web.</span></span>

<span data-ttu-id="04447-132">在第一次安裝和/或第一次執行團隊後的桌面用戶端版本超過三個月，在遇到上述服務資訊之前，會有28天的寬限期。</span><span class="sxs-lookup"><span data-stu-id="04447-132">Desktop client versions that are more than three months old upon first install and/or first run of Teams have a 28-day grace period before encountering the above-mentioned servicing information.</span></span> <span data-ttu-id="04447-133">在此期間，自動更新程式將會更新團隊用戶端。</span><span class="sxs-lookup"><span data-stu-id="04447-133">During this period, the auto-update process will update the Teams client.</span></span> <span data-ttu-id="04447-134">如果未更新，使用者就會看到應用程式內的警示，鼓勵他們手動更新為最新版本的團隊，或視需要向 IT 系統管理員確認。</span><span class="sxs-lookup"><span data-stu-id="04447-134">If not updated, users will see an in-app alert encouraging them to manually update to the latest version of Teams or, if necessary, to reach out to their IT admin to do so.</span></span> <span data-ttu-id="04447-135">這包括使用小組桌面用戶端的使用者做為 Office 365 專業增強版套件的一部分。</span><span class="sxs-lookup"><span data-stu-id="04447-135">This includes users using the Teams desktop client as part of the Office 365 ProPlus bundle.</span></span>

<span data-ttu-id="04447-136">政府群的小組桌面用戶端目前有此服務協定的例外狀況，直到進一步通知。</span><span class="sxs-lookup"><span data-stu-id="04447-136">Teams desktop clients on Government Clouds currently have an exception to this servicing agreement until further notice.</span></span>

<span data-ttu-id="04447-137">如需新版版本的詳細資訊，請參閱[訊息中心](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter)或移至**協助** > 用戶端**的新增功能**。</span><span class="sxs-lookup"><span data-stu-id="04447-137">For information on new version releases, check [Message Center](https://admin.microsoft.com/AdminPortal/Home#/MessageCenter) or go to **Help** > **What’s new** in the client.</span></span>
