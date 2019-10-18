---
title: 安裝 StaffHub PowerShell 模組
author: LanaChin
ms.author: v-lanac
ms.reviewer: lisawu
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 瞭解如何安裝和連線到 Microsoft StaffHub PowerShell 模組的預發行版本本。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: aa7f84342b2d4ae16cf801be513e1ae9d6440802
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569207"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="d5500-103">安裝 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="d5500-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d5500-104">2019年12月31日生效，Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="d5500-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="d5500-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="d5500-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="d5500-106">今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="d5500-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="d5500-107">StaffHub 將會停止針對2019年12月31日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="d5500-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="d5500-108">任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="d5500-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="d5500-109">若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="d5500-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="d5500-110">使用本文中的步驟來安裝並聯機到 Microsoft StaffHub PowerShell 模組的預發行版本本。</span><span class="sxs-lookup"><span data-stu-id="d5500-110">Use the steps in this article to install and connect to the prerelease version of the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="d5500-111">您需要這樣做，才能[將您的 StaffHub 團隊移至團隊](move-staffhub-teams-to-shifts-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="d5500-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-prerelease-version-of-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="d5500-112">安裝 Microsoft StaffHub PowerShell 模組的預發行版本本</span><span class="sxs-lookup"><span data-stu-id="d5500-112">Install the prerelease version of the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="d5500-113">以系統管理員身分開啟 Windows PowerShell 3.0 或更新版本。若要這樣做，請按一下 [**開始**]，輸入**Windows powershell**，以滑鼠右鍵按一下 [ **windows powershell**]，然後選取 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="d5500-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="d5500-114">若要取得最新版本的 Windows PowerShell，請參閱[安裝 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d5500-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="d5500-115">執行下列動作來安裝 StaffHub PowerShell 模組的預發行版本本：</span><span class="sxs-lookup"><span data-stu-id="d5500-115">Run the following to install the prerelease version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub -AllowPrerelease
    ```
3. <span data-ttu-id="d5500-116">您可能會看到警告訊息：</span><span class="sxs-lookup"><span data-stu-id="d5500-116">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

    <span data-ttu-id="d5500-117">輸入`Y`，然後按一下`Enter`。</span><span class="sxs-lookup"><span data-stu-id="d5500-117">Type `Y`, and then click `Enter`.</span></span>
 
4. <span data-ttu-id="d5500-118">退出 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d5500-118">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="d5500-119">連線到 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="d5500-119">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="d5500-120">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="d5500-120">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="d5500-121">出現提示時，請以全域管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="d5500-121">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d5500-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="d5500-122">Related topics</span></span>

- [<span data-ttu-id="d5500-123">Microsoft StaffHub PowerShell 參考</span><span class="sxs-lookup"><span data-stu-id="d5500-123">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="d5500-124">將 Microsoft StaffHub 小組移至團隊中</span><span class="sxs-lookup"><span data-stu-id="d5500-124">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
