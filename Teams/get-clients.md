---
title: 為 Microsoft 團隊取得用戶端
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 04/25/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: harij, rafarhi
localization_priority: Normal
search.appverid: MET150
description: 瞭解如何使用 Microsoft 團隊提供的各種用戶端，包括 web、桌面（Windows 和 Mac），以及行動裝置（Android 與 iOS）。
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: f8ea5133998e9d11e5ab070ffe66f7e719252ee5
ms.sourcegitcommit: 0dba0ad1f8f00415c6437cadabed0548ce3281b1
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 12/10/2019
ms.locfileid: "39919145"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="4b9b4-103">為 Microsoft 團隊取得用戶端</span><span class="sxs-lookup"><span data-stu-id="4b9b4-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="4b9b4-104">Microsoft 團隊擁有適用于桌面（Windows、Mac 和 Linux）、web 和 mobile （Android 和 iOS）的用戶端。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="4b9b4-105">這些用戶端都需要使用中的網際網路連線，而且不支援離線模式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="4b9b4-106">2018年11月29日，您將無法再使用 microsoft 網上商店提供的 Windows 10 S （預覽版） app Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="4b9b4-107">您現在可以改為在執行 Windows 10 S 模式的裝置上下載並安裝小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="4b9b4-108">若要下載桌面用戶端，請[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)移至。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="4b9b4-109">在執行 Windows 10 S 模式的裝置上，不提供團隊桌面用戶端的 MSI 組建。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="4b9b4-110">如需 Windows 10 S 模式的詳細資訊，請參閱[在 S 模式中簡介 Windows 10](https://www.microsoft.com/windows/s-mode)。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="4b9b4-111">桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="4b9b4-111">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="4b9b4-112">請觀看下列會話，瞭解 Windows 桌面用戶端的優點、如何規劃它，以及如何部署：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="4b9b4-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="4b9b4-113">Microsoft 團隊桌面用戶端是獨立的應用程式，也[可在 Office 365 專業增強版中](https://docs.microsoft.com/deployoffice/teams-install)取得。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="4b9b4-114">團隊可在 Windows （7 +）、32位和64位版本、macOS （10.10 +）及 Linux （ `.deb` `.rpm`格式）中取得。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="4b9b4-115">在 Windows 上，小組需要 .NET Framework 4.5 或更新版本;如果您沒有，團隊安裝程式將會提供將它安裝給您的人員。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="4b9b4-116">在 Linux 上，套件管理員（例如 apt 和 yum）會嘗試為您安裝任何需求。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="4b9b4-117">不過，如果不是這樣，在 Linux 上安裝小組之前，您將需要安裝任何已報告的需求。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="4b9b4-118">桌面用戶端可為小組會議、群組通話和私人一對一通話提供即時通訊支援（音訊、影片和內容共用）。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="4b9b4-119">如果使用者具有適當的本地許可權（在 PC 上安裝[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)團隊用戶端但在 Mac 上是必要的系統管理員許可權），則使用者可以直接從桌面用戶端下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="4b9b4-120">IT 管理員可以選擇其慣用的方法，將安裝檔案分發給組織中的電腦。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="4b9b4-121">一些範例包括 System Center Configuration Manager （Windows）或 Jamf Pro （macOS）。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="4b9b4-122">若要取得適用于 Windows 發佈的 MSI 套件，請參閱[使用 MSI 安裝 Microsoft 團隊](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="4b9b4-123">透過這些機制發佈用戶端只適用于 Microsoft 團隊用戶端的初始安裝，不適用於未來的更新。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="4b9b4-124">時間</span><span class="sxs-lookup"><span data-stu-id="4b9b4-124">Windows</span></span>

<span data-ttu-id="4b9b4-125">Windows 版 Microsoft 團隊安裝會提供32位與64位架構中的可下載的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="4b9b4-126">Microsoft 團隊的架構（32位與64位）不可知是已安裝的 Windows 與 Office 體系結構。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="4b9b4-127">Windows 用戶端會部署至位於使用者設定檔中的 [AppData] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="4b9b4-128">部署到使用者的本機設定檔後，就能在不需要提升許可權的情況下安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="4b9b4-129">Windows 用戶端會利用下列位置：</span><span class="sxs-lookup"><span data-stu-id="4b9b4-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="4b9b4-130">% LocalAppData%\\Microsoft\\團隊</span><span class="sxs-lookup"><span data-stu-id="4b9b4-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="4b9b4-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="4b9b4-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="4b9b4-132">% AppData%\\Microsoft\\團隊</span><span class="sxs-lookup"><span data-stu-id="4b9b4-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="4b9b4-133">% LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="4b9b4-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="4b9b4-134">當使用者第一次使用 Microsoft 團隊用戶端啟動通話時，可能會注意到 Windows 防火牆設定要求使用者允許通訊的警告。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="4b9b4-135">使用者可能會指示您略過這封郵件，因為通話會起作用，即使關閉警告也一樣。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows 安全性警報] 對話方塊的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="4b9b4-137">您也可以在關閉提示時選取 [取消] 來變更 Windows 防火牆設定。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="4b9b4-138">針對 TCP 和 UDP 通訊協定，會建立兩個針對團隊 .exe 的入站規則。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="4b9b4-139">版</span><span class="sxs-lookup"><span data-stu-id="4b9b4-139">Mac</span></span>

<span data-ttu-id="4b9b4-140">Mac 使用者可以使用 INSTALLER.PKG 安裝檔 macOS 電腦來安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="4b9b4-141">必須具備系統管理存取權才能安裝 Mac 用戶端。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="4b9b4-142">MacOS 用戶端已安裝至 [/Applications] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="4b9b4-143">使用 INSTALLER.PKG 檔案安裝團隊</span><span class="sxs-lookup"><span data-stu-id="4b9b4-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="4b9b4-144">從 [[團隊下載] 頁面](https://teams.microsoft.com/downloads)的 [ **Mac**] 底下，按一下 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="4b9b4-145">按兩下 INSTALLER.PKG 檔案。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="4b9b4-146">依照安裝精靈完成安裝。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="4b9b4-147">團隊將會安裝至/Applications 資料夾。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="4b9b4-148">這是整個電腦的安裝。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="4b9b4-149">在安裝期間，INSTALLER.PKG 會提示您輸入管理員認證。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="4b9b4-150">無論使用者是否為系統管理員，使用者都必須輸入管理員認證。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="4b9b4-151">如果使用者目前已安裝 .DMG 的團隊，而想要將它取代為 INSTALLER.PKG 安裝，使用者應該：</span><span class="sxs-lookup"><span data-stu-id="4b9b4-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="4b9b4-152">結束團隊 app。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="4b9b4-153">卸載 [團隊] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="4b9b4-154">安裝 INSTALLER.PKG 檔案。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-154">Install the PKG file.</span></span>

<span data-ttu-id="4b9b4-155">IT 管理員可以使用小組的 managed 部署來將安裝檔案發佈到其組織中的所有 Mac，例如 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="4b9b4-156">如果您在安裝 INSTALLER.PKG 時遇到問題，請告訴我們。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="4b9b4-157">在本文結尾的 [**意見**反應] 區段中，按一下 [**產品意見**反應]。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="4b9b4-158">Linux</span><span class="sxs-lookup"><span data-stu-id="4b9b4-158">Linux</span></span>

<span data-ttu-id="4b9b4-159">使用者將能夠安裝原生 Linux 套件`.deb`及`.rpm`格式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>
<span data-ttu-id="4b9b4-160">安裝 DEB 或 RPM 套件時會自動安裝套件儲存庫</span><span class="sxs-lookup"><span data-stu-id="4b9b4-160">Installing the DEB or RPM package will automatically install the package repository</span></span>
- <span data-ttu-id="4b9b4-161">DEB`https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="4b9b4-161">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="4b9b4-162">RPM`https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="4b9b4-162">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span> 

<span data-ttu-id="4b9b4-163">使用系統的套件管理員來啟用自動更新的簽名金鑰會自動安裝。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-163">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="4b9b4-164">不過，您也可以在以下網址找到：https://packages.microsoft.com/keys/microsoft.asc)（。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-164">However, it can also be found at: (https://packages.microsoft.com/keys/microsoft.asc).</span></span> <span data-ttu-id="4b9b4-165">Microsoft 團隊每月都會隨附，而且如果儲存庫已正確安裝，系統套件管理員就會以與系統中其他套件相同的方式處理自動更新。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-165">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="4b9b4-166">如果您發現錯誤，請使用`Report a Problem`用戶端中的 [從] 進行提交。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-166">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="4b9b4-167">如有已知問題，請參閱[已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-167">For known issues, see [Known Issues](Known-issues.md).</span></span>
> <span data-ttu-id="4b9b4-168">對於 Linux 版團隊支援，您可以使用（Microsoft Q&A） [https://docs.microsoft.com/answers/topics/teams.html] 上的 linux 論壇支援頻道。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-168">For Teams for Linux support you can use the (Linux forum support channel on Microsoft Q&A)[https://docs.microsoft.com/answers/topics/teams.html].</span></span> <span data-ttu-id="4b9b4-169">在張貼問題時， `teams-linux`請務必使用標記。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-169">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="4b9b4-170">使用 DEB 套件安裝團隊</span><span class="sxs-lookup"><span data-stu-id="4b9b4-170">Install Teams using DEB package</span></span>

1. <span data-ttu-id="4b9b4-171">從https://aka.ms/getteams下載套件。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-171">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="4b9b4-172">（Linux 用戶端在有限預覽中，即將啟動。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-172">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="4b9b4-173">如果您在 [下載] 頁面上沒有看到 Linux 用戶端，則它尚未啟動。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-173">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="4b9b4-174">使用下列其中一項進行安裝：</span><span class="sxs-lookup"><span data-stu-id="4b9b4-174">Install using one of the following:</span></span>  
    - <span data-ttu-id="4b9b4-175">開啟相關的套件管理工具，並完成自行引導的 Linux app 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-175">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="4b9b4-176">或者，如果您喜歡 [終端]，請輸入：`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="4b9b4-176">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="4b9b4-177">您可以透過 [活動] 或 [透過終端] `Teams`啟動小組，只要輸入即可。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-177">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="4b9b4-178">使用 RPM 套件安裝團隊</span><span class="sxs-lookup"><span data-stu-id="4b9b4-178">Install Teams using RPM package</span></span>

1. <span data-ttu-id="4b9b4-179">從https://aka.ms/getteams下載套件。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-179">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="4b9b4-180">（Linux 用戶端在有限預覽中，即將啟動。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-180">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="4b9b4-181">如果您在 [下載] 頁面上沒有看到 Linux 用戶端，則它尚未啟動。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-181">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="4b9b4-182">使用下列其中一項進行安裝：</span><span class="sxs-lookup"><span data-stu-id="4b9b4-182">Install using one of the following:</span></span>
    - <span data-ttu-id="4b9b4-183">開啟相關的套件管理工具，並完成自行引導的 Linux app 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-183">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="4b9b4-184">或者，如果您喜歡 [終端]，請輸入：`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="4b9b4-184">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="4b9b4-185">您可以透過 [活動] 或 [透過終端] `Teams`啟動小組，只要輸入即可。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-185">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

## <a name="web-client"></a><span data-ttu-id="4b9b4-186">網頁用戶端</span><span class="sxs-lookup"><span data-stu-id="4b9b4-186">Web client</span></span> 

<span data-ttu-id="4b9b4-187">Web 用戶端（[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)）是一種完整的功能用戶端，可在各種不同的瀏覽器中使用。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-187">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="4b9b4-188">網頁用戶端支援使用 webRTC 進行通話與會議，因此在網頁瀏覽器中不需要使用外掛程式或下載來執行團隊。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-188">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="4b9b4-189">瀏覽器必須設定為允許協力廠商 cookie。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-189">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="4b9b4-190">網頁用戶端會在連線時執行瀏覽器[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)版本檢測。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-190">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="4b9b4-191">如果偵測到不受支援的瀏覽器版本，它會封鎖網頁介面的存取權，並建議使用者下載桌面用戶端或行動裝置 app。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-191">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="4b9b4-192">行動用戶端</span><span class="sxs-lookup"><span data-stu-id="4b9b4-192">Mobile clients</span></span>

<span data-ttu-id="4b9b4-193">Microsoft 團隊行動應用程式適用于 Android 和 iOS，且適用于參與聊天交談和允許對等音訊通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-193">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="4b9b4-194">若是行動裝置應用程式，請移至相關的行動裝置商店 [Google Play] 和 [Apple App Store]。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-194">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="4b9b4-195">Windows Phone 應用程式已于2018年7月20日停用，可能無法再運作。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-195">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="4b9b4-196">Microsoft 團隊行動裝置 app 支援的行動平臺如下：</span><span class="sxs-lookup"><span data-stu-id="4b9b4-196">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="4b9b4-197">**Android**：5.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4b9b4-197">**Android**: 5.0 or later</span></span>

-   <span data-ttu-id="4b9b4-198">**iOS**：10.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="4b9b4-198">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="4b9b4-199">行動裝置版必須提供給公眾，小組才能如期運作。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-199">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="4b9b4-200">行動應用程式只會透過各個行動平臺的 app store 進行散佈與更新。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-200">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="4b9b4-201">Microsoft 不支援透過 MDM 或側載來傳播行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-201">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="4b9b4-202">在支援的行動平臺上安裝行動應用程式後，如果版本在目前發行的三個月內，就會支援小組行動應用程式本身。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-202">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![描述決策點的圖示](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="4b9b4-204">決策點</span><span class="sxs-lookup"><span data-stu-id="4b9b4-204">Decision Point</span></span>         |<span data-ttu-id="4b9b4-205">是否有任何限制讓使用者在他們的裝置上安裝適當的 Microsoft 團隊用戶端？</span><span class="sxs-lookup"><span data-stu-id="4b9b4-205">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![描繪後續步驟的圖示](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="4b9b4-207">後續步驟</span><span class="sxs-lookup"><span data-stu-id="4b9b4-207">Next Steps</span></span>         |<span data-ttu-id="4b9b4-208">如果您的組織限制軟體安裝，請確定此程式與 Microsoft 團隊相容。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-208">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="4b9b4-209">注意：電腦用戶端安裝不需要系統管理員許可權，但在 Mac 上安裝則是必要的。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-209">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="4b9b4-210">用戶端更新管理</span><span class="sxs-lookup"><span data-stu-id="4b9b4-210">Client update management</span></span>

<span data-ttu-id="4b9b4-211">用戶端目前會自動由 Microsoft 團隊服務更新，不需要 IT 管理員干預。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-211">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="4b9b4-212">如果有可用的更新，用戶端會自動下載更新，當 app 在一段時間內有 idled 時，更新程式就會開始。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-212">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="4b9b4-213">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="4b9b4-213">Client-side configurations</span></span>

<span data-ttu-id="4b9b4-214">目前，沒有任何受支援的選項可用來透過租使用者管理員、PowerShell、群組原則物件或登錄設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-214">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="4b9b4-215">通知設定</span><span class="sxs-lookup"><span data-stu-id="4b9b4-215">Notification settings</span></span>

<span data-ttu-id="4b9b4-216">目前沒有可供 IT 系統管理員設定用戶端通知設定的選項。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-216">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="4b9b4-217">所有通知選項都是由使用者設定。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-217">All notification options are set by the user.</span></span> <span data-ttu-id="4b9b4-218">下圖概述預設用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-218">The figure below outlines the default client settings.</span></span>

![通知設定的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="4b9b4-220">範例 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="4b9b4-220">Sample PowerShell Script</span></span>

<span data-ttu-id="4b9b4-221">這個範例腳本（需要在已提升許可權的管理員帳戶的內容中執行用戶端電腦）會針對在 c:\users. 中找到的每個使用者資料夾，建立新的入站防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-221">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="4b9b4-222">當團隊找到這個規則時，會防止團隊應用程式在使用者第一次從小組通話時提示使用者建立防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="4b9b4-222">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```powershell
<#
.SYNOPSIS
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($null -ne $users) {
    foreach ($user in $users) {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath) {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue)) {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}
```
