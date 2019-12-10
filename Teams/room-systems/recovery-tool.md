---
title: 使用 Microsoft 團隊會議室恢復工具
ms.author: v-lanac
author: lanachin
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
localization_priority: Normal
description: 本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具]，讓您用來將已過期的系統變成受支援的狀態。
ms.openlocfilehash: 79cdd7b2e3530570033083bdac7089e862f169ce
ms.sourcegitcommit: dc70fd277d9542d831741e14dba9ae22367210ae
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/09/2019
ms.locfileid: "39909459"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="6054e-103">使用 Microsoft 團隊會議室恢復工具</span><span class="sxs-lookup"><span data-stu-id="6054e-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="6054e-104">本文討論如何使用 Microsoft 團隊聊天室的 [恢復工具]，讓您用來將已過期的系統變成受支援的狀態。</span><span class="sxs-lookup"><span data-stu-id="6054e-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="6054e-105">當 Microsoft 團隊聊天室主控台顯示「系統組態已過期」錯誤，或在執行推播按鈕重設[factory 還原](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore)之前，應該套用此工具。</span><span class="sxs-lookup"><span data-stu-id="6054e-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](https://docs.microsoft.com/microsoftteams/room-systems/room-systems-v2-operations#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6054e-106">先決條件</span><span class="sxs-lookup"><span data-stu-id="6054e-106">Prerequisites</span></span>

<span data-ttu-id="6054e-107">下載最新的[Microsoft 團隊聊天室安裝套件](https://go.microsoft.com/fwlink/?linkid=851168)，並將其解壓縮至 Microsoft 團隊聊天室裝置可存取的 USB 記憶棒或網路共用。</span><span class="sxs-lookup"><span data-stu-id="6054e-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="6054e-108">從 MSI 解壓縮檔案的方式有許多種。</span><span class="sxs-lookup"><span data-stu-id="6054e-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="6054e-109">提取所有檔案並保留其目錄結構的任何機制都是可接受的。</span><span class="sxs-lookup"><span data-stu-id="6054e-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="6054e-110">其中一個方法是使用命令`msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget`來`PathToMsi`代表 Microsoft 團隊聊天室安裝套件的完整路徑，並`PathToTarget`代表您想要解壓縮檔案的目的檔案夾的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="6054e-110">One such way is to use the command `msiexec /qn PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="6054e-111">執行工具</span><span class="sxs-lookup"><span data-stu-id="6054e-111">Running the tool</span></span>

1) <span data-ttu-id="6054e-112">在 Microsoft 團隊聊天室裝置上登入系統管理員帳戶，然後啟動提升的命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="6054e-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="6054e-113">從 microsoft 團隊聊天室裝置驗證您可以存取的`RecoveryTool.ps1 file`Microsoft 小組聊天室裝置，該裝置會包含在從 Microsoft 小組聊天室安裝套件提取的檔案中。</span><span class="sxs-lookup"><span data-stu-id="6054e-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="6054e-114">您可以在使用網路共用或 USB 磁片磁碟機上的 [準備必備元件] 中找到套件。</span><span class="sxs-lookup"><span data-stu-id="6054e-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="6054e-115">執行`powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`。</span><span class="sxs-lookup"><span data-stu-id="6054e-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="6054e-116">如果您執行的是 factory 還原：</span><span class="sxs-lookup"><span data-stu-id="6054e-116">If you are performing a factory restore:</span></span>
   - <span data-ttu-id="6054e-117">當腳本出現提示時，選取選項2：**重設**。</span><span class="sxs-lookup"><span data-stu-id="6054e-117">When prompted by the script select option 2: **Reset**.</span></span>
   - <span data-ttu-id="6054e-118">如果 BitLocker 已開啟，請依照腳本輸出末端提供的指示來停用。</span><span class="sxs-lookup"><span data-stu-id="6054e-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   - <span data-ttu-id="6054e-119">執行 factory 還原。</span><span class="sxs-lookup"><span data-stu-id="6054e-119">Perform the factory restore.</span></span>
      - <span data-ttu-id="6054e-120">開啟 [**設定**] 應用程式，然後選取 [**更新 & 安全性**]</span><span class="sxs-lookup"><span data-stu-id="6054e-120">Open the **Settings** app, and select **Update & Security**</span></span>
      - <span data-ttu-id="6054e-121">流覽至 [**恢復**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6054e-121">Navigate to the **Recovery** tab.</span></span>
      - <span data-ttu-id="6054e-122">在 [**重設此電腦**] 底下，選取 [**開始**使用]</span><span class="sxs-lookup"><span data-stu-id="6054e-122">Beneath **Reset this PC**, select **Get started**</span></span>
      - <span data-ttu-id="6054e-123">選取 [**移除所有專案**]，**然後選取**[移除 **]** 。</span><span class="sxs-lookup"><span data-stu-id="6054e-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
      - <span data-ttu-id="6054e-124">系統會多次重新開機。</span><span class="sxs-lookup"><span data-stu-id="6054e-124">The system will reboot multiple times.</span></span> <span data-ttu-id="6054e-125">重設完成後，系統將會出現在 Windows OOBE 畫面上。</span><span class="sxs-lookup"><span data-stu-id="6054e-125">When the reset is complete, the system will be at the Windows OOBE screen.</span></span>
5) <span data-ttu-id="6054e-126">如果您要修復「已結束」系統：</span><span class="sxs-lookup"><span data-stu-id="6054e-126">If you are repairing an "out of date" system:</span></span>
    - <span data-ttu-id="6054e-127">當腳本出現提示時，選取選項1：**修復**。</span><span class="sxs-lookup"><span data-stu-id="6054e-127">When prompted by the script select option 1: **Repair**.</span></span>
    - <span data-ttu-id="6054e-128">完成後，請重新開機 Microsoft 團隊聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="6054e-128">Upon completion, reboot the Microsoft Teams Rooms device.</span></span> <span data-ttu-id="6054e-129">它會自動重新開機，並在第二次完全復原。</span><span class="sxs-lookup"><span data-stu-id="6054e-129">It will reboot again automatically and come up fully recovered the second time.</span></span>

> [!NOTE]
> <span data-ttu-id="6054e-130">如果 [保留我的檔案] **：移除 app 和設定，但**在 Windows 重設程式期間已選取 [保留您的個人檔案] 選項，則 Microsoft 團隊聊天室可能無法使用的已知問題。</span><span class="sxs-lookup"><span data-stu-id="6054e-130">There is a known issue where the Microsoft Teams Rooms can become unusable if the  **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="6054e-131">請勿*使用此*選項。</span><span class="sxs-lookup"><span data-stu-id="6054e-131">Do *not* use this option.</span></span>

## <a name="see-also"></a><span data-ttu-id="6054e-132">另請參閱</span><span class="sxs-lookup"><span data-stu-id="6054e-132">See also</span></span>

[<span data-ttu-id="6054e-133">Microsoft 團隊聊天室說明</span><span class="sxs-lookup"><span data-stu-id="6054e-133">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="6054e-134">管理 Microsoft 團隊聊天室</span><span class="sxs-lookup"><span data-stu-id="6054e-134">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
