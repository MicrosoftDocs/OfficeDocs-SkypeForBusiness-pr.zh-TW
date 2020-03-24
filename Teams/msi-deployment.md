---
title: 透過 Microsoft 端點 Configuration Manager 使用 MSI 安裝 Microsoft 團隊
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 系統管理員可以使用團隊 MSI 來大量部署 Microsoft 團隊來選取使用者或電腦。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 084f6d4587bc279c4387cf44b8ed29d38d51d4a6
ms.sourcegitcommit: 613665c866f6fd0febfa6e26ad718241cdfbb207
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/24/2020
ms.locfileid: "42937597"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="76e27-103">使用 Microsoft 端點 Configuration Manager 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="76e27-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="76e27-104">請觀看下列會話，瞭解 Windows 桌面用戶端的優點，以及如何進行規劃，以及部署方式：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)。</span><span class="sxs-lookup"><span data-stu-id="76e27-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="76e27-105">若要使用 Microsoft 端點設定管理員（或群組原則），或適用于廣泛部署的任何協力廠商發佈機制，Microsoft 提供了 MSI 檔案（32位與64位），管理員可以使用它來大量部署團隊來選取使用者，或桌上型電腦.</span><span class="sxs-lookup"><span data-stu-id="76e27-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="76e27-106">系統管理員可以使用這些檔案來遠端部署團隊，讓使用者不需要手動下載團隊 app。</span><span class="sxs-lookup"><span data-stu-id="76e27-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="76e27-107">部署時，小組會自動啟動在該電腦上登入的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="76e27-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="76e27-108">（您可以在安裝應用程式後停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="76e27-109">[請參閱下文](#disable-auto-launch-for-the-msi-installer)。）我們建議您將套件部署到電腦，讓電腦的所有新使用者也能從這項部署獲益。</span><span class="sxs-lookup"><span data-stu-id="76e27-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="76e27-110">以下是 MSI 檔案的連結：</span><span class="sxs-lookup"><span data-stu-id="76e27-110">These are the links to the MSI files:</span></span>


|<span data-ttu-id="76e27-111">實體</span><span class="sxs-lookup"><span data-stu-id="76e27-111">Entity</span></span>  |<span data-ttu-id="76e27-112">32位</span><span class="sxs-lookup"><span data-stu-id="76e27-112">32-bit</span></span>      |<span data-ttu-id="76e27-113">64位</span><span class="sxs-lookup"><span data-stu-id="76e27-113">64-bit</span></span>      |
|---------|---------|---------|
|<span data-ttu-id="76e27-114">商用</span><span class="sxs-lookup"><span data-stu-id="76e27-114">Commercial</span></span>     | [<span data-ttu-id="76e27-115">32位</span><span class="sxs-lookup"><span data-stu-id="76e27-115">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="76e27-116">64位</span><span class="sxs-lookup"><span data-stu-id="76e27-116">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       |
|<span data-ttu-id="76e27-117">聯邦政府-GCC</span><span class="sxs-lookup"><span data-stu-id="76e27-117">Federal Government - GCC</span></span>     | [<span data-ttu-id="76e27-118">32位</span><span class="sxs-lookup"><span data-stu-id="76e27-118">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="76e27-119">64位</span><span class="sxs-lookup"><span data-stu-id="76e27-119">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |
|<span data-ttu-id="76e27-120">聯邦政府-GCC 高</span><span class="sxs-lookup"><span data-stu-id="76e27-120">Federal Government - GCC High</span></span>    | [<span data-ttu-id="76e27-121">32位</span><span class="sxs-lookup"><span data-stu-id="76e27-121">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="76e27-122">64位</span><span class="sxs-lookup"><span data-stu-id="76e27-122">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |
|<span data-ttu-id="76e27-123">聯邦政府-DoD</span><span class="sxs-lookup"><span data-stu-id="76e27-123">Federal Government - DoD</span></span>     | [<span data-ttu-id="76e27-124">32位</span><span class="sxs-lookup"><span data-stu-id="76e27-124">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="76e27-125">64位</span><span class="sxs-lookup"><span data-stu-id="76e27-125">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |

> [!NOTE]
> <span data-ttu-id="76e27-126">在64位作業系統上安裝64位版本的團隊。</span><span class="sxs-lookup"><span data-stu-id="76e27-126">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="76e27-127">如果您嘗試在32位作業系統上安裝64位版本的團隊，安裝將無法成功完成，而且目前您不會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="76e27-127">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and  currently you won't receive an error message.</span></span>

<span data-ttu-id="76e27-128">團隊也可以包含在 Office 365 專業增強版的部署中。</span><span class="sxs-lookup"><span data-stu-id="76e27-128">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="76e27-129">如需詳細資訊，請參閱[使用 Office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="76e27-129">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>

> [!Note]
> <span data-ttu-id="76e27-130">若要深入瞭解 Microsoft Endpoint Configuration Manager，請參閱[何謂 Configuration manager？](https://docs.microsoft.com/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="76e27-130">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](https://docs.microsoft.com/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="76e27-131">部署程式（建議使用）</span><span class="sxs-lookup"><span data-stu-id="76e27-131">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="76e27-132">取得最新套件。</span><span class="sxs-lookup"><span data-stu-id="76e27-132">Retrieve the latest package.</span></span>
2. <span data-ttu-id="76e27-133">使用 MSI 預先填入的預設值。</span><span class="sxs-lookup"><span data-stu-id="76e27-133">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="76e27-134">如有可能，請部署到電腦。</span><span class="sxs-lookup"><span data-stu-id="76e27-134">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="76e27-135">Microsoft 團隊 MSI 套件的運作方式</span><span class="sxs-lookup"><span data-stu-id="76e27-135">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="76e27-136">電腦安裝</span><span class="sxs-lookup"><span data-stu-id="76e27-136">PC installation</span></span>

<span data-ttu-id="76e27-137">[團隊 MSI] 會在程式檔案中放置安裝程式。</span><span class="sxs-lookup"><span data-stu-id="76e27-137">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="76e27-138">每當使用者登入新的 Windows 使用者設定檔時，系統就會啟動安裝程式，而且會在該使用者的`AppData`資料夾中安裝 [小組] app 的複本。</span><span class="sxs-lookup"><span data-stu-id="76e27-138">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="76e27-139">如果使用者已在`AppData`資料夾中安裝 [團隊] 應用程式，則 MSI 安裝程式將會略過該使用者的進程。</span><span class="sxs-lookup"><span data-stu-id="76e27-139">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="76e27-140">請勿使用 MSI 來部署更新，因為用戶端會在檢測到可從服務取得新版本時自動更新。</span><span class="sxs-lookup"><span data-stu-id="76e27-140">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="76e27-141">若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。</span><span class="sxs-lookup"><span data-stu-id="76e27-141">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="76e27-142">如果您部署舊版的 MSI 套件，則用戶端可能會自動更新（在 VDI 環境中除外）。</span><span class="sxs-lookup"><span data-stu-id="76e27-142">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="76e27-143">如果部署的是較舊的版本，MSI 將觸發應用程式更新，讓使用者能夠使用團隊。</span><span class="sxs-lookup"><span data-stu-id="76e27-143">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!Important]
> <span data-ttu-id="76e27-144">我們不建議您變更預設安裝位置，因為這可能會中斷更新流程。</span><span class="sxs-lookup"><span data-stu-id="76e27-144">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="76e27-145">如果版本太舊，最終會封鎖使用者存取服務。</span><span class="sxs-lookup"><span data-stu-id="76e27-145">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="76e27-146">目的電腦需求</span><span class="sxs-lookup"><span data-stu-id="76e27-146">Target computer requirements</span></span>

- <span data-ttu-id="76e27-147">.NET framework 4.5 或更新版本</span><span class="sxs-lookup"><span data-stu-id="76e27-147">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="76e27-148">Windows 8.1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="76e27-148">Windows 8.1 or later</span></span>
- <span data-ttu-id="76e27-149">Windows Server 2012 R2 或更新版本</span><span class="sxs-lookup"><span data-stu-id="76e27-149">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="76e27-150">每個使用者設定檔 3 GB 的磁碟空間（建議使用）</span><span class="sxs-lookup"><span data-stu-id="76e27-150">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="76e27-151">VDI 安裝</span><span class="sxs-lookup"><span data-stu-id="76e27-151">VDI installation</span></span>

<span data-ttu-id="76e27-152">如需如何在 VDI 上部署團隊桌面應用程式的完整指南，請參閱[虛擬化桌面基礎結構的團隊](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="76e27-152">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="76e27-153">清理及重新部署程式</span><span class="sxs-lookup"><span data-stu-id="76e27-153">Clean up and redeployment procedure</span></span>

<span data-ttu-id="76e27-154">如果使用者從使用者設定檔中移除團隊，MSI 安裝程式將會追蹤使用者已卸載小組應用程式，而且不會再安裝該使用者設定檔的小組。</span><span class="sxs-lookup"><span data-stu-id="76e27-154">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="76e27-155">若要在已卸載此使用者的特定電腦上重新部署團隊，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="76e27-155">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="76e27-156">卸載針對每個使用者設定檔所安裝的團隊 app。</span><span class="sxs-lookup"><span data-stu-id="76e27-156">Uninstall the Teams app installed for every user profile.</span></span>
2. <span data-ttu-id="76e27-157">卸載之後，請以遞迴方式刪除`%localappdata%\Microsoft\Teams\`目錄。</span><span class="sxs-lookup"><span data-stu-id="76e27-157">After uninstall, delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="76e27-158">將 MSI 套件重新部署到該特定電腦。</span><span class="sxs-lookup"><span data-stu-id="76e27-158">Redeploy the MSI package to that particular computer.</span></span>

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="76e27-159">避免團隊在安裝後自動啟動</span><span class="sxs-lookup"><span data-stu-id="76e27-159">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="76e27-160">MSI 的預設行為是在使用者登入後立即安裝 [小組] app，然後自動啟動小組。</span><span class="sxs-lookup"><span data-stu-id="76e27-160">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="76e27-161">如果您不想讓團隊在使用者安裝之後自動開始進行，您可以使用群組原則來設定策略設定，或停用 MSI 安裝程式的自動啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-161">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="76e27-162">使用群組原則（建議使用）</span><span class="sxs-lookup"><span data-stu-id="76e27-162">Use Group Policy (recommended)</span></span>

<span data-ttu-id="76e27-163">啟用 [在安裝群組原則設定**之後，禁止 Microsoft 小組自動啟動**]。</span><span class="sxs-lookup"><span data-stu-id="76e27-163">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="76e27-164">您可以在 User Configuration\Policies\Administrative Templates\Microsoft 團隊中找到此原則設定。</span><span class="sxs-lookup"><span data-stu-id="76e27-164">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="76e27-165">這是建議的方法，因為您可以根據組織的需求關閉或開啟原則設定。</span><span class="sxs-lookup"><span data-stu-id="76e27-165">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="76e27-166">在安裝團隊之前啟用此原則設定之後，小組就不會在使用者登入 Windows 時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-166">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="76e27-167">使用者第一次登入團隊後，小組會在下次使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-167">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="76e27-168">若要深入瞭解，請參閱[使用群組原則避免團隊在安裝之後自動啟動](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)。</span><span class="sxs-lookup"><span data-stu-id="76e27-168">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](https://docs.microsoft.com/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="76e27-169">如果您已部署團隊，且想要將此原則設定為 [停用團隊自動啟動]，請先將 [群組原則] 設定設為 [您想要的值]，然後在每個使用者的基礎上執行團隊的 [[自動啟動] 重設腳本](scripts/powershell-script-teams-reset-autostart.md)。</span><span class="sxs-lookup"><span data-stu-id="76e27-169">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="76e27-170">停用 MSI 安裝程式的自動啟動</span><span class="sxs-lookup"><span data-stu-id="76e27-170">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="76e27-171">您可以使用**選項 = "noAutoStart = true"** 參數來停用 MSI 安裝程式的自動啟動，如下所示。</span><span class="sxs-lookup"><span data-stu-id="76e27-171">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="76e27-172">針對32位版本：</span><span class="sxs-lookup"><span data-stu-id="76e27-172">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="76e27-173">針對64位版本：</span><span class="sxs-lookup"><span data-stu-id="76e27-173">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="76e27-174">當使用者登入 Windows 時，會在 MSI 中安裝小組，並將開始團隊的快捷方式新增至使用者的桌面。</span><span class="sxs-lookup"><span data-stu-id="76e27-174">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="76e27-175">在使用者手動開始團隊前，小組將無法啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-175">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="76e27-176">使用者手動啟動團隊後，小組會在使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-176">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="76e27-177">請注意，這些範例也會使用**ALLUSERS = 1**參數。</span><span class="sxs-lookup"><span data-stu-id="76e27-177">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="76e27-178">當您設定此參數時，系統會在 [控制台] 的 [程式和功能] 和 [應用程式 & Windows 設定] 中的 [應用程式] 中，顯示「團隊電腦範圍」的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="76e27-178">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="76e27-179">如果團隊在電腦上擁有管理員認證，則所有使用者都可以卸載小組。</span><span class="sxs-lookup"><span data-stu-id="76e27-179">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="76e27-180">如果您是手動執行 MSI，請務必以提升許可權執行。</span><span class="sxs-lookup"><span data-stu-id="76e27-180">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="76e27-181">即使您是以系統管理員身分執行，而且不是以提升許可權執行，安裝程式也無法將選項設定為停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="76e27-181">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>
