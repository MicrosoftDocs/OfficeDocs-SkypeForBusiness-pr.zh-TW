---
title: 手動更新 Microsoft 團隊聊天室裝置
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
description: 瞭解如何手動將您的 Microsoft 團隊聊天室裝置更新為特定版本。
ms.openlocfilehash: fc5602aad6ffdb52ddd9f58c458b0fd6d2a625fd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731389"
---
# <a name="manually-update-a-microsoft-teams-rooms-device"></a><span data-ttu-id="92e44-103">手動更新 Microsoft 團隊聊天室裝置</span><span class="sxs-lookup"><span data-stu-id="92e44-103">Manually update a Microsoft Teams Rooms device</span></span>

<span data-ttu-id="92e44-104">Microsoft 團隊聊天室 app 是透過 Microsoft Store 發佈。</span><span class="sxs-lookup"><span data-stu-id="92e44-104">The Microsoft Teams Rooms app is distributed through the Microsoft Store.</span></span> <span data-ttu-id="92e44-105">在夜間維護期間，會自動從 Microsoft Store 安裝應用程式的更新。這是取得更新的建議方法。</span><span class="sxs-lookup"><span data-stu-id="92e44-105">Updates to the app are installed from the Microsoft Store automatically during nightly maintenance; this is the recommended method to get updates.</span></span> <span data-ttu-id="92e44-106">不過，在某些情況下，小組機房裝置無法從 Microsoft 網上商店接收更新。</span><span class="sxs-lookup"><span data-stu-id="92e44-106">However, there are some situations where a Teams Rooms device can't receive updates from the Microsoft Store.</span></span> <span data-ttu-id="92e44-107">例如，安全性原則可能不允許裝置連線至網際網路，或可能不允許從 Microsoft 網上商店下載 app。</span><span class="sxs-lookup"><span data-stu-id="92e44-107">For example, security policies may not allow devices to connect to the Internet or may not allow apps to be downloaded from the Microsoft Store.</span></span> <span data-ttu-id="92e44-108">或者，您可能會想要在執行安裝程式之前更新裝置，在此期間無法使用 Microsoft Store。</span><span class="sxs-lookup"><span data-stu-id="92e44-108">Or, you may want to update a device before performing setup, during which the Microsoft Store isn't available.</span></span>

<span data-ttu-id="92e44-109">如果您無法從 Microsoft 網上商店取得更新，您可以使用離線 app 更新 PowerShell 腳本，將團隊機房裝置手動更新為較新版本的團隊聊天室 app。</span><span class="sxs-lookup"><span data-stu-id="92e44-109">If you can't get updates from the Microsoft Store, you can use an offline app update PowerShell script to manually update your Teams Rooms devices to a newer version of the Teams Rooms app.</span></span> <span data-ttu-id="92e44-110">請依照本文所述的步驟，手動更新您的小組聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="92e44-110">Follow the steps in this article to manually update your Teams Rooms devices.</span></span>

> [!NOTE]
> <span data-ttu-id="92e44-111">這個程式只能更新已安裝 [小組室] app 的小組會議室裝置。</span><span class="sxs-lookup"><span data-stu-id="92e44-111">This process can only update a Teams Rooms device with the Teams Rooms app already installed.</span></span> <span data-ttu-id="92e44-112">無法用來執行新的安裝。</span><span class="sxs-lookup"><span data-stu-id="92e44-112">It can't be used to perform a new installation.</span></span> <span data-ttu-id="92e44-113">它也無法用來將應用程式降級至較舊的版本。</span><span class="sxs-lookup"><span data-stu-id="92e44-113">It also can't be used to downgrade the app to an older version.</span></span> <span data-ttu-id="92e44-114">若要執行 [團隊聊天室] app 的新安裝，請與您的裝置製造商聯繫，以取得其專用的媒體，或參閱 [準備安裝媒體](console.md#prepare-the-installation-media)。</span><span class="sxs-lookup"><span data-stu-id="92e44-114">To perform a new installation of the Teams Rooms app, contact your device's manufacturer for media specific to it, or see [Prepare the installation media](console.md#prepare-the-installation-media).</span></span>

## <a name="step-1-download-the-offline-app-update-script"></a><span data-ttu-id="92e44-115">步驟1：下載離線 app 更新腳本</span><span class="sxs-lookup"><span data-stu-id="92e44-115">Step 1: Download the offline app update script</span></span>

<span data-ttu-id="92e44-116">首先，請下載最新版本的離線 app 更新腳本。</span><span class="sxs-lookup"><span data-stu-id="92e44-116">First, download the latest version of the offline app update script.</span></span> <span data-ttu-id="92e44-117">若要下載腳本，請按一下 <https://go.microsoft.com/fwlink/?linkid=2151817> 。</span><span class="sxs-lookup"><span data-stu-id="92e44-117">To download the script, click <https://go.microsoft.com/fwlink/?linkid=2151817>.</span></span> <span data-ttu-id="92e44-118">此腳本將會下載到您裝置上的預設 [下載] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="92e44-118">The script will be downloaded to the default downloads folder on your device.</span></span>

<span data-ttu-id="92e44-119">已下載的檔案可能會標示為 Windows 所封鎖。</span><span class="sxs-lookup"><span data-stu-id="92e44-119">Downloaded files may be marked as blocked by Windows.</span></span> <span data-ttu-id="92e44-120">如果您需要執行腳本而不進行任何互動，您必須解除封鎖腳本。</span><span class="sxs-lookup"><span data-stu-id="92e44-120">If you need to run the script without any interaction, you'll need to unblock the script.</span></span> <span data-ttu-id="92e44-121">若要解除封鎖腳本，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="92e44-121">To unblock the script, do the following:</span></span>

1. <span data-ttu-id="92e44-122">在檔案資源管理器中以滑鼠右鍵按一下檔案</span><span class="sxs-lookup"><span data-stu-id="92e44-122">Right-click on the file in File Explorer</span></span>
2. <span data-ttu-id="92e44-123">按一下 [**屬性**]</span><span class="sxs-lookup"><span data-stu-id="92e44-123">Click **Properties**</span></span>
3. <span data-ttu-id="92e44-124">選取 [**解除封鎖**]</span><span class="sxs-lookup"><span data-stu-id="92e44-124">Select **Unblock**</span></span>
4. <span data-ttu-id="92e44-125">按一下 **[確定]**</span><span class="sxs-lookup"><span data-stu-id="92e44-125">Click **OK**</span></span>

<span data-ttu-id="92e44-126">若要使用 PowerShell 解除封鎖腳本，請參閱 [解除封鎖](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1)檔案。</span><span class="sxs-lookup"><span data-stu-id="92e44-126">To unblock the script using PowerShell, see [Unblock-File](https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/unblock-file?view=powershell-7.1).</span></span>

<span data-ttu-id="92e44-127">下載離線 app 更新腳本之後，請將檔案轉接至小組聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="92e44-127">After the offline app update script is downloaded, transfer the file to the Teams Rooms device.</span></span> <span data-ttu-id="92e44-128">您可以使用 USB 磁片磁碟機或從網路檔案共用（在裝置上為 [系統管理] 模式）存取檔案，以將檔案傳輸到裝置。</span><span class="sxs-lookup"><span data-stu-id="92e44-128">You can transfer a file to the device by using a USB drive or by accessing the file from a network file share while in Admin Mode on the device.</span></span> <span data-ttu-id="92e44-129">請務必注意您在裝置上儲存檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="92e44-129">Be sure to note where you save the file on the device.</span></span>

## <a name="step-2-run-the-script-to-update-the-teams-rooms-app"></a><span data-ttu-id="92e44-130">步驟2：執行腳本以更新團隊聊天室應用程式</span><span class="sxs-lookup"><span data-stu-id="92e44-130">Step 2: Run the script to update the Teams Rooms app</span></span>

<span data-ttu-id="92e44-131">離線 app 更新腳本需要從提升許可權的命令提示字元執行，而 Skype 使用者 (應用程式所使用的使用者) 仍已登入。</span><span class="sxs-lookup"><span data-stu-id="92e44-131">The offline app update script needs to be run from an elevated command prompt while the Skype user (the user under which the app runs) is still signed in.</span></span> <span data-ttu-id="92e44-132">如需如何登入管理員帳戶以在 Skype 使用者仍登入時使用提升的命令提示字元的詳細資訊，請參閱在 [Microsoft 團隊聊天室 app 執行時，切換到 [管理員模式] 並返回 [返回]](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running)。</span><span class="sxs-lookup"><span data-stu-id="92e44-132">For more information about how to log into an admin account to use the elevated command prompt while the Skype user is still logged in, see [Switching to Admin Mode and back when the Microsoft Teams Rooms app is running](rooms-operations.md#switching-to-admin-mode-and-back-when-the-microsoft-teams-rooms-app-is-running).</span></span>

<span data-ttu-id="92e44-133">請執行下列動作，從提升許可權的命令提示字元執行腳本：</span><span class="sxs-lookup"><span data-stu-id="92e44-133">Do the following to run the script from an elevated command prompt:</span></span>

1. <span data-ttu-id="92e44-134">切換到 [管理員模式]</span><span class="sxs-lookup"><span data-stu-id="92e44-134">Switch to Admin Mode</span></span>
2. <span data-ttu-id="92e44-135">按一下 [開始] 圖示，輸入 **命令提示** 字元，然後選取 [以 **系統管理員身分執行**]</span><span class="sxs-lookup"><span data-stu-id="92e44-135">Click the Start icon, type **Command Prompt**, and then select **Run as administrator**</span></span>
3. <span data-ttu-id="92e44-136">執行下列命令，其中 `<path to script>` 包含腳本的完整路徑和腳本檔案的名稱：</span><span class="sxs-lookup"><span data-stu-id="92e44-136">Run the following command where `<path to script>` includes the full path to the script and the name of the script file:</span></span>

    ```console
    PowerShell -ExecutionPolicy Unrestricted "<path to script>"
    ```

<span data-ttu-id="92e44-137">例如，如果腳本檔案位於中 `C:\Users\Admin\Downloads` ，而指令檔名是 `MTR-Update-4.5.6.7.ps1` ，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="92e44-137">For example, if the script file is located in `C:\Users\Admin\Downloads`, and the script file name is `MTR-Update-4.5.6.7.ps1`, run the following command:</span></span>

```console
PowerShell -ExecutionPolicy Unrestricted "C:\Users\Admin\Downloads\MTR-Update-4.5.6.7.ps1"
```

<span data-ttu-id="92e44-138">允許腳本執行。</span><span class="sxs-lookup"><span data-stu-id="92e44-138">Allow the script to run.</span></span> <span data-ttu-id="92e44-139">完成後，腳本會重新開機小組聊天室裝置。</span><span class="sxs-lookup"><span data-stu-id="92e44-139">When it's finished, the script will reboot the Teams Rooms device.</span></span>

<span data-ttu-id="92e44-140">您也可以使用遠端 PowerShell 來執行腳本。</span><span class="sxs-lookup"><span data-stu-id="92e44-140">You can also run the script by using Remote PowerShell.</span></span> <span data-ttu-id="92e44-141">如需有關將遠端 PowerShell 與團隊聊天室裝置結合使用的詳細資訊，請參閱 [使用 PowerShell 進行遠端系統管理](rooms-operations.md#remote-management-using-powershell)。</span><span class="sxs-lookup"><span data-stu-id="92e44-141">For more information about using Remote PowerShell with Teams Rooms devices, see [Remote Management using PowerShell](rooms-operations.md#remote-management-using-powershell).</span></span>

## <a name="step-3-verify-the-app-has-been-updated-successfully"></a><span data-ttu-id="92e44-142">步驟3：驗證 app 已順利更新</span><span class="sxs-lookup"><span data-stu-id="92e44-142">Step 3: Verify the app has been updated successfully</span></span>

<span data-ttu-id="92e44-143">如果腳本順利執行，裝置將會重新開機至 [小組室] app。</span><span class="sxs-lookup"><span data-stu-id="92e44-143">If the script runs successfully, the device will reboot into the Teams Rooms app.</span></span>

<span data-ttu-id="92e44-144">如果腳本遇到問題，會在命令列上指出問題，並將其輸出記錄到檔案中。</span><span class="sxs-lookup"><span data-stu-id="92e44-144">If the script encounters a problem, it will indicate what the problem is on the command line and record its output to a file.</span></span> <span data-ttu-id="92e44-145">依照腳本提供的任何指示進行。</span><span class="sxs-lookup"><span data-stu-id="92e44-145">Follow any instructions that the script provides.</span></span> <span data-ttu-id="92e44-146">如果您需要與 Microsoft 支援人員取得聯繫，請務必將記錄檔與支援要求一起隨附。</span><span class="sxs-lookup"><span data-stu-id="92e44-146">If you need to contact Microsoft Support, make sure to include the log file along with the support request.</span></span> <span data-ttu-id="92e44-147">此腳本將提供記錄檔的路徑。</span><span class="sxs-lookup"><span data-stu-id="92e44-147">The script will provide you with the path to the log file.</span></span>
