---
title: 使用 Microsoft 端點建構管理員安裝團隊
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rafarhi, jhreddy
audience: admin
description: 使用 Microsoft 端點設定管理員來大量部署 Microsoft 團隊以選取使用者或電腦。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 23bec0ff2e320da917fbdde122913a56f31b6d1c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802323"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="1f694-103">使用 Microsoft 端點 Configuration Manager 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="1f694-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="1f694-104">請觀看下列會話，瞭解 Windows 桌面用戶端的優點，以及如何進行規劃，以及部署方式： [團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)。</span><span class="sxs-lookup"><span data-stu-id="1f694-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="1f694-105">若要使用 Microsoft 端點設定管理員（或群組原則），或適用于廣泛部署的任何協力廠商發佈機制，Microsoft 提供的 MSI 檔案 (32 位和64位) ，管理員可以使用它來大量部署團隊來選取使用者或電腦。</span><span class="sxs-lookup"><span data-stu-id="1f694-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="1f694-106">系統管理員可以使用這些檔案來遠端部署團隊，讓使用者不需要手動下載團隊 app。</span><span class="sxs-lookup"><span data-stu-id="1f694-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="1f694-107">部署時，小組會自動啟動在該電腦上登入的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="1f694-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="1f694-108"> (您可以在安裝應用程式後停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="1f694-109">[請參閱下方](#disable-auto-launch-for-the-msi-installer)。 ) 建議您將套件部署到電腦，所以電腦的所有新使用者也都能從這個部署獲益。</span><span class="sxs-lookup"><span data-stu-id="1f694-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="1f694-110">以下是 MSI 檔案的連結：</span><span class="sxs-lookup"><span data-stu-id="1f694-110">These are the links to the MSI files:</span></span>

|<span data-ttu-id="1f694-111">實體</span><span class="sxs-lookup"><span data-stu-id="1f694-111">Entity</span></span>  |<span data-ttu-id="1f694-112">32位</span><span class="sxs-lookup"><span data-stu-id="1f694-112">32-bit</span></span>      |<span data-ttu-id="1f694-113">64位</span><span class="sxs-lookup"><span data-stu-id="1f694-113">64-bit</span></span>      | <span data-ttu-id="1f694-114">ARM64</span><span class="sxs-lookup"><span data-stu-id="1f694-114">ARM64</span></span> |
|---------|---------|---------|-----------|
|<span data-ttu-id="1f694-115">商用</span><span class="sxs-lookup"><span data-stu-id="1f694-115">Commercial</span></span>     | [<span data-ttu-id="1f694-116">32位</span><span class="sxs-lookup"><span data-stu-id="1f694-116">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="1f694-117">64位</span><span class="sxs-lookup"><span data-stu-id="1f694-117">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [<span data-ttu-id="1f694-118">ARM64</span><span class="sxs-lookup"><span data-stu-id="1f694-118">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|<span data-ttu-id="1f694-119">聯邦政府-GCC</span><span class="sxs-lookup"><span data-stu-id="1f694-119">Federal Government - GCC</span></span>     | [<span data-ttu-id="1f694-120">32位</span><span class="sxs-lookup"><span data-stu-id="1f694-120">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="1f694-121">64位</span><span class="sxs-lookup"><span data-stu-id="1f694-121">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[<span data-ttu-id="1f694-122">ARM64</span><span class="sxs-lookup"><span data-stu-id="1f694-122">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="1f694-123">聯邦政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="1f694-123">Federal Government - GCC High</span></span>    | [<span data-ttu-id="1f694-124">32位</span><span class="sxs-lookup"><span data-stu-id="1f694-124">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="1f694-125">64位</span><span class="sxs-lookup"><span data-stu-id="1f694-125">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[<span data-ttu-id="1f694-126">ARM64</span><span class="sxs-lookup"><span data-stu-id="1f694-126">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="1f694-127">聯邦政府-DoD</span><span class="sxs-lookup"><span data-stu-id="1f694-127">Federal Government - DoD</span></span>     | [<span data-ttu-id="1f694-128">32位</span><span class="sxs-lookup"><span data-stu-id="1f694-128">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="1f694-129">64位</span><span class="sxs-lookup"><span data-stu-id="1f694-129">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [<span data-ttu-id="1f694-130">ARM64</span><span class="sxs-lookup"><span data-stu-id="1f694-130">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

<span data-ttu-id="1f694-131">**若要確保成功地進行部署，請注意下列事項：**</span><span class="sxs-lookup"><span data-stu-id="1f694-131">**To ensure a successful deployment, be aware of the following:**</span></span>

- <span data-ttu-id="1f694-132">在64位作業系統上安裝64位版本的團隊。</span><span class="sxs-lookup"><span data-stu-id="1f694-132">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="1f694-133">如果您嘗試在32位作業系統上安裝64位版本的團隊，安裝將無法成功完成，而且目前您不會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="1f694-133">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and currently you won't receive an error message.</span></span>

- <span data-ttu-id="1f694-134">如果客戶租使用者是在 GCCH 或 DoD 雲彩，客戶應該在登錄中將 **CloudType** 值新增至登錄 **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** 金鑰，以設定登錄中的初始端點。</span><span class="sxs-lookup"><span data-stu-id="1f694-134">If the customer tenant is on the GCCH or DoD clouds, the customer should set the initial endpoint in the registry by adding the **CloudType** value to the **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** key in the registry.</span></span> <span data-ttu-id="1f694-135">**CloudType** 的類型是 **DWORD** ，而值是 (0 = 取消，1 = 商業，2 = GCC，3 = GCCH，4 = DOD) 。</span><span class="sxs-lookup"><span data-stu-id="1f694-135">The type for **CloudType** is **DWORD** and values are (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD).</span></span> <span data-ttu-id="1f694-136">使用登錄金鑰設定端點會限制團隊連線至正確的雲端端點，以與團隊進行預先登入連線。</span><span class="sxs-lookup"><span data-stu-id="1f694-136">Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams.</span></span>

- <span data-ttu-id="1f694-137">團隊也可以包含在企業版 Microsoft 365 應用程式的部署中。</span><span class="sxs-lookup"><span data-stu-id="1f694-137">Teams can also be included with a deployment of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="1f694-138">如需詳細資訊，請參閱 [使用適用于企業的 microsoft 365 應用程式部署 Microsoft 團隊](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="1f694-138">For more information, see [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

- <span data-ttu-id="1f694-139">若要深入瞭解 Microsoft Endpoint Configuration Manager，請參閱 [何謂 Configuration manager？](https://docs.microsoft.com/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="1f694-139">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="1f694-140">建議) 的部署程式 (</span><span class="sxs-lookup"><span data-stu-id="1f694-140">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="1f694-141">取得最新套件。</span><span class="sxs-lookup"><span data-stu-id="1f694-141">Retrieve the latest package.</span></span>
2. <span data-ttu-id="1f694-142">使用 MSI 預先填入的預設值。</span><span class="sxs-lookup"><span data-stu-id="1f694-142">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="1f694-143">如有可能，請部署到電腦。</span><span class="sxs-lookup"><span data-stu-id="1f694-143">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="1f694-144">Microsoft 團隊 MSI 套件的運作方式</span><span class="sxs-lookup"><span data-stu-id="1f694-144">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="1f694-145">電腦安裝</span><span class="sxs-lookup"><span data-stu-id="1f694-145">PC installation</span></span>

<span data-ttu-id="1f694-146">[團隊 MSI] 會在程式檔案中放置安裝程式。</span><span class="sxs-lookup"><span data-stu-id="1f694-146">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="1f694-147">每當使用者登入新的 Windows 使用者設定檔時，系統就會啟動安裝程式，而且會在該使用者的資料夾中安裝 [小組] app 的複本 `AppData` 。</span><span class="sxs-lookup"><span data-stu-id="1f694-147">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="1f694-148">如果使用者已在資料夾中安裝 [團隊] 應用程式 `AppData` ，則 MSI 安裝程式將會略過該使用者的進程。</span><span class="sxs-lookup"><span data-stu-id="1f694-148">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="1f694-149">請勿使用 MSI 來部署更新，因為用戶端會在檢測到可從服務取得新版本時自動更新。</span><span class="sxs-lookup"><span data-stu-id="1f694-149">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="1f694-150">若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。</span><span class="sxs-lookup"><span data-stu-id="1f694-150">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="1f694-151">如果您部署舊版的 MSI 套件，用戶端會自動更新 (但在使用 VDI 環境時，使用者可能會) 。</span><span class="sxs-lookup"><span data-stu-id="1f694-151">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="1f694-152">如果部署的是較舊的版本，MSI 將觸發應用程式更新，讓使用者能夠使用團隊。</span><span class="sxs-lookup"><span data-stu-id="1f694-152">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f694-153">預設位置是64位作業系統上的 C:\Program 檔案 (x86) \Teams 安裝程式，以及32位作業系統上的 C:\Program Files\Teams 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="1f694-153">The default location is C:\Program Files (x86)\Teams Installer on 64-bit operating systems and C:\Program Files\Teams Installer on 32-bit operating systems.</span></span>
> <span data-ttu-id="1f694-154">我們不建議您變更預設安裝位置，因為這可能會中斷更新流程。</span><span class="sxs-lookup"><span data-stu-id="1f694-154">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="1f694-155">如果版本太舊，最終會封鎖使用者存取服務。</span><span class="sxs-lookup"><span data-stu-id="1f694-155">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="1f694-156">目的電腦需求</span><span class="sxs-lookup"><span data-stu-id="1f694-156">Target computer requirements</span></span>

- <span data-ttu-id="1f694-157">.NET framework 4.5 或更新版本</span><span class="sxs-lookup"><span data-stu-id="1f694-157">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="1f694-158">Windows 8.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="1f694-158">Windows 8.1 or later</span></span>
- <span data-ttu-id="1f694-159">Windows Server 2012 R2 或更新版本</span><span class="sxs-lookup"><span data-stu-id="1f694-159">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="1f694-160">每個使用者設定檔的 3 GB 磁碟空間 (建議) </span><span class="sxs-lookup"><span data-stu-id="1f694-160">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="1f694-161">VDI 安裝</span><span class="sxs-lookup"><span data-stu-id="1f694-161">VDI installation</span></span>

<span data-ttu-id="1f694-162">如需如何在 VDI 上部署團隊桌面應用程式的完整指南，請參閱 [虛擬化桌面基礎結構的團隊](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="1f694-162">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="1f694-163">清理及重新部署程式</span><span class="sxs-lookup"><span data-stu-id="1f694-163">Clean up and redeployment procedure</span></span>

<span data-ttu-id="1f694-164">如果使用者從使用者設定檔中移除團隊，MSI 安裝程式將會追蹤使用者已卸載小組應用程式，而且不會再安裝該使用者設定檔的小組。</span><span class="sxs-lookup"><span data-stu-id="1f694-164">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="1f694-165">若要在已卸載此使用者的特定電腦上重新部署團隊，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="1f694-165">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f694-166">後續步驟包含如何修改註冊表的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="1f694-166">The next steps contain information about how to modify the registry.</span></span> <span data-ttu-id="1f694-167">修改之後，請務必先備份註冊表，然後在問題發生時，瞭解如何還原註冊表。</span><span class="sxs-lookup"><span data-stu-id="1f694-167">Make sure that you back up the registry before you modify it and that you know how to restore the registry if a problem occurs.</span></span> <span data-ttu-id="1f694-168">如需如何備份、還原及修改註冊表的詳細資訊，請參閱 [適用于高級使用者的 Windows 註冊資訊](https://support.microsoft.com/help/256986)。</span><span class="sxs-lookup"><span data-stu-id="1f694-168">For more information about how to back up, restore, and modify the registry, see [Windows registry information for advanced users](https://support.microsoft.com/help/256986).</span></span>

1. <span data-ttu-id="1f694-169">卸載針對每個使用者設定檔所安裝的團隊 app。</span><span class="sxs-lookup"><span data-stu-id="1f694-169">Uninstall the Teams app installed for every user profile.</span></span> <span data-ttu-id="1f694-170">如需詳細資訊，請參閱 [卸載 Microsoft 團隊](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)。</span><span class="sxs-lookup"><span data-stu-id="1f694-170">For more information, see [Uninstall Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).</span></span>
2. <span data-ttu-id="1f694-171">在下遞迴刪除目錄 `%localappdata%\Microsoft\Teams\` 。</span><span class="sxs-lookup"><span data-stu-id="1f694-171">Delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="1f694-172">刪除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 註冊表值。</span><span class="sxs-lookup"><span data-stu-id="1f694-172">Delete the `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` registry value.</span></span>
4. <span data-ttu-id="1f694-173">將 MSI 套件重新部署到該特定電腦。</span><span class="sxs-lookup"><span data-stu-id="1f694-173">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="1f694-174">您也可以使用我們的 [小組部署清理腳本](scripts/powershell-script-deployment-cleanup.md) 來完成步驟1和2。</span><span class="sxs-lookup"><span data-stu-id="1f694-174">You can also use our [Teams deployment clean up script](scripts/powershell-script-deployment-cleanup.md) to complete steps 1 and 2.</span></span>  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="1f694-175">避免團隊在安裝後自動啟動</span><span class="sxs-lookup"><span data-stu-id="1f694-175">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="1f694-176">MSI 的預設行為是在使用者登入後立即安裝 [小組] app，然後自動啟動小組。</span><span class="sxs-lookup"><span data-stu-id="1f694-176">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="1f694-177">如果您不想讓團隊在使用者安裝之後自動開始進行，您可以使用群組原則來設定策略設定，或停用 MSI 安裝程式的自動啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-177">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="1f694-178">使用群組原則 (建議的) </span><span class="sxs-lookup"><span data-stu-id="1f694-178">Use Group Policy (recommended)</span></span>

<span data-ttu-id="1f694-179">啟用 [在安裝群組原則設定 **之後，禁止 Microsoft 小組自動啟動** ]。</span><span class="sxs-lookup"><span data-stu-id="1f694-179">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="1f694-180">您可以在 User Configuration\Policies\Administrative Templates\Microsoft 團隊中找到此原則設定。</span><span class="sxs-lookup"><span data-stu-id="1f694-180">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="1f694-181">這是建議的方法，因為您可以根據組織的需求關閉或開啟原則設定。</span><span class="sxs-lookup"><span data-stu-id="1f694-181">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="1f694-182">在安裝團隊之前啟用此原則設定之後，小組就不會在使用者登入 Windows 時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-182">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="1f694-183">使用者第一次登入團隊後，小組會在下次使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-183">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="1f694-184">若要深入瞭解，請參閱 [使用群組原則避免團隊在安裝之後自動啟動](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。</span><span class="sxs-lookup"><span data-stu-id="1f694-184">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="1f694-185">如果您已部署團隊，且想要將此原則設定為 [停用團隊自動啟動]，請先將 [群組原則] 設定設為 [您想要的值]，然後在每個使用者的基礎上執行團隊的 [ [自動啟動] 重設腳本](scripts/powershell-script-teams-reset-autostart.md) 。</span><span class="sxs-lookup"><span data-stu-id="1f694-185">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="1f694-186">停用 MSI 安裝程式的自動啟動</span><span class="sxs-lookup"><span data-stu-id="1f694-186">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="1f694-187">您可以使用 **選項 = "noAutoStart = true"** 參數來停用 MSI 安裝程式的自動啟動，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1f694-187">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="1f694-188">針對32位版本：</span><span class="sxs-lookup"><span data-stu-id="1f694-188">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="1f694-189">針對64位版本：</span><span class="sxs-lookup"><span data-stu-id="1f694-189">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="1f694-190">當使用者登入 Windows 時，會在 MSI 中安裝小組，並將開始團隊的快捷方式新增至使用者的桌面。</span><span class="sxs-lookup"><span data-stu-id="1f694-190">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="1f694-191">在使用者手動開始團隊前，小組將無法啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-191">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="1f694-192">使用者手動啟動團隊後，小組會在使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-192">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="1f694-193">請注意，這些範例也會使用 **ALLUSERS = 1** 參數。</span><span class="sxs-lookup"><span data-stu-id="1f694-193">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="1f694-194">當您設定此參數時，[小組] Machine-Wide 安裝程式會出現在 [控制台] 的 [程式和功能] 中，以及電腦所有使用者的 [Windows 設定] & 功能。</span><span class="sxs-lookup"><span data-stu-id="1f694-194">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="1f694-195">如果團隊在電腦上擁有管理員認證，則所有使用者都可以卸載小組。</span><span class="sxs-lookup"><span data-stu-id="1f694-195">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="1f694-196">如果您是手動執行 MSI，請務必以提升許可權執行。</span><span class="sxs-lookup"><span data-stu-id="1f694-196">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="1f694-197">即使您是以系統管理員身分執行，而且不是以提升許可權執行，安裝程式也無法將選項設定為停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="1f694-197">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
