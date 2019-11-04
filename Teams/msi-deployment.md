---
title: 透過 SCCM 使用 MSI 安裝 Microsoft 團隊
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
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0b80b82a89fc162e33263c784480f619dcd5cf32
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/01/2019
ms.locfileid: "37573371"
---
<a name="install-microsoft-teams-using-msi"></a><span data-ttu-id="60ffa-103">使用 MSI 安裝 Microsoft 團隊</span><span class="sxs-lookup"><span data-stu-id="60ffa-103">Install Microsoft Teams using MSI</span></span>
=================================

> [!Tip]
> <span data-ttu-id="60ffa-104">請觀看下列會話，瞭解 Windows 桌面用戶端的優點，以及如何進行規劃，以及部署方式：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="60ffa-104">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="60ffa-105">若要使用 System Center Configuration Manager，或群組原則，或適用于廣泛部署的任何協力廠商發佈機制，Microsoft 提供了 MSI 檔案（ [32 位](https://aka.ms/teams32bitmsi)與[64 位](https://aka.ms/teams64bitmsi)），管理員可以用來大量部署團隊以進行選取使用者或電腦。</span><span class="sxs-lookup"><span data-stu-id="60ffa-105">To use System Center Configuration Manager, or Group Policy, or any third-party distribution mechanisms for broad deployment, Microsoft has provided MSI files (both [32-bit](https://aka.ms/teams32bitmsi) and [64-bit](https://aka.ms/teams64bitmsi)) that admins can use for bulk deployment of Teams to select users or computers.</span></span> <span data-ttu-id="60ffa-106">系統管理員可以使用這些檔案來遠端部署團隊，讓使用者不需要手動下載團隊 app。</span><span class="sxs-lookup"><span data-stu-id="60ffa-106">Admins can use these files to remotely deploy Teams so that users do not have to manually download the Teams app.</span></span> <span data-ttu-id="60ffa-107">部署時，小組會自動啟動在該電腦上登入的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="60ffa-107">When deployed, Teams will auto launch for all users who sign in on that machine.</span></span> <span data-ttu-id="60ffa-108">（您可以在安裝應用程式後停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="60ffa-108">(You can disable auto launch after installing the app.</span></span> <span data-ttu-id="60ffa-109">[請參閱下文](#disable-auto-launch-for-the-msi-installer)。）我們建議您將套件部署到電腦，讓電腦的所有新使用者也能從這項部署獲益。</span><span class="sxs-lookup"><span data-stu-id="60ffa-109">[See below](#disable-auto-launch-for-the-msi-installer).) We recommend that you deploy the package to the computer, so all new users of the machine will also benefit from this deployment.</span></span> 

<span data-ttu-id="60ffa-110">團隊也可以包含在 Office 365 專業增強版的部署中。</span><span class="sxs-lookup"><span data-stu-id="60ffa-110">Teams can also be included with a deployment of Office 365 ProPlus.</span></span> <span data-ttu-id="60ffa-111">如需詳細資訊，請參閱[使用 Office 365 專業增強版部署 Microsoft 團隊](https://docs.microsoft.com/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="60ffa-111">For more information, see [Deploy Microsoft Teams with Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span>
 
> [!Note] 
> <span data-ttu-id="60ffa-112">若要深入瞭解 SCCM，請參閱[System Center Configuration Manager 簡介](https://docs.microsoft.com/sccm/core/understand/introduction)。</span><span class="sxs-lookup"><span data-stu-id="60ffa-112">To learn more about SCCM, see [Introduction to System Center Configuration Manager](https://docs.microsoft.com/sccm/core/understand/introduction).</span></span>

## <a name="deployment-procedure-recommended"></a><span data-ttu-id="60ffa-113">部署程式（建議使用）</span><span class="sxs-lookup"><span data-stu-id="60ffa-113">Deployment procedure (recommended)</span></span>
1. <span data-ttu-id="60ffa-114">取得最新套件。</span><span class="sxs-lookup"><span data-stu-id="60ffa-114">Retrieve the latest package.</span></span>
2. <span data-ttu-id="60ffa-115">使用 MSI 預先填入的預設值。</span><span class="sxs-lookup"><span data-stu-id="60ffa-115">Use the defaults prepopulated by the MSI.</span></span>
3. <span data-ttu-id="60ffa-116">如有可能，請部署到電腦。</span><span class="sxs-lookup"><span data-stu-id="60ffa-116">Deploy to computers when possible.</span></span>

## <a name="how-the-microsoft-teams-msi-package-works"></a><span data-ttu-id="60ffa-117">Microsoft 團隊 MSI 套件的運作方式</span><span class="sxs-lookup"><span data-stu-id="60ffa-117">How the Microsoft Teams MSI package works</span></span>

### <a name="pc-installation"></a><span data-ttu-id="60ffa-118">電腦安裝</span><span class="sxs-lookup"><span data-stu-id="60ffa-118">PC installation</span></span>

> [!Note] 
> <span data-ttu-id="60ffa-119">請參閱[VDI 安裝](#vdi-installation)，以取得如何將團隊部署到虛擬 DESKTOPINFRASTRUCTURE （VDI）環境的指導方針。</span><span class="sxs-lookup"><span data-stu-id="60ffa-119">See [VDI installation](#vdi-installation) for guidance on how to deploy Teams to a Virtual DesktopInfrastructure (VDI) environment.</span></span>

<span data-ttu-id="60ffa-120">[團隊 MSI] 會在程式檔案中放置安裝程式。</span><span class="sxs-lookup"><span data-stu-id="60ffa-120">The Teams MSI will place an installer in Program Files.</span></span> <span data-ttu-id="60ffa-121">每當使用者登入新的 Windows 使用者設定檔時，系統就會啟動安裝程式，並將 [小組] app 複本安裝在該使用者的 appdata 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="60ffa-121">Whenever a user signs into a new Windows User Profile, the installer will be launched and a copy of the Teams app will be installed in that user's appdata folder.</span></span> <span data-ttu-id="60ffa-122">如果使用者已在 appdata 資料夾中安裝 [團隊] 應用程式，MSI 安裝程式將會略過該使用者的程式。</span><span class="sxs-lookup"><span data-stu-id="60ffa-122">If a user already has the Teams app installed in the appdata folder, the MSI installer will skip the process for that user.</span></span>

<span data-ttu-id="60ffa-123">請勿使用 MSI 來部署更新，因為用戶端會在檢測到可從服務取得新版本時自動更新。</span><span class="sxs-lookup"><span data-stu-id="60ffa-123">Do not use the MSI to deploy updates, because the client will auto update when it detects a new version is available from the service.</span></span> <span data-ttu-id="60ffa-124">若要重新部署最新的安裝程式，請使用以下所述的重新部署 MSI 程式。</span><span class="sxs-lookup"><span data-stu-id="60ffa-124">To re-deploy the latest installer use the process of redeploying MSI described below.</span></span><span data-ttu-id="60ffa-125">如果您部署舊版的 MSI 套件，則用戶端可能會自動更新（在 VDI 環境中除外）。</span><span class="sxs-lookup"><span data-stu-id="60ffa-125"> If you deploy an older version of the MSI package, the client will auto-update (except in VDI environments) when possible for the user.</span></span> <span data-ttu-id="60ffa-126">如果部署的是較舊的版本，MSI 將觸發應用程式更新，讓使用者能夠使用團隊。</span><span class="sxs-lookup"><span data-stu-id="60ffa-126">If a very old version gets deployed, the MSI will trigger an app update before the user is able to use Teams.</span></span> 

> [!Important] 
> <span data-ttu-id="60ffa-127">我們不建議您變更預設安裝位置，因為這可能會中斷更新流程。</span><span class="sxs-lookup"><span data-stu-id="60ffa-127">We don't recommended that you change the default install locations, as this could break the update flow.</span></span> <span data-ttu-id="60ffa-128">如果版本太舊，最終會封鎖使用者存取服務。</span><span class="sxs-lookup"><span data-stu-id="60ffa-128">Having too old a version will eventually block users from accessing the service.</span></span> 

#### <a name="target-computer-requirements"></a><span data-ttu-id="60ffa-129">目的電腦需求</span><span class="sxs-lookup"><span data-stu-id="60ffa-129">Target computer requirements</span></span>

- <span data-ttu-id="60ffa-130">.NET framework 4.5 或更新版本</span><span class="sxs-lookup"><span data-stu-id="60ffa-130">.NET framework 4.5 or later</span></span>
- <span data-ttu-id="60ffa-131">Windows 7 或更新版本</span><span class="sxs-lookup"><span data-stu-id="60ffa-131">Windows 7 or later</span></span>
- <span data-ttu-id="60ffa-132">每個使用者設定檔 3 GB 的磁碟空間（建議使用）</span><span class="sxs-lookup"><span data-stu-id="60ffa-132">3 GB of disk space for each user profile (recommended)</span></span>

### <a name="vdi-installation"></a><span data-ttu-id="60ffa-133">VDI 安裝</span><span class="sxs-lookup"><span data-stu-id="60ffa-133">VDI installation</span></span>

<span data-ttu-id="60ffa-134">以下是部署團隊桌面應用程式的步驟。</span><span class="sxs-lookup"><span data-stu-id="60ffa-134">Here's the process to deploy the Teams desktop app.</span></span> <span data-ttu-id="60ffa-135">如需完整指南，請參閱[虛擬化桌面基礎結構的團隊](teams-for-vdi.md)。</span><span class="sxs-lookup"><span data-stu-id="60ffa-135">For complete guidance, see [Teams for Virtualized Desktop Infrastructure](teams-for-vdi.md).</span></span>

1. <span data-ttu-id="60ffa-136">根據環境，使用下列其中一個連結來下載團隊 MSI 套件。</span><span class="sxs-lookup"><span data-stu-id="60ffa-136">Download the Teams MSI package using one of the following links depending on the environment.</span></span> <span data-ttu-id="60ffa-137">我們建議使用64位作業系統的 VDI VM 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="60ffa-137">We recommend the 64-bit version for a VDI VM with a 64-bit operating system.</span></span>

    - [<span data-ttu-id="60ffa-138">32位版本</span><span class="sxs-lookup"><span data-stu-id="60ffa-138">32-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true)
    - [<span data-ttu-id="60ffa-139">64位版本</span><span class="sxs-lookup"><span data-stu-id="60ffa-139">64-bit version</span></span>](https://teams.microsoft.com/downloads/desktopurl?env=production&plat=windows&download=true&managedInstaller=true&arch=x64)

2. <span data-ttu-id="60ffa-140">執行下列命令，將 MSI 安裝到 VDI VM （或完成更新）。</span><span class="sxs-lookup"><span data-stu-id="60ffa-140">Run the following command to install the MSI to the VDI VM (or complete updating it).</span></span>

        msiexec /i <path_to_msi> /l*v <install_logfile_name> ALLUSER=1

    <span data-ttu-id="60ffa-141">這會將小組安裝到程式檔。</span><span class="sxs-lookup"><span data-stu-id="60ffa-141">This installs Teams to Program Files.</span></span> <span data-ttu-id="60ffa-142">此時，黃金影像設定就完成了。</span><span class="sxs-lookup"><span data-stu-id="60ffa-142">At this point, the golden image setup is complete.</span></span>

    <span data-ttu-id="60ffa-143">下次互動式登入會話會啟動團隊並要求認證。</span><span class="sxs-lookup"><span data-stu-id="60ffa-143">The next interactive logon session starts Teams and asks for credentials.</span></span> <span data-ttu-id="60ffa-144">請注意，在 VDI 上使用 ALLUSER 屬性來安裝小組時，不可能停用自動啟動小組。</span><span class="sxs-lookup"><span data-stu-id="60ffa-144">Note that it's not possible to disable auto-launch of Teams when installing Teams on VDI using the ALLUSER property.</span></span>

3. <span data-ttu-id="60ffa-145">執行下列命令以從 VDI VM 卸載 MSI （或準備更新）。</span><span class="sxs-lookup"><span data-stu-id="60ffa-145">Run the following command to uninstall the MSI from the VDI VM (or prepare for updating it).</span></span>

        msiexec /passive /x <path_to_msi> /l*v <uninstall_logfile_name>

    <span data-ttu-id="60ffa-146">這會從程式檔案中卸載小組。</span><span class="sxs-lookup"><span data-stu-id="60ffa-146">This uninstalls Teams from Program Files.</span></span>

## <a name="clean-up-and-redeployment-procedure"></a><span data-ttu-id="60ffa-147">清理及重新部署程式</span><span class="sxs-lookup"><span data-stu-id="60ffa-147">Clean up and redeployment procedure</span></span>

<span data-ttu-id="60ffa-148">如果使用者從使用者設定檔中移除團隊，MSI 安裝程式將會追蹤使用者已卸載小組應用程式，而且不會再安裝該使用者設定檔的小組。</span><span class="sxs-lookup"><span data-stu-id="60ffa-148">If a user uninstalls Teams from their User Profile, the MSI installer will track that the user has uninstalled the Teams app and no longer install Teams for that User Profile.</span></span> <span data-ttu-id="60ffa-149">若要在已卸載此使用者的特定電腦上重新部署團隊，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="60ffa-149">To redeploy Teams for this user on a particular computer where it was uninstalled, do the following:</span></span>

1. <span data-ttu-id="60ffa-150">針對每個使用者設定檔卸載已安裝的團隊 App。</span><span class="sxs-lookup"><span data-stu-id="60ffa-150">Uninstall Teams App installed for every user profile.</span></span> 
2. <span data-ttu-id="60ffa-151">卸載之後，以遞迴方式在%localappdata%\Microsoft\Teams\. 下刪除目錄</span><span class="sxs-lookup"><span data-stu-id="60ffa-151">After uninstall, delete directory recursively under %localappdata%\Microsoft\Teams\.</span></span>
3. <span data-ttu-id="60ffa-152">將 MSI 套件重新部署到該特定電腦。</span><span class="sxs-lookup"><span data-stu-id="60ffa-152">Redeploy the MSI package to that particular computer.</span></span>

> [!TIP] 
> <span data-ttu-id="60ffa-153">您可以使用我們的[Microsoft 團隊部署清理](scripts/Powershell-script-teams-deployment-clean-up.md)腳本，透過 SCCM 完成步驟1和2。</span><span class="sxs-lookup"><span data-stu-id="60ffa-153">You can use our [Microsoft Teams deployment clean up](scripts/Powershell-script-teams-deployment-clean-up.md) script to accomplish steps 1 and 2 via SCCM.</span></span>

## <a name="disable-auto-launch-for-the-msi-installer"></a><span data-ttu-id="60ffa-154">停用 MSI 安裝程式的自動啟動</span><span class="sxs-lookup"><span data-stu-id="60ffa-154">Disable auto launch for the MSI installer</span></span>

<span data-ttu-id="60ffa-155">MSI 的預設行為是在使用者登入後立即安裝團隊用戶端，然後自動啟動團隊。</span><span class="sxs-lookup"><span data-stu-id="60ffa-155">Default behavior of the MSI is to install the Teams client as soon as a user signs in and then automatically start Teams.</span></span> <span data-ttu-id="60ffa-156">您可以使用下列參數來修改此行為，如下所示：</span><span class="sxs-lookup"><span data-stu-id="60ffa-156">You can modify this behavior with the parameters below as follows:</span></span>

- <span data-ttu-id="60ffa-157">當使用者登入 Windows 時，系統會使用 MSI 安裝團隊</span><span class="sxs-lookup"><span data-stu-id="60ffa-157">When a user logs in into Windows, Teams will be installed with the MSI</span></span>
- <span data-ttu-id="60ffa-158">不過，小組用戶端將無法啟動，直到使用者手動開始團隊為止</span><span class="sxs-lookup"><span data-stu-id="60ffa-158">However, the Teams client will not start until the user has started Teams manually</span></span>
- <span data-ttu-id="60ffa-159">[開始] 團隊的快捷方式將會新增至使用者的桌面</span><span class="sxs-lookup"><span data-stu-id="60ffa-159">A shortcut to start Teams will be added on the desktop of the user</span></span>
- <span data-ttu-id="60ffa-160">手動開始之後，每次使用者登入時，小組就會自動啟動</span><span class="sxs-lookup"><span data-stu-id="60ffa-160">Once manually started, Teams will auto-start whenever the user logs in</span></span>

<span data-ttu-id="60ffa-161">針對32位版本</span><span class="sxs-lookup"><span data-stu-id="60ffa-161">For the 32-bit version</span></span>
```
msiexec /i Teams_windows.msi OPTIONS="noAutoStart=true"
```
<span data-ttu-id="60ffa-162">針對64位版本</span><span class="sxs-lookup"><span data-stu-id="60ffa-162">For the 64-bit version</span></span>
```
msiexec /i Teams_windows_x64.msi OPTIONS="noAutoStart=true"
```

> [!Note]
>  <span data-ttu-id="60ffa-163">如果您是手動執行 MSI，請務必以提升許可權執行。</span><span class="sxs-lookup"><span data-stu-id="60ffa-163">If you run the MSI manually, be sure to run it with elevated permissions.</span></span> <span data-ttu-id="60ffa-164">即使您是以系統管理員身分執行，而且不是以提升許可權執行，安裝程式也無法將選項設定為停用自動啟動。</span><span class="sxs-lookup"><span data-stu-id="60ffa-164">Even if you run it as an administrator, without running it with elevated permissions, the installer will not be able to configure the option to disable auto start.</span></span>
