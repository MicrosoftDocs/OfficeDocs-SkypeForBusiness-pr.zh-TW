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
description: 瞭解如何安裝和連線到 Microsoft StaffHub PowerShell 模組。
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 122a704df184619591f121f088162a045733cf4b
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992128"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="35559-103">安裝 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35559-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35559-104">2019年12月31日生效，Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="35559-104">Effective December 31, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="35559-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="35559-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="35559-106">今天，小組包含針對排程管理的倒班應用程式，而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="35559-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="35559-107">StaffHub 將會停止針對2019年12月31日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="35559-107">StaffHub will stop working for all users on December 31, 2019.</span></span> <span data-ttu-id="35559-108">任何試圖開啟 StaffHub 的人，都會顯示一則訊息，讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="35559-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="35559-109">若要深入瞭解，請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="35559-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="35559-110">請使用本文中的步驟來安裝並聯機至 Microsoft StaffHub PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="35559-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="35559-111">您需要這樣做，才能[將您的 StaffHub 團隊移至團隊](move-staffhub-teams-to-shifts-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="35559-111">You'll need this to [move your StaffHub teams to Teams](move-staffhub-teams-to-shifts-in-teams.md).</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="35559-112">安裝 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35559-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="35559-113">下載[StaffHub PowerShell 模組](https://www.powershellgallery.com/packages/MicrosoftStaffHub)。</span><span class="sxs-lookup"><span data-stu-id="35559-113">Download the [StaffHub PowerShell module](https://www.powershellgallery.com/packages/MicrosoftStaffHub).</span></span>
2. <span data-ttu-id="35559-114">以系統管理員身分開啟 Windows PowerShell 3.0 或更新版本。若要這樣做，請按一下 [**開始**]，輸入**Windows powershell**，以滑鼠右鍵按一下 [ **windows powershell**]，然後選取 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="35559-114">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="35559-115">若要取得最新版本的 Windows PowerShell，請參閱[安裝 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="35559-115">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span>
3. <span data-ttu-id="35559-116">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="35559-116">Run the following:</span></span>

    ```PowerShell
    $ENV:PSModulePath
    ```
4. <span data-ttu-id="35559-117">檢查輸出中的資料夾路徑，並確認路徑中的所有資料夾都存在於您的電腦上，然後再移至下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="35559-117">Check the folder path in the output and make sure that all folders in the path exist on your computer before you go to the next step.</span></span> <span data-ttu-id="35559-118">如果資料夾遺失，請建立。</span><span class="sxs-lookup"><span data-stu-id="35559-118">If folders are missing, create them.</span></span>
5. <span data-ttu-id="35559-119">執行下列動作，以允許安裝 StaffHub PowerShell 模組：</span><span class="sxs-lookup"><span data-stu-id="35559-119">Run the following to allow for installation of the StaffHub PowerShell module:</span></span>

    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
6. <span data-ttu-id="35559-120">執行下列動作，其中&lt;path&gt;是步驟3輸出中的路徑。</span><span class="sxs-lookup"><span data-stu-id="35559-120">Run the following, where &lt;path&gt; is the path in the output from step 3.</span></span> <span data-ttu-id="35559-121">例如，路徑看起來可能像 C:\Users\User1\Documents\WindowsPowerShell\Modules。</span><span class="sxs-lookup"><span data-stu-id="35559-121">For example, the path might look like C:\Users\User1\Documents\WindowsPowerShell\Modules.</span></span>

    <span data-ttu-id="35559-122">請務必分別執行每個命令。</span><span class="sxs-lookup"><span data-stu-id="35559-122">Be sure to run each command separately.</span></span>

    ```PowerShell
    Install-Module -Name PackageManagement -Force  -AllowClobber
    Install-Module -Name PowerShellGet -Force  -AllowClobber
    ```
7. <span data-ttu-id="35559-123">退出 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="35559-123">Exit Windows PowerShell.</span></span>
8. <span data-ttu-id="35559-124">以全域系統管理員身分開啟 Windows PowerShell 3.0 或更新版本，然後執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="35559-124">Open Windows PowerShell 3.0 or later as a global admin, and then run the following:</span></span>

    ```PowerShell
    Install-Module -Name MicrosoftStaffHub
    ```

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="35559-125">連線到 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="35559-125">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="35559-126">執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="35559-126">Run the following:</span></span>

    ```PowerShell
    Connect-StaffHub
    ```

2. <span data-ttu-id="35559-127">出現提示時，請以全域管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="35559-127">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="35559-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="35559-128">Related topics</span></span>

- [<span data-ttu-id="35559-129">Microsoft StaffHub PowerShell 參考</span><span class="sxs-lookup"><span data-stu-id="35559-129">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="35559-130">將 StaffHub 小組移動至 Teams 中的 Shifts</span><span class="sxs-lookup"><span data-stu-id="35559-130">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
