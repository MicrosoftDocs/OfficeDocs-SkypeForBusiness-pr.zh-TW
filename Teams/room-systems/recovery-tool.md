---
title: 使用 Microsoft 團隊會議室恢復工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: davgroom
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
ms.collection: M365-voice
localization_priority: Normal
description: 本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具], 讓您用來將已過期的系統變成受支援的狀態。
ms.openlocfilehash: cbfb3ef1ec033389894b3b7479e454160dc77b1b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 05/20/2019
ms.locfileid: "36182463"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="afafb-103">使用 Microsoft 團隊會議室恢復工具</span><span class="sxs-lookup"><span data-stu-id="afafb-103">Use the Microsoft Teams Rooms recovery tool</span></span>
 
<span data-ttu-id="afafb-104">本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具], 讓您用來將已過期的系統變成受支援的狀態。</span><span class="sxs-lookup"><span data-stu-id="afafb-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="afafb-105">當 Microsoft [團隊聊天室] 主控台顯示「系統組態已過期」錯誤時, 您可以使用這個工具。</span><span class="sxs-lookup"><span data-stu-id="afafb-105">You would use this tool when the Microsoft Teams Rooms console shows a "system config out of date" error.</span></span>
  

<span data-ttu-id="afafb-106"><a name="Prerequisites"> </a></span><span class="sxs-lookup"><span data-stu-id="afafb-106"></span></span>  
## <a name="prerequisites"></a><span data-ttu-id="afafb-107">先決條件</span><span class="sxs-lookup"><span data-stu-id="afafb-107">Prerequisites</span></span>

<span data-ttu-id="afafb-108">下載最新的[Microsoft 團隊聊天室安裝套件](https://go.microsoft.com/fwlink/?linkid=851168), 並將其解壓縮至 Microsoft 團隊聊天室裝置可存取的 USB 記憶棒或網路共用。</span><span class="sxs-lookup"><span data-stu-id="afafb-108">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

<span data-ttu-id="afafb-109">您可能也需要安裝[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="afafb-109">You may also need to install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span>

<span data-ttu-id="afafb-110"><a name="Windows-ver"> </a></span><span class="sxs-lookup"><span data-stu-id="afafb-110"></span></span>
## <a name="verify-windows-version"></a><span data-ttu-id="afafb-111">驗證 Windows 版本</span><span class="sxs-lookup"><span data-stu-id="afafb-111">Verify Windows Version</span></span> 

1. <span data-ttu-id="afafb-112">若要登入管理員帳戶, 請移至 [**設定]> Windows 設定]> 管理員**從 Microsoft 團隊聊天室裝置登入。</span><span class="sxs-lookup"><span data-stu-id="afafb-112">Login to an admin account by going to **Settings> Windows Setting> Admin Sign In** from the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="afafb-113">此選項會將您帶到 [登入] 畫面。</span><span class="sxs-lookup"><span data-stu-id="afafb-113">This option brings you to the login screen.</span></span>
2. <span data-ttu-id="afafb-114">`admin`使用密碼`sfb`登入管理員帳戶 (預設系統管理員帳戶)。</span><span class="sxs-lookup"><span data-stu-id="afafb-114">Sign into an admin account, the default admin account being `admin` with the password `sfb`.</span></span>
3. <span data-ttu-id="afafb-115">按一下 [開始] 功能表, 然後`winver.exe`在搜尋方塊中輸入 [\**執行] 命令*, 並在結果上按一下。</span><span class="sxs-lookup"><span data-stu-id="afafb-115">Click on the start menu and type `winver.exe` into the search box and click \**Run Command* on the result.</span></span>
4. <span data-ttu-id="afafb-116">記下 [資訊] 窗格第二行的「版本」後面的數位。</span><span class="sxs-lookup"><span data-stu-id="afafb-116">Make note of the number after 'Version' on the second line of the info pane.</span></span>

>[!NOTE]
><span data-ttu-id="afafb-117">如果顯示的版本是1607或更舊版本, 請先依照在<a href="#Windows-up">恢復步驟之前更新 Windows</a>中的步驟操作, 然後再 Proceding 到<a href="#Perform">執行損毀修復</a>步驟。</span><span class="sxs-lookup"><span data-stu-id="afafb-117">If the Version shown is 1607 or earlier, follow the steps in the <a href="#Windows-up">Update Windows before recovery</a> steps before proceding to the <a href="#Perform">Perform a recovery</a> steps.</span></span> <span data-ttu-id="afafb-118">如果顯示的版本大於 1607, 請依照<a href="#Perform">執行恢復</a>中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="afafb-118">If the Version shown is greater than 1607, follow only the steps in <a href="#Perform">Perform a recovery</a>.</span></span>

<span data-ttu-id="afafb-119"><a name="Windows-up"> </a></span><span class="sxs-lookup"><span data-stu-id="afafb-119"></span></span>
## <a name="update-windows-before-recovery-if-needed"></a><span data-ttu-id="afafb-120">在恢復之前更新 Windows (如有需要)</span><span class="sxs-lookup"><span data-stu-id="afafb-120">Update Windows before recovery (if needed)</span></span>

1. <span data-ttu-id="afafb-121">在仍以系統管理員使用者身分登入的情況下, 啟動提升許可權的 Powershell 提示。</span><span class="sxs-lookup"><span data-stu-id="afafb-121">While still logged in as an admin user, launch an elevated Powershell prompt.</span></span>
2. <span data-ttu-id="afafb-122">執行命令`Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`。</span><span class="sxs-lookup"><span data-stu-id="afafb-122">Run the command `Remove-Item -Path 'c:\Recovery\OEM\$oem$\$1\Rigel' -Force -Recurse`.</span></span>
3. <span data-ttu-id="afafb-123">請執行 Windows Update 並安裝 Windows 1709 更新。</span><span class="sxs-lookup"><span data-stu-id="afafb-123">Run Windows Update and install the update for Windows 1709.</span></span>
4. <span data-ttu-id="afafb-124">在1709更新完成之後, 請重新登入管理員帳戶並安裝[KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu)。</span><span class="sxs-lookup"><span data-stu-id="afafb-124">After the update to 1709 is complete sign back into admin account and install [KB4089848](http://download.windowsupdate.com/d/msdownload/update/software/updt/2018/03/windows10.0-kb4089848-x64_db7c5aad31c520c6983a937c3d53170e84372b11.msu).</span></span> <span data-ttu-id="afafb-125">更新可能是從連結或使用 Windows Update 完成。</span><span class="sxs-lookup"><span data-stu-id="afafb-125">The update may be done from the link or using Windows Update.</span></span>
5. <span data-ttu-id="afafb-126">如果您選用的是選擇性步驟, 請安裝 [Windows Update] 中提供的任何其他更新。</span><span class="sxs-lookup"><span data-stu-id="afafb-126">As an optional step, install any additional updates available from Windows Update.</span></span>

<span data-ttu-id="afafb-127"><a name="Perform"> </a></span><span class="sxs-lookup"><span data-stu-id="afafb-127"></span></span>
## <a name="perform-a-recovery"></a><span data-ttu-id="afafb-128">執行恢復</span><span class="sxs-lookup"><span data-stu-id="afafb-128">Perform a recovery</span></span>

1. <span data-ttu-id="afafb-129">在 Microsoft 團隊聊天室裝置上登入系統管理員帳戶, 然後啟動提升的命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="afafb-129">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2. <span data-ttu-id="afafb-130">從 microsoft 團隊聊天室裝置驗證您可以存取`RecoveryTool.ps1`檔案的 Microsoft 團隊聊天室裝置, 該檔案會包含在從 Microsoft 小組聊天室安裝套件提取的檔案中。</span><span class="sxs-lookup"><span data-stu-id="afafb-130">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1` file, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="afafb-131">您可以在使用網路共用或 USB 磁片磁碟機上的 [準備必備元件] 中找到套件。</span><span class="sxs-lookup"><span data-stu-id="afafb-131">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3. <span data-ttu-id="afafb-132">執行 Powershell 命令`-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="afafb-132">Run the Powershell.exe command `-ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4. <span data-ttu-id="afafb-133">當腳本選取選項`1:"Repair System"`提示時。</span><span class="sxs-lookup"><span data-stu-id="afafb-133">When prompted by the script select option `1:"Repair System"`.</span></span>
5. <span data-ttu-id="afafb-134">完成後, 請重新開機 Microsoft 團隊聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="afafb-134">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="afafb-135">它會自動重新開機, 並在第二次完全復原。</span><span class="sxs-lookup"><span data-stu-id="afafb-135">It will reboot again automatically and come up fully recovered the second time.</span></span>



<span data-ttu-id="afafb-136"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="afafb-136"></span></span>  
## <a name="see-also"></a><span data-ttu-id="afafb-137">另請參閱</span><span class="sxs-lookup"><span data-stu-id="afafb-137">See also</span></span>
 
[<span data-ttu-id="afafb-138">Microsoft 團隊聊天室說明</span><span class="sxs-lookup"><span data-stu-id="afafb-138">Microsoft Teams Rooms help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="afafb-139">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="afafb-139">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
