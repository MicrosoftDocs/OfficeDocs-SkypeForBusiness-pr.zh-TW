---
title: 使用 Microsoft Teams 會議室修復工具
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: sohailta
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
localization_priority: Normal
description: 本文將討論如何使用復原工具Microsoft Teams 會議室，您將使用此工具將過期的系統帶至支援的狀態。
ms.openlocfilehash: 9a856312229ae326b4adbfd039ee0553213ca09c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117491"
---
# <a name="use-the-microsoft-teams-rooms-recovery-tool"></a><span data-ttu-id="89073-103">使用 Microsoft Teams 會議室修復工具</span><span class="sxs-lookup"><span data-stu-id="89073-103">Use the Microsoft Teams Rooms recovery tool</span></span>

<span data-ttu-id="89073-104">本文將討論如何使用復原工具Microsoft Teams 會議室，您將使用此工具將過期的系統帶至支援的狀態。</span><span class="sxs-lookup"><span data-stu-id="89073-104">This article discusses how to use the recovery tool for Microsoft Teams Rooms, which you would use to bring an out of date system into a supported state.</span></span> <span data-ttu-id="89073-105">當主機主機顯示「系統Microsoft Teams 會議室已過期」錯誤，或在執行按鈕重設出廠還原之前，應該會使用[此工具](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore)。</span><span class="sxs-lookup"><span data-stu-id="89073-105">This tool should be applied when either the Microsoft Teams Rooms console shows a "system config out of date" error, or prior to performing a push button reset [factory restore](./rooms-operations.md#microsoft-teams-rooms-reset-factory-restore).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="89073-106">必要條件</span><span class="sxs-lookup"><span data-stu-id="89073-106">Prerequisites</span></span>

<span data-ttu-id="89073-107">下載最新的[Microsoft Teams 會議室套件](https://go.microsoft.com/fwlink/?linkid=851168)，然後解壓縮到 USB 記憶棒或可供裝置Microsoft Teams 會議室共用。</span><span class="sxs-lookup"><span data-stu-id="89073-107">Download the latest [Microsoft Teams Rooms installation package](https://go.microsoft.com/fwlink/?linkid=851168) and extract it to a USB memory stick or network share accessible to the Microsoft Teams Rooms device.</span></span>

> [!NOTE]
> <span data-ttu-id="89073-108">從 MSI 解壓縮檔案有許多方法可以完成。</span><span class="sxs-lookup"><span data-stu-id="89073-108">Extracting the files from the MSI can be accomplished by many means.</span></span> <span data-ttu-id="89073-109">任何能解壓縮所有檔案並保留其目錄結構的機制都是可接受的。</span><span class="sxs-lookup"><span data-stu-id="89073-109">Any mechanism that extracts all the files and preserves their directory structure is acceptable.</span></span> <span data-ttu-id="89073-110">其中一個方法就是使用命令，其中代表 Microsoft Teams 會議室安裝套件的完整路徑，並代表要解壓縮檔案之資料夾的完整 `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` `PathToMsi` `PathToTarget` 路徑。</span><span class="sxs-lookup"><span data-stu-id="89073-110">One such way is to use the command `msiexec /a PathToMsi /qb TARGETDIR=PathToTarget` where `PathToMsi` represents the full path to the Microsoft Teams Room installation package, and `PathToTarget` represents the full path to the folder you would like the files extracted to.</span></span>

## <a name="running-the-tool"></a><span data-ttu-id="89073-111">執行工具</span><span class="sxs-lookup"><span data-stu-id="89073-111">Running the tool</span></span>

1) <span data-ttu-id="89073-112">在裝置上Microsoft Teams 會議室系統管理員帳戶，然後啟動提升的命令提示。</span><span class="sxs-lookup"><span data-stu-id="89073-112">Sign in to the admin account on your Microsoft Teams Rooms device, and launch an elevated command prompt.</span></span>
2) <span data-ttu-id="89073-113">請從Microsoft Teams 會議室裝置確認您能夠存取 ，該裝置包含在從安裝套件Microsoft Teams 會議室 `RecoveryTool.ps1 file` 檔案中。</span><span class="sxs-lookup"><span data-stu-id="89073-113">Verify from the Microsoft Teams Rooms device that you are able to access the `RecoveryTool.ps1 file`, which is included in the files extracted from the Microsoft Teams Rooms installation package.</span></span> <span data-ttu-id="89073-114">您可以在準備先決條件時所使用的網路共用或 USB 磁碟機上找到套件。</span><span class="sxs-lookup"><span data-stu-id="89073-114">The kit can be found on the network share or USB drive used when preparing prerequisites.</span></span>
3) <span data-ttu-id="89073-115">執行 `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"` 。</span><span class="sxs-lookup"><span data-stu-id="89073-115">Run `powershell.exe -ExecutionPolicy Unrestricted -File "<path to RecoveryTool.ps1>"`.</span></span>
4) <span data-ttu-id="89073-116">若要執行出廠還原：</span><span class="sxs-lookup"><span data-stu-id="89073-116">To perform a factory restore:</span></span>
   1. <span data-ttu-id="89073-117">當腳本提示時，請選取選項 2： **重設**。</span><span class="sxs-lookup"><span data-stu-id="89073-117">When prompted by the script select option 2: **Reset**.</span></span>
   2. <span data-ttu-id="89073-118">如果BitLocker，請按照腳本輸出結尾所提供的指示來停用。</span><span class="sxs-lookup"><span data-stu-id="89073-118">If BitLocker is on, follow the instructions provided at the end of the script output to disable it.</span></span>
   3. <span data-ttu-id="89073-119">執行出廠還原。</span><span class="sxs-lookup"><span data-stu-id="89073-119">Perform the factory restore.</span></span>
      1. <span data-ttu-id="89073-120">開啟 **設定應用程式**，然後選取 **&安全性**</span><span class="sxs-lookup"><span data-stu-id="89073-120">Open the **Settings** app, and select **Update & Security**</span></span>
      2. <span data-ttu-id="89073-121">流覽至修復 **定位** 點。</span><span class="sxs-lookup"><span data-stu-id="89073-121">Navigate to the **Recovery** tab.</span></span>
      3. <span data-ttu-id="89073-122">在 **重設此電腦** 底下，選取 **開始**</span><span class="sxs-lookup"><span data-stu-id="89073-122">Beneath **Reset this PC**, select **Get started**</span></span>
      4. <span data-ttu-id="89073-123">選取 **移除所有專案**，然後選取下 **一步** 和 **重設**</span><span class="sxs-lookup"><span data-stu-id="89073-123">Select **Remove everything**, then **Next** and **Reset**</span></span>
        > [!WARNING]
        > <span data-ttu-id="89073-124">如果在Microsoft Teams 會議室重設程式期間選取了保留我的檔案 **-** 移除應用程式和設定，但保留您的個人檔案選項，Windows無法使用。</span><span class="sxs-lookup"><span data-stu-id="89073-124">The Microsoft Teams Rooms device can become unusable if the **Keep my files - Removes Apps and settings, but keeps your personal files** option is selected during the Windows Reset process.</span></span> <span data-ttu-id="89073-125">請勿選取此選項。</span><span class="sxs-lookup"><span data-stu-id="89073-125">Do not select this option.</span></span>
      5. <span data-ttu-id="89073-126">系統會重新開機多次。</span><span class="sxs-lookup"><span data-stu-id="89073-126">The system will reboot multiple times.</span></span> <span data-ttu-id="89073-127">重設完成後，系統會位於 OOBE Windows畫面的 「開箱 (」) 畫面。</span><span class="sxs-lookup"><span data-stu-id="89073-127">When the reset is complete, the system will be at the Windows "out of box experience" (OOBE) screen.</span></span>



## <a name="see-also"></a><span data-ttu-id="89073-128">另請參閱</span><span class="sxs-lookup"><span data-stu-id="89073-128">See also</span></span>

[<span data-ttu-id="89073-129">Microsoft Teams 會議室協助</span><span class="sxs-lookup"><span data-stu-id="89073-129">Microsoft Teams Rooms help</span></span>](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="89073-130">管理 Microsoft Teams 會議室</span><span class="sxs-lookup"><span data-stu-id="89073-130">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)