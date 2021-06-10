---
title: 手動更新Microsoft Teams 會議室裝置
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
appliesto:
- Microsoft Teams
ms.reviewer: sohailta
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 瞭解如何手動將裝置Microsoft Teams 會議室到特定版本。
ms.openlocfilehash: 3353758fa36534994336fc81e0a759c8b9f3c678
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117511"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="5a99d-103">手動更新Microsoft Teams 會議室裝置</span><span class="sxs-lookup"><span data-stu-id="5a99d-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="5a99d-104">此Microsoft Teams 會議室應用程式會透過 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="5a99d-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="5a99d-105">應用程式更新會從應用程式Microsoft Store維護期間自動安裝;這是取得更新的建議方法。</span><span class="sxs-lookup"><span data-stu-id="5a99d-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="5a99d-106">不過，在某些情況下，Teams 會議室裝置無法從Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="5a99d-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="5a99d-107">例如，安全性原則可能不允許裝置連接到網際網路，或可能不允許應用程式從 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="5a99d-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="5a99d-108">或者，您可能想要在執行設定之前先更新裝置，Microsoft Store安裝期間無法使用裝置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="5a99d-109">如果您無法從 Microsoft Store 取得更新，您可以使用離線應用程式更新 PowerShell 腳本，將 Teams 會議室 裝置手動更新至較新版本的 Teams 會議室 App。</span><span class="sxs-lookup"><span data-stu-id="5a99d-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="5a99d-110">請遵循本文中的步驟，手動更新您的Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="5a99d-111">此程式只能更新已安裝Teams 會議室應用程式Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="5a99d-112">它無法用來執行新安裝。</span><span class="sxs-lookup"><span data-stu-id="5a99d-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="5a99d-113">它也無法用來將應用程式降級為較舊版本。</span><span class="sxs-lookup"><span data-stu-id="5a99d-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="5a99d-114">若要執行新安裝的 Teams 會議室應用程式，請針對裝置的特定媒體，與裝置製造商聯繫，或參閱準備[安裝媒體](console.md#prepare-the-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="5a99d-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="5a99d-115">步驟 1：下載離線應用程式更新腳本</span><span class="sxs-lookup"><span data-stu-id="5a99d-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="5a99d-116">首先，下載最新版本的離線應用程式更新腳本。</span><span class="sxs-lookup"><span data-stu-id="5a99d-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="5a99d-117">若要下載腳本，請按一下 <https://go.microsoft.com/fwlink/?linkid=2151817> 。</span><span class="sxs-lookup"><span data-stu-id="5a99d-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="5a99d-118">腳本會下載到您裝置上的預設下載資料夾。</span><span class="sxs-lookup"><span data-stu-id="5a99d-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="5a99d-119">下載的檔案可能會標示為封鎖Windows。</span><span class="sxs-lookup"><span data-stu-id="5a99d-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="5a99d-120">如果您需要執行腳本而不進行任何互動，則需要解除封鎖腳本。</span><span class="sxs-lookup"><span data-stu-id="5a99d-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="5a99d-121">若要解除封鎖腳本，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5a99d-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="5a99d-122">在檔案檔案管理器中以滑鼠右鍵按一下檔案</span><span class="sxs-lookup"><span data-stu-id="5a99d-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="5a99d-123">按一下 **[屬性**</span><span class="sxs-lookup"><span data-stu-id="5a99d-123">Click **Properties**</span></span>
3. <span data-ttu-id="5a99d-124">選取 **取消封鎖**</span><span class="sxs-lookup"><span data-stu-id="5a99d-124">Select **Unblock**</span></span>
4. <span data-ttu-id="5a99d-125">按一下 **[確定**</span><span class="sxs-lookup"><span data-stu-id="5a99d-125">Click **OK**</span></span>

<span data-ttu-id="5a99d-126">若要使用 PowerShell 解除封鎖腳本，請參閱 [解除封鎖-檔案](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)。</span><span class="sxs-lookup"><span data-stu-id="5a99d-126">To unblock the script using PowerShell, see [Unblock-File](/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="5a99d-127">下載離線應用程式更新腳本之後，將檔案傳輸至Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="5a99d-128">您可以在裝置上的系統管理模式中，使用 USB 磁碟機或從網路檔案共用存取檔案，將檔案傳輸至裝置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="5a99d-129">請務必記下檔案儲存在裝置上的位置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="5a99d-130">步驟 2：執行腳本以更新Teams 會議室應用程式</span><span class="sxs-lookup"><span data-stu-id="5a99d-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="5a99d-131">離線應用程式更新腳本必須從提升的命令提示符執行，Skype使用者 (應用程式執行) 的使用者仍然會登錄。</span><span class="sxs-lookup"><span data-stu-id="5a99d-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="5a99d-132">若要進一步瞭解如何登入系統管理員帳戶，以在 Skype 使用者仍登入時使用提升的命令提示，請參閱切換至系統管理模式，[](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)以及當 Microsoft Teams 會議室 應用程式執行時返回 。</span><span class="sxs-lookup"><span data-stu-id="5a99d-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="5a99d-133">執行下列操作，從提升的命令提示符執行腳本：</span><span class="sxs-lookup"><span data-stu-id="5a99d-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="5a99d-134">切換到系統管理模式</span><span class="sxs-lookup"><span data-stu-id="5a99d-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="5a99d-135">按一下 [開始點選圖示，輸入 **命令提示** 符，然後選取 **[以系統管理員角色執行**</span><span class="sxs-lookup"><span data-stu-id="5a99d-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="5a99d-136">執行下列命令，其中包含腳本的完整路徑和腳本 `<path to script>` 檔案名：</span><span class="sxs-lookup"><span data-stu-id="5a99d-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="5a99d-137">例如，如果腳本檔案位於 中，且指令檔名 `C:\Users\Admin\Downloads` 為 `MTR-Update-4.5.6.7.ps1` ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5a99d-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="5a99d-138">允許腳本執行。</span><span class="sxs-lookup"><span data-stu-id="5a99d-138">Allow the script to run.</span></span> <span data-ttu-id="5a99d-139">完成後，腳本會重新開機Teams 會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="5a99d-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="5a99d-140">您也可以使用遠端 PowerShell 執行腳本。</span><span class="sxs-lookup"><span data-stu-id="5a99d-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="5a99d-141">有關在裝置上使用遠端 PowerShell Teams 會議室，請參閱[使用 PowerShell 進行遠端系統管理](rooms-operations.md#remote-management-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="5a99d-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="5a99d-142">步驟 3：確認應用程式已成功更新</span><span class="sxs-lookup"><span data-stu-id="5a99d-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="5a99d-143">如果腳本成功執行，裝置會重新開機至 Teams 會議室 App。</span><span class="sxs-lookup"><span data-stu-id="5a99d-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="5a99d-144">如果腳本遇到問題，它會指出命令列上的問題，並記錄其輸出至檔案。</span><span class="sxs-lookup"><span data-stu-id="5a99d-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="5a99d-145">請遵循腳本提供的任何指示。</span><span class="sxs-lookup"><span data-stu-id="5a99d-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="5a99d-146">如果您需要與 Microsoft 支援服務聯繫，請務必包含記錄檔案以及支援要求。</span><span class="sxs-lookup"><span data-stu-id="5a99d-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="5a99d-147">腳本會提供記錄檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="5a99d-147">The script will provide you with the path to the log file.</span></span>