---
title: 團隊更新
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 05/13/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: annaray
search.appverid: MET150
description: 瞭解小組桌面用戶端的更新方式。
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba5280e03e316dfcde3bda9b62520fa513f3157a
ms.sourcegitcommit: 5faa89ea686448d5b339178f1330edc63e21a52f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/09/2019
ms.locfileid: "36184761"
---
# <a name="teams-update-process"></a><span data-ttu-id="304a7-103">小組更新流程</span><span class="sxs-lookup"><span data-stu-id="304a7-103">Teams update process</span></span>

<span data-ttu-id="304a7-104">團隊 web app 會每週更新一次。</span><span class="sxs-lookup"><span data-stu-id="304a7-104">The Teams web app is updated weekly.</span></span>

<span data-ttu-id="304a7-105">小組的桌面用戶端更新會在經過我們的技術採納計畫 (攻絲) 嚴格內部測試和驗證之後, 每兩周發行一次。</span><span class="sxs-lookup"><span data-stu-id="304a7-105">Teams desktop client updates are released every two weeks after rigorous internal testing and validation through our Technology Adoption Program (TAP).</span></span> <span data-ttu-id="304a7-106">這通常會在星期二進行。</span><span class="sxs-lookup"><span data-stu-id="304a7-106">This usually takes place on a Tuesday.</span></span> <span data-ttu-id="304a7-107">如果需要重要更新, 小組會略過此排程, 並在更新推出後立即發行更新。</span><span class="sxs-lookup"><span data-stu-id="304a7-107">If a critical update is required, Teams will bypass this schedule and release the update as soon as it’s available.</span></span>

<span data-ttu-id="304a7-108">桌面用戶端會自動更新。</span><span class="sxs-lookup"><span data-stu-id="304a7-108">The desktop client updates itself automatically.</span></span> <span data-ttu-id="304a7-109">團隊會在幕後每隔幾小時檢查更新、下載更新, 然後等到電腦處於空閒狀態, 然後才能自行安裝更新。</span><span class="sxs-lookup"><span data-stu-id="304a7-109">Teams checks for updates every few hours behind the scenes, downloads it, and then waits for the computer to be idle before silently installing the update.</span></span>

<span data-ttu-id="304a7-110">使用者也可以按一下應用程式右上方的 [檢查**設定檔**] 下拉式功能表上的 [**檢查更新**], 手動下載更新。</span><span class="sxs-lookup"><span data-stu-id="304a7-110">Users can also manually download updates by clicking **Check for updates** on the **Profile** drop-down menu on the top right of the app.</span></span> <span data-ttu-id="304a7-111">如果有可用的更新, 系統會在電腦空閒時下載並自動安裝。</span><span class="sxs-lookup"><span data-stu-id="304a7-111">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

<span data-ttu-id="304a7-112">使用者必須登入, 才能下載更新。</span><span class="sxs-lookup"><span data-stu-id="304a7-112">Users need to be signed in for updates to be downloaded.</span></span> 

<span data-ttu-id="304a7-113">從2019年7月9日開始, 團隊用戶端更新在更新期間使用明顯較低的網路頻寬。</span><span class="sxs-lookup"><span data-stu-id="304a7-113">Starting July 9, 2019, Teams client updates use significantly lower network bandwidth during the update.</span></span> <span data-ttu-id="304a7-114">此功能預設為開啟, 且不需要系統管理員或使用者執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="304a7-114">This is turned on by default and requires no action from admins or users.</span></span>


## <a name="what-about-updates-to-office-365-proplus"></a><span data-ttu-id="304a7-115">Office 365 專業增強版的更新內容是什麼？</span><span class="sxs-lookup"><span data-stu-id="304a7-115">What about updates to Office 365 ProPlus?</span></span>

<span data-ttu-id="304a7-116">依[使用 office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/DeployOffice/teams-install)中所述, 預設會在新安裝的 Office 365 專業增強版中安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="304a7-116">Teams is installed by default with new installations of Office 365 ProPlus as described in [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/teams-install).</span></span> 

<span data-ttu-id="304a7-117">團隊會依照上面所述的更新程式, 而不是其他辦公室應用程式 (例如 Word 和 Excel) 的更新程式。</span><span class="sxs-lookup"><span data-stu-id="304a7-117">Teams follows its own update process as outlined above, and not the update process for the other Offices apps, such as Word and Excel.</span></span> <span data-ttu-id="304a7-118">若要深入瞭解, 請參閱[Office 365 專業增強版更新通道的概覽](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span><span class="sxs-lookup"><span data-stu-id="304a7-118">To learn more, read [Overview of update channels for Office 365 ProPlus](https://docs.microsoft.com/DeployOffice/overview-of-update-channels-for-office-365-proplus)</span></span>

## <a name="what-about-updates-to-teams-on-vdi"></a><span data-ttu-id="304a7-119">VDI 上的小組更新為何？</span><span class="sxs-lookup"><span data-stu-id="304a7-119">What about updates to Teams on VDI?</span></span>

<span data-ttu-id="304a7-120">虛擬桌面基礎結構 (VDI) 上的團隊用戶端不會自動更新非 VDI 團隊用戶端的方式。</span><span class="sxs-lookup"><span data-stu-id="304a7-120">Teams clients on Virtual Desktop Infrastructure (VDI) aren't automatically updated the way that non-VDI Teams clients are.</span></span> <span data-ttu-id="304a7-121">您必須安裝新的 MSI 來更新 VM 影像, 如在[VDI 上安裝小組](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi)中所述。</span><span class="sxs-lookup"><span data-stu-id="304a7-121">You have to update the VM image by installing a new MSI as described in the instructions to [Install Teams on VDI](https://docs.microsoft.com/microsoftteams/teams-for-vdi#install-teams-on-vdi).</span></span> <span data-ttu-id="304a7-122">您必須卸載目前的版本, 才能更新為較新的版本。</span><span class="sxs-lookup"><span data-stu-id="304a7-122">You must uninstall the current version to update to a newer version.</span></span>

## <a name="can-admins-deploy-updates-instead-of-teams-auto-updating"></a><span data-ttu-id="304a7-123">管理員是否可以部署更新, 而不是團隊自動更新？</span><span class="sxs-lookup"><span data-stu-id="304a7-123">Can admins deploy updates instead of Teams auto-updating?</span></span>

<span data-ttu-id="304a7-124">團隊不會給予管理員透過任何傳遞機制部署更新的功能。</span><span class="sxs-lookup"><span data-stu-id="304a7-124">Teams does not give admins the ability to deploy updates through any delivery mechanism.</span></span>
