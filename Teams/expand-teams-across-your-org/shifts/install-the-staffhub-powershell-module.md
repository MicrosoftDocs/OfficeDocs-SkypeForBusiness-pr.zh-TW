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
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ce0d1acec923d09591e8f81b3f500ee9a910f5c
ms.sourcegitcommit: b914c044c43ff8147f35eea684fec1de01a7bcd2
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/19/2019
ms.locfileid: "36464662"
---
# <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="743e9-103">安裝 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="743e9-103">Install the Microsoft StaffHub PowerShell module</span></span>

> [!IMPORTANT]
> <span data-ttu-id="743e9-104">2019年10月1日生效, Microsoft StaffHub 將停用。</span><span class="sxs-lookup"><span data-stu-id="743e9-104">Effective October 1, 2019, Microsoft StaffHub will be retired.</span></span> <span data-ttu-id="743e9-105">我們正在將 StaffHub 功能組建至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="743e9-105">We’re building StaffHub capabilities into Microsoft Teams.</span></span> <span data-ttu-id="743e9-106">今天, 小組包含針對排程管理的倒班應用程式, 而其他功能則會隨著時間推移而推出。</span><span class="sxs-lookup"><span data-stu-id="743e9-106">Today, Teams includes the Shifts app for schedule management and additional capabilities will roll out over time.</span></span> <span data-ttu-id="743e9-107">StaffHub 將會停止針對2019年10月1日的所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="743e9-107">StaffHub will stop working for all users on October 1, 2019.</span></span> <span data-ttu-id="743e9-108">任何試圖開啟 StaffHub 的人, 都會顯示一則訊息, 讓他們下載小組。</span><span class="sxs-lookup"><span data-stu-id="743e9-108">Anyone who tries to open StaffHub will be shown a message directing them to download Teams.</span></span> <span data-ttu-id="743e9-109">若要深入瞭解, 請參閱[Microsoft StaffHub 停用](microsoft-staffhub-to-be-retired.md)。</span><span class="sxs-lookup"><span data-stu-id="743e9-109">To learn more, see [Microsoft StaffHub to be retired](microsoft-staffhub-to-be-retired.md).</span></span>  

<span data-ttu-id="743e9-110">請使用本文中的步驟來安裝並聯機至 Microsoft StaffHub PowerShell 模組。</span><span class="sxs-lookup"><span data-stu-id="743e9-110">Use the steps in this article to install and connect to the Microsoft StaffHub PowerShell module.</span></span> <span data-ttu-id="743e9-111">您需要使用 PowerShell 來管理 StaffHub, 並將 StaffHub 團隊移至 Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="743e9-111">You'll need this to manage StaffHub by using PowerShell and to move your StaffHub teams to Microsoft Teams.</span></span>

## <a name="install-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="743e9-112">安裝 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="743e9-112">Install the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="743e9-113">以系統管理員身分開啟 Windows PowerShell 3.0 或更新版本。若要這樣做, 請按一下 [**開始**], 輸入**Windows powershell**, 以滑鼠右鍵按一下 [ **windows powershell**], 然後選取 [**以系統管理員身分執行**]。</span><span class="sxs-lookup"><span data-stu-id="743e9-113">Open Windows PowerShell 3.0 or later as an admin. To do this, click **Start**, type **Windows PowerShell**, right-click **Windows PowerShell**, and then select **Run as administrator**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="743e9-114">若要取得最新版本的 Windows PowerShell, 請參閱[安裝 Windows powershell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell)。</span><span class="sxs-lookup"><span data-stu-id="743e9-114">To get the latest version of Windows PowerShell, see [Installing Windows PowerShell](https://docs.microsoft.com/powershell/scripting/install/installing-windows-powershell).</span></span> 
2. <span data-ttu-id="743e9-115">執行下列動作以安裝目前穩定版本的 StaffHub PowerShell 模組:</span><span class="sxs-lookup"><span data-stu-id="743e9-115">Run the following to install the current stable version of the StaffHub PowerShell module:</span></span>

    ```
    Install-Module -Name MicrosoftStaffHub
    ```
    
    <span data-ttu-id="743e9-116">只有在您需要安裝最新版本時, 才能執行這個命令, 這可能會有比目前穩定版本更多的 instabilities:`Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span><span class="sxs-lookup"><span data-stu-id="743e9-116">You can run this command only if you need to install the latest version, which may have more instabilities than the current stable version: `Install-Module -Name MicrosoftStaffHub -AllowPrerelease`</span></span>

     > [!NOTE]
     > <span data-ttu-id="743e9-117">如果您在使用更多 instabilities 安裝最新版本期間收到錯誤, 您可以執行下列動作:`Install-Module PowershellGet -Force`</span><span class="sxs-lookup"><span data-stu-id="743e9-117">If you receive an error during the installation of the latest version with more instabilities, you can run: `Install-Module PowershellGet -Force`</span></span>

3. <span data-ttu-id="743e9-118">您可能會看到警告訊息:</span><span class="sxs-lookup"><span data-stu-id="743e9-118">You may see the warning message:</span></span>

    ```
    Untrusted repository - You are installing the modules from an untrusted repository. If you trust this repository, change its InstallationPolicy value by running the Set-PSRepository cmdlet. Are you sure you want to install the modules from 'PSGallery'?
    ```

<span data-ttu-id="743e9-119">鍵入`Y`並按一下`Enter`。</span><span class="sxs-lookup"><span data-stu-id="743e9-119">Type `Y` and click `Enter`.</span></span>
 
4. <span data-ttu-id="743e9-120">退出 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="743e9-120">Exit Windows PowerShell.</span></span>

## <a name="connect-to-the-microsoft-staffhub-powershell-module"></a><span data-ttu-id="743e9-121">連線到 Microsoft StaffHub PowerShell 模組</span><span class="sxs-lookup"><span data-stu-id="743e9-121">Connect to the Microsoft StaffHub PowerShell module</span></span>

1. <span data-ttu-id="743e9-122">執行下列動作:</span><span class="sxs-lookup"><span data-stu-id="743e9-122">Run the following:</span></span>

    ```
    Connect-StaffHub
    ```

2. <span data-ttu-id="743e9-123">出現提示時, 請以全域管理員身分登入。</span><span class="sxs-lookup"><span data-stu-id="743e9-123">When you're prompted, log in as a global admin.</span></span>

## <a name="related-topics"></a><span data-ttu-id="743e9-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="743e9-124">Related topics</span></span>

- [<span data-ttu-id="743e9-125">Microsoft StaffHub PowerShell 參考</span><span class="sxs-lookup"><span data-stu-id="743e9-125">Microsoft StaffHub PowerShell reference</span></span>](https://docs.microsoft.com/en-us/powershell/module/staffhub/?view=staffhub-ps)
- [<span data-ttu-id="743e9-126">將 Microsoft StaffHub 小組移至團隊中</span><span class="sxs-lookup"><span data-stu-id="743e9-126">Move your Microsoft StaffHub teams to Shifts in Teams</span></span>](move-staffhub-teams-to-shifts-in-teams.md)
