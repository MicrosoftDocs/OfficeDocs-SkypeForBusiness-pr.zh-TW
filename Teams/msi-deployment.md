---
title: 使用 Teams 安裝Microsoft Endpoint Configuration Manager
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: amitsri
audience: admin
description: 使用 Microsoft Endpoint Configuration Manager大量部署Microsoft Teams以選取使用者或電腦。
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
ms.openlocfilehash: b31ffca29891a903c68614239bacedabc6729d39
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098109"
---
# <a name="install-microsoft-teams-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="dc224-103">使用 Microsoft Teams 安裝Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dc224-103">Install Microsoft Teams using Microsoft Endpoint Configuration Manager</span></span>

> [!Tip]
> <span data-ttu-id="dc224-104">觀看下列會話以瞭解桌面用戶端Windows、如何規劃及部署它：Teams Windows[用戶端](https://aka.ms/teams-clients)。</span><span class="sxs-lookup"><span data-stu-id="dc224-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients).</span></span>

<span data-ttu-id="dc224-105">若要使用 Microsoft Endpoint Configuration Manager、群組原則或任何協力廠商發佈機制進行廣泛部署，Microsoft 已提供 MSI 檔案 (32 位和 64 位) 系統管理員可用於大量部署 Teams 以選取使用者或電腦。</span><span class="sxs-lookup"><span data-stu-id="dc224-105">To use Microsoft Endpoint Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both 32-bit and 64-bit) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="dc224-106">系統管理員可以使用這些檔案來遠端部署Teams讓使用者不需要手動下載Teams應用程式。</span><span class="sxs-lookup"><span data-stu-id="dc224-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="dc224-107">部署之後，Teams將針對所有在該電腦上登錄的使用者自動啟動。</span><span class="sxs-lookup"><span data-stu-id="dc224-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="dc224-108"> (安裝應用程式之後，您可以停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="dc224-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="dc224-109">[請參閱下方的](#disable-auto-launch-for-the-msi-installer).) 我們建議您將套件部署到電腦，因此所有新使用者也會受益于此部署。</span><span class="sxs-lookup"><span data-stu-id="dc224-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span>

<span data-ttu-id="dc224-110">這些是 MSI 檔案的連結：</span><span class="sxs-lookup"><span data-stu-id="dc224-110">These are the links to the MSI files:</span></span>

|<span data-ttu-id="dc224-111">實體</span><span class="sxs-lookup"><span data-stu-id="dc224-111">Entity</span></span>  |<span data-ttu-id="dc224-112">32 位</span><span class="sxs-lookup"><span data-stu-id="dc224-112">32-bit</span></span>      |<span data-ttu-id="dc224-113">64 位</span><span class="sxs-lookup"><span data-stu-id="dc224-113">64-bit</span></span>      | <span data-ttu-id="dc224-114">ARM64</span><span class="sxs-lookup"><span data-stu-id="dc224-114">ARM64</span></span> |
|---------|---------|---------|-----------|
|<span data-ttu-id="dc224-115">商業</span><span class="sxs-lookup"><span data-stu-id="dc224-115">Commercial</span></span>     | [<span data-ttu-id="dc224-116">32 位</span><span class="sxs-lookup"><span data-stu-id="dc224-116">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="dc224-117">64 位</span><span class="sxs-lookup"><span data-stu-id="dc224-117">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)       | [<span data-ttu-id="dc224-118">ARM64</span><span class="sxs-lookup"><span data-stu-id="dc224-118">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|
|<span data-ttu-id="dc224-119">美國政府 - GCC</span><span class="sxs-lookup"><span data-stu-id="dc224-119">U.S. Government - GCC</span></span>     | [<span data-ttu-id="dc224-120">32 位</span><span class="sxs-lookup"><span data-stu-id="dc224-120">32-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&ring=general_gcc&download=true)       | [<span data-ttu-id="dc224-121">64 位</span><span class="sxs-lookup"><span data-stu-id="dc224-121">64-bit</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&ring=general_gcc&download=true)        |[<span data-ttu-id="dc224-122">ARM64</span><span class="sxs-lookup"><span data-stu-id="dc224-122">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="dc224-123">美國政府 - GCC高</span><span class="sxs-lookup"><span data-stu-id="dc224-123">U.S. Government - GCC High</span></span>    | [<span data-ttu-id="dc224-124">32 位</span><span class="sxs-lookup"><span data-stu-id="dc224-124">32-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)         | [<span data-ttu-id="dc224-125">64 位</span><span class="sxs-lookup"><span data-stu-id="dc224-125">64-bit</span></span>](https://gov.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        |[<span data-ttu-id="dc224-126">ARM64</span><span class="sxs-lookup"><span data-stu-id="dc224-126">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true) |
|<span data-ttu-id="dc224-127">美國政府 - DoD</span><span class="sxs-lookup"><span data-stu-id="dc224-127">U.S. Government - DoD</span></span>     | [<span data-ttu-id="dc224-128">32 位</span><span class="sxs-lookup"><span data-stu-id="dc224-128">32-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&managedInstaller=true&download=true)        | [<span data-ttu-id="dc224-129">64 位</span><span class="sxs-lookup"><span data-stu-id="dc224-129">64-bit</span></span>](https://dod.teams.microsoft.us/downloads/desktopurl?env=production&plat=windows&arch=x64&managedInstaller=true&download=true)        | [<span data-ttu-id="dc224-130">ARM64</span><span class="sxs-lookup"><span data-stu-id="dc224-130">ARM64</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&arch=arm64&managedInstaller=true&download=true)|

<span data-ttu-id="dc224-131">**若要確保部署成功，請注意下列事項：**</span><span class="sxs-lookup"><span data-stu-id="dc224-131">**To ensure a successful deployment, be aware of the following:**</span></span>

- <span data-ttu-id="dc224-132">在 64 位作業系統上Teams 64 位版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="dc224-132">Install the 64-bit version of Teams on 64-bit operating systems.</span></span> <span data-ttu-id="dc224-133">如果您嘗試在 32 位作業系統上Teams 64 位版本的 Teams，安裝將不會成功，而且您目前不會收到錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="dc224-133">If you try to install the 64-bit version of Teams on a 32-bit operating system, the installation won't be successful and currently you won't receive an error message.</span></span>

- <span data-ttu-id="dc224-134">如果客戶租使用者位於 GCCH 或 DoD 雲端上，客戶應新增 **CloudType** 值至註冊表中的HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams鍵，以在註冊表中設定初始端點。</span><span class="sxs-lookup"><span data-stu-id="dc224-134">If the customer tenant is on the GCCH or DoD clouds, the customer should set the initial endpoint in the registry by adding the **CloudType** value to the **HKEY_CURRENT_USER\SOFTWARE\Policies\Microsoft\Office\16.0\Teams** key in the registry.</span></span> <span data-ttu-id="dc224-135">CloudType的類型是 **DWORD，** 值為 (0 = 未套用、1 = 商業、2 = GCC、3 = GCCH、4 = DOD) 。</span><span class="sxs-lookup"><span data-stu-id="dc224-135">The type for **CloudType** is **DWORD** and values are (0 = Unset, 1 = commercial, 2 = GCC, 3 = GCCH, 4 = DOD).</span></span> <span data-ttu-id="dc224-136">使用登錄鍵設定端點會限制Teams連接到正確的雲端端點，以使用 Teams。</span><span class="sxs-lookup"><span data-stu-id="dc224-136">Setting the endpoint with the registry key restricts Teams to connecting to the correct cloud endpoint for pre-sign-in connectivity with Teams.</span></span>

- <span data-ttu-id="dc224-137">Teams，也可以包含在部署 Microsoft 365 Apps 企業版。</span><span class="sxs-lookup"><span data-stu-id="dc224-137">Teams can also be included with a deployment of Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="dc224-138">詳細資訊，請參閱使用 Microsoft Teams[部署Microsoft 365 Apps 企業版。](/deployoffice/teams-install)</span><span class="sxs-lookup"><span data-stu-id="dc224-138">For more information, see [Deploy Microsoft Teams with Microsoft 365 Apps for enterprise](/deployoffice/teams-install).</span></span>

- <span data-ttu-id="dc224-139">若要進一Microsoft Endpoint Configuration Manager，請參閱什麼是 Configuration [Manager？](/configmgr/core/understand/introduction)</span><span class="sxs-lookup"><span data-stu-id="dc224-139">To learn more about Microsoft Endpoint Configuration Manager, see [What is Configuration Manager?](/configmgr/core/understand/introduction)</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="dc224-140">部署程式 (建議) </span><span class="sxs-lookup"><span data-stu-id="dc224-140">Deployment procedure (recommended)</span></span>

1. <span data-ttu-id="dc224-141">取回最新的套件。</span><span class="sxs-lookup"><span data-stu-id="dc224-141">Retrieve the latest package.</span></span>
2. <span data-ttu-id="dc224-142">使用 MSI 預先填充的預設值。</span><span class="sxs-lookup"><span data-stu-id="dc224-142">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="dc224-143">盡可能部署到電腦。</span><span class="sxs-lookup"><span data-stu-id="dc224-143">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="dc224-144">MSI 套件Microsoft Teams運作方式</span><span class="sxs-lookup"><span data-stu-id="dc224-144">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="dc224-145">電腦安裝</span><span class="sxs-lookup"><span data-stu-id="dc224-145">PC installation</span></span>

<span data-ttu-id="dc224-146">MSI Teams將安裝程式放在程式檔案中。</span><span class="sxs-lookup"><span data-stu-id="dc224-146">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="dc224-147">每當使用者登錄新的 Windows使用者設定檔時，安裝程式就會啟動，Teams應用程式的副本將會安裝在該使用者 `AppData` 的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="dc224-147">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's `AppData` folder.</span></span> <span data-ttu-id="dc224-148">如果使用者已在資料夾中Teams應用程式 `AppData` ，MSI 安裝程式會略過該使用者的程式。</span><span class="sxs-lookup"><span data-stu-id="dc224-148">If a user already has the Teams app installed in the `AppData` folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="dc224-149">請勿使用 MSI 來部署更新，因為當用戶端偵測到可從服務使用新版本時，就會自動更新。</span><span class="sxs-lookup"><span data-stu-id="dc224-149">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="dc224-150">若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。</span><span class="sxs-lookup"><span data-stu-id="dc224-150">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span> <span data-ttu-id="dc224-151">如果您部署舊版 MSI 套件，用戶端會自動更新 (VDI 環境除外) 使用者可能的話。</span><span class="sxs-lookup"><span data-stu-id="dc224-151">If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="dc224-152">如果部署非常舊的版本，MSI 會先觸發應用程式更新，使用者才能Teams。</span><span class="sxs-lookup"><span data-stu-id="dc224-152">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc224-153">預設位置為 C：\Program Files (x86) \Teams 64 位作業系統上的安裝程式，以及 32 位作業系統上的 C：\Program Files\Teams Installer。</span><span class="sxs-lookup"><span data-stu-id="dc224-153">The default location is C:\Program Files (x86)\Teams Installer on 64-bit operating systems and C:\Program Files\Teams Installer on 32-bit operating systems.</span></span>
> <span data-ttu-id="dc224-154">我們不建議您變更預設安裝位置，因為這樣做可能會中斷更新流程。</span><span class="sxs-lookup"><span data-stu-id="dc224-154">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="dc224-155">版本太舊，最終會封鎖使用者存取服務。</span><span class="sxs-lookup"><span data-stu-id="dc224-155">Having too old a version will eventually block users from accessing the service.</span></span>

#### <a name="target-computer-requirements"></a><span data-ttu-id="dc224-156">目的電腦需求</span><span class="sxs-lookup"><span data-stu-id="dc224-156">Target computer requirements</span></span>

- <span data-ttu-id="dc224-157">.NET framework 4.5 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc224-157">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="dc224-158">Windows 8.1或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc224-158">Windows 8.1 or later</span></span>
- <span data-ttu-id="dc224-159">Windows Server 2012R2 或更高版本</span><span class="sxs-lookup"><span data-stu-id="dc224-159">Windows Server 2012 R2 or later</span></span>
- <span data-ttu-id="dc224-160">每個使用者設定檔的磁碟空間為 3 GB， (建議) </span><span class="sxs-lookup"><span data-stu-id="dc224-160">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="dc224-161">VDI 安裝</span><span class="sxs-lookup"><span data-stu-id="dc224-161">VDI installation</span></span>

<span data-ttu-id="dc224-162">若要瞭解如何在 VDI 上部署Teams桌面應用程式的完整指南，請參閱Teams桌面基礎結構[的指南](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="dc224-162">For complete guidance on how to deploy the Teams desktop app on VDI, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="dc224-163">清理和重新部署程式</span><span class="sxs-lookup"><span data-stu-id="dc224-163">Clean up and redeployment procedure</span></span>

<span data-ttu-id="dc224-164">如果使用者從使用者設定檔Teams，MSI 安裝程式會追蹤使用者已卸載 Teams 應用程式，且不再Teams使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="dc224-164">If a user uninstalls Teams from their user profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that user profile.</span></span> <span data-ttu-id="dc224-165">若要將Teams使用者重新部署至已卸載的特定電腦上，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="dc224-165">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc224-166">下列步驟包含如何修改註冊表的資訊。</span><span class="sxs-lookup"><span data-stu-id="dc224-166">The next steps contain information about how to modify the registry.</span></span> <span data-ttu-id="dc224-167">請務必先備份該註冊表，再進行修改，並瞭解如何在發生問題時還原註冊表。</span><span class="sxs-lookup"><span data-stu-id="dc224-167">Make sure that you back up the registry before you modify it and that you know how to restore the registry if a problem occurs.</span></span> <span data-ttu-id="dc224-168">若要進一步瞭解如何備份、還原及修改登錄，請參閱Windows[使用者的登錄資訊](https://support.microsoft.com/help/256986)。</span><span class="sxs-lookup"><span data-stu-id="dc224-168">For more information about how to back up, restore, and modify the registry, see [Windows registry information for advanced users](https://support.microsoft.com/help/256986).</span></span>

1. <span data-ttu-id="dc224-169">卸載每個Teams安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="dc224-169">Uninstall the Teams app installed for every user profile.</span></span> <span data-ttu-id="dc224-170">若要詳細資訊，請參閱卸載[Microsoft Teams。](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop)</span><span class="sxs-lookup"><span data-stu-id="dc224-170">For more information, see [Uninstall Microsoft Teams](https://support.office.com/article/uninstall-microsoft-teams-3b159754-3c26-4952-abe7-57d27f5f4c81#ID0EAABAAA=Desktop).</span></span>
2. <span data-ttu-id="dc224-171">在 下遞迴刪除目錄 `%localappdata%\Microsoft\Teams\` 。</span><span class="sxs-lookup"><span data-stu-id="dc224-171">Delete the directory recursively under `%localappdata%\Microsoft\Teams\`.</span></span>
3. <span data-ttu-id="dc224-172">刪除 `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` 註冊表值。</span><span class="sxs-lookup"><span data-stu-id="dc224-172">Delete the `HKEY_CURRENT_USER\Software\Microsoft\Office\Teams\PreventInstallationFromMsi` registry value.</span></span>
4. <span data-ttu-id="dc224-173">將 MSI 套件重新部署至該特定電腦。</span><span class="sxs-lookup"><span data-stu-id="dc224-173">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP]
> <span data-ttu-id="dc224-174">您也可以使用我們的部署清理[Teams腳本](scripts/powershell-script-deployment-cleanup.md)來完成步驟 1 和 2。</span><span class="sxs-lookup"><span data-stu-id="dc224-174">You can also use our [Teams deployment clean up script](scripts/powershell-script-deployment-cleanup.md) to complete steps 1 and 2.</span></span>  

## <a name="prevent-teams-from-starting-automatically-after-installation"></a><span data-ttu-id="dc224-175">防止Teams安裝後自動啟動</span><span class="sxs-lookup"><span data-stu-id="dc224-175">Prevent Teams from starting automatically after installation</span></span>

<span data-ttu-id="dc224-176">MSI 的預設行為是使用者一Teams安裝應用程式，然後自動Teams。</span><span class="sxs-lookup"><span data-stu-id="dc224-176">The default behavior of the MSI is to install the Teams app as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="dc224-177">如果您不希望系統安裝Teams使用者自動啟動，您可以使用群組原則設定或停用 MSI 安裝程式的自動啟動。</span><span class="sxs-lookup"><span data-stu-id="dc224-177">If you don't want Teams to start automatically for users after it's installed, you can use Group Policy to set a policy setting or disable auto launch for the MSI installer.</span></span>

### <a name="use-group-policy-recommended"></a><span data-ttu-id="dc224-178">使用群組原則 (建議) </span><span class="sxs-lookup"><span data-stu-id="dc224-178">Use Group Policy (recommended)</span></span>

<span data-ttu-id="dc224-179">啟用安裝 **Microsoft Teams自動啟動組** 策略設定。</span><span class="sxs-lookup"><span data-stu-id="dc224-179">Enable the **Prevent Microsoft Teams from starting automatically after installation** Group Policy setting.</span></span> <span data-ttu-id="dc224-180">您可以在使用者設定\Policy\系統管理範本\Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="dc224-180">You can find this policy setting in User Configuration\Policies\Administrative Templates\Microsoft Teams.</span></span> <span data-ttu-id="dc224-181">這是建議的方法，因為您可以根據組織的需求關閉或開啟策略設定。</span><span class="sxs-lookup"><span data-stu-id="dc224-181">This is the recommended method because you can turn off or turn on the policy setting according to your organization's needs.</span></span>

<span data-ttu-id="dc224-182">當您在安裝之前啟用此Teams設定時，Teams登入系統時，系統不會自動Windows。</span><span class="sxs-lookup"><span data-stu-id="dc224-182">When you enable this policy setting before Teams is installed, Teams doesn't start automatically when users log in to Windows.</span></span> <span data-ttu-id="dc224-183">使用者第一次Teams之後，Teams下次使用者登錄時，系統會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="dc224-183">After a user signs in to Teams for the first time, Teams starts automatically the next time the user logs in.</span></span>

<span data-ttu-id="dc224-184">若要深入瞭解，請參閱[使用群組原則防止Teams安裝後自動啟動。](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation)</span><span class="sxs-lookup"><span data-stu-id="dc224-184">To learn more, see [Use Group Policy to prevent Teams from starting automatically after installation](/deployoffice/teams-install#use-group-policy-to-prevent-microsoft-teams-from-starting-automatically-after-installation).</span></span>

> [!CAUTION]
> <span data-ttu-id="dc224-185">如果您已經部署 Teams，並想要設定此策略以停用 Teams 自動啟動，請先將群組原則設定設為您想要的值，然後根據每個使用者執行[Teams](scripts/powershell-script-teams-reset-autostart.md)自動啟動重設腳本。</span><span class="sxs-lookup"><span data-stu-id="dc224-185">If you've already deployed Teams and want to set this policy to disable Teams autostart, first set the Group Policy setting to the value you want, and then run the [Teams autostart reset script](scripts/powershell-script-teams-reset-autostart.md) on a per-user basis.</span></span>

### <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="dc224-186">停用 MSI 安裝程式的自動啟動</span><span class="sxs-lookup"><span data-stu-id="dc224-186">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="dc224-187">您可以使用 **OPTIONS="noAutoStart=true"** 參數來停用 MSI 安裝程式的自動啟動，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dc224-187">You can disable auto launch for the MSI installer by using the **OPTIONS="noAutoStart=true"** parameter as follows.</span></span>  

<span data-ttu-id="dc224-188">針對 32 位版本：</span><span class="sxs-lookup"><span data-stu-id="dc224-188">For the 32-bit version:</span></span>

```console
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="dc224-189">針對 64 位版本：</span><span class="sxs-lookup"><span data-stu-id="dc224-189">For the 64-bit version:</span></span>

```console
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true" ALLUSERS=1
```

<span data-ttu-id="dc224-190">當使用者以 msI Windows時Teams，系統即會使用 MSI 安裝Teams快捷方式會新增到使用者的桌面。</span><span class="sxs-lookup"><span data-stu-id="dc224-190">When a user logs in to Windows, Teams is installed with the MSI and a shortcut to start Teams is added to the user's desktop.</span></span> <span data-ttu-id="dc224-191">Teams使用者手動啟動Teams。</span><span class="sxs-lookup"><span data-stu-id="dc224-191">Teams won't start until the user manually starts Teams.</span></span> <span data-ttu-id="dc224-192">在使用者手動啟動Teams，Teams使用者每次登錄時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="dc224-192">After the user manually starts Teams, Teams automatically starts whenever the user logs in.</span></span>

<span data-ttu-id="dc224-193">請注意，這些範例也會使用 **ALLUSERS=1** 參數。</span><span class="sxs-lookup"><span data-stu-id="dc224-193">Note that these examples also use the **ALLUSERS=1** parameter.</span></span> <span data-ttu-id="dc224-194">當您設定此參數時，Teams Machine-Wide安裝程式會顯示在控制台中的程式和功能中，&應用程式Windows 設定所有電腦使用者的功能。</span><span class="sxs-lookup"><span data-stu-id="dc224-194">When you set this parameter, Teams Machine-Wide Installer appears in Programs and Features in Control Panel and in Apps & features in Windows Settings for all users of the computer.</span></span> <span data-ttu-id="dc224-195">然後所有使用者都可以卸載Teams，如果他們的電腦上有系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="dc224-195">All users can then uninstall Teams if they have admin credentials on the computer.</span></span>

> [!Note]
> <span data-ttu-id="dc224-196">如果您手動執行 MSI，請務必以較高的權限執行。</span><span class="sxs-lookup"><span data-stu-id="dc224-196">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="dc224-197">即使您以系統管理員執行，但不以較高的權限執行，安裝程式將無法設定停用自動啟動的選項。</span><span class="sxs-lookup"><span data-stu-id="dc224-197">Even if you run it as an administrator, without running it with elevated permissions, the installer won't be able to configure the option to disable auto start.</span></span>