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
ms.openlocfilehash: 6f7a1cd3002135e2327ca4953ddfbb5b0393242d
ms.sourcegitcommit: 15fe483079847d24869e325eead35f252da8c7dd
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 11/06/2019
ms.locfileid: "37979696"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="99946-103">為 Microsoft 團隊取得用戶端</span><span class="sxs-lookup"><span data-stu-id="99946-103">Get clients for Microsoft Teams</span></span> 


<span data-ttu-id="99946-104">Microsoft 團隊擁有適用于桌面（Windows、Mac 和 Linux）、web 和 mobile （Android 和 iOS）的用戶端。</span><span class="sxs-lookup"><span data-stu-id="99946-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="99946-105">這些用戶端都需要使用中的網際網路連線，而且不支援離線模式。</span><span class="sxs-lookup"><span data-stu-id="99946-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="99946-106">2018年11月29日，您將無法再使用 microsoft 網上商店提供的 Windows 10 S （預覽版） app Microsoft 團隊。</span><span class="sxs-lookup"><span data-stu-id="99946-106">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="99946-107">您現在可以改為在執行 Windows 10 S 模式的裝置上下載並安裝小組桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="99946-107">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="99946-108">若要下載桌面用戶端，請[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)移至。</span><span class="sxs-lookup"><span data-stu-id="99946-108">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754).</span></span> <span data-ttu-id="99946-109">在執行 Windows 10 S 模式的裝置上，不提供團隊桌面用戶端的 MSI 組建。</span><span class="sxs-lookup"><span data-stu-id="99946-109">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="99946-110">如需 Windows 10 S 模式的詳細資訊，請參閱[在 S 模式中簡介 Windows 10](https://www.microsoft.com/windows/s-mode)。</span><span class="sxs-lookup"><span data-stu-id="99946-110">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span> 

## <a name="desktop-client"></a><span data-ttu-id="99946-111">桌面用戶端</span><span class="sxs-lookup"><span data-stu-id="99946-111">Desktop client</span></span>

> [!Tip]
> <span data-ttu-id="99946-112">請觀看下列會話，瞭解 Windows 桌面用戶端的優點、如何規劃它，以及如何部署：[團隊 Windows 桌面用戶端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="99946-112">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="99946-113">Microsoft 團隊桌面用戶端是獨立的應用程式，也[可在 Office 365 專業增強版中](https://docs.microsoft.com/deployoffice/teams-install)取得。</span><span class="sxs-lookup"><span data-stu-id="99946-113">The Microsoft Teams desktop client is a standalone application and is also [available in Office 365 ProPlus](https://docs.microsoft.com/deployoffice/teams-install).</span></span> <span data-ttu-id="99946-114">團隊可在 Windows （7 +）、32位和64位版本、macOS （10.10 +）及 Linux （ `.deb` `.rpm`格式）中取得。</span><span class="sxs-lookup"><span data-stu-id="99946-114">Teams is available for Windows (7+), both 32-bit and 64-bit versions, macOS (10.10+), and Linux (in `.deb` and `.rpm` formats.).</span></span> <span data-ttu-id="99946-115">在 Windows 上，小組需要 .NET Framework 4.5 或更新版本;如果您沒有，團隊安裝程式將會提供將它安裝給您的人員。</span><span class="sxs-lookup"><span data-stu-id="99946-115">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="99946-116">在 Linux 上，套件管理員（例如 apt 和 yum）會嘗試為您安裝任何需求。</span><span class="sxs-lookup"><span data-stu-id="99946-116">On Linux, package managers such as apt and yum will try to install any requirements for you.</span></span> <span data-ttu-id="99946-117">不過，如果不是這樣，在 Linux 上安裝小組之前，您將需要安裝任何已報告的需求。</span><span class="sxs-lookup"><span data-stu-id="99946-117">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="99946-118">桌面用戶端可為小組會議、群組通話和私人一對一通話提供即時通訊支援（音訊、影片和內容共用）。</span><span class="sxs-lookup"><span data-stu-id="99946-118">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="99946-119">如果使用者具有適當的本地許可權（在 PC 上安裝[https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754)團隊用戶端但在 Mac 上是必要的系統管理員許可權），則使用者可以直接從桌面用戶端下載並安裝。</span><span class="sxs-lookup"><span data-stu-id="99946-119">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

<span data-ttu-id="99946-120">IT 管理員可以選擇其慣用的方法，將安裝檔案分發給組織中的電腦。</span><span class="sxs-lookup"><span data-stu-id="99946-120">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="99946-121">一些範例包括 System Center Configuration Manager （Windows）或 Jamf Pro （macOS）。</span><span class="sxs-lookup"><span data-stu-id="99946-121">Some examples include System Center Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="99946-122">若要取得適用于 Windows 發佈的 MSI 套件，請參閱[使用 MSI 安裝 Microsoft 團隊](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="99946-122">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>  

> [!NOTE]
> <span data-ttu-id="99946-123">透過這些機制發佈用戶端只適用于 Microsoft 團隊用戶端的初始安裝，不適用於未來的更新。</span><span class="sxs-lookup"><span data-stu-id="99946-123">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="99946-124">時間</span><span class="sxs-lookup"><span data-stu-id="99946-124">Windows</span></span>

<span data-ttu-id="99946-125">Windows 版 Microsoft 團隊安裝會提供32位與64位架構中的可下載的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="99946-125">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="99946-126">Microsoft 團隊的架構（32位與64位）不可知是已安裝的 Windows 與 Office 體系結構。</span><span class="sxs-lookup"><span data-stu-id="99946-126">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="99946-127">Windows 用戶端會部署至位於使用者設定檔中的 [AppData] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="99946-127">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="99946-128">部署到使用者的本機設定檔後，就能在不需要提升許可權的情況下安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="99946-128">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="99946-129">Windows 用戶端會利用下列位置：</span><span class="sxs-lookup"><span data-stu-id="99946-129">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="99946-130">% LocalAppData%\\Microsoft\\團隊</span><span class="sxs-lookup"><span data-stu-id="99946-130">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="99946-131">% LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="99946-131">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="99946-132">% AppData%\\Microsoft\\團隊</span><span class="sxs-lookup"><span data-stu-id="99946-132">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="99946-133">% LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="99946-133">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="99946-134">當使用者第一次使用 Microsoft 團隊用戶端啟動通話時，可能會注意到 Windows 防火牆設定要求使用者允許通訊的警告。</span><span class="sxs-lookup"><span data-stu-id="99946-134">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="99946-135">使用者可能會指示您略過這封郵件，因為通話會起作用，即使關閉警告也一樣。</span><span class="sxs-lookup"><span data-stu-id="99946-135">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![[Windows 安全性警報] 對話方塊的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="99946-137">您也可以在關閉提示時選取 [取消] 來變更 Windows 防火牆設定。</span><span class="sxs-lookup"><span data-stu-id="99946-137">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="99946-138">針對 TCP 和 UDP 通訊協定，會建立兩個針對團隊 .exe 的入站規則。</span><span class="sxs-lookup"><span data-stu-id="99946-138">Two inbound rules for teams.exe will be created with Block action for both TCP and UDP protocols.</span></span>

### <a name="mac"></a><span data-ttu-id="99946-139">版</span><span class="sxs-lookup"><span data-stu-id="99946-139">Mac</span></span>

<span data-ttu-id="99946-140">Mac 使用者可以使用 INSTALLER.PKG 安裝檔 macOS 電腦來安裝團隊。</span><span class="sxs-lookup"><span data-stu-id="99946-140">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="99946-141">必須具備系統管理存取權才能安裝 Mac 用戶端。</span><span class="sxs-lookup"><span data-stu-id="99946-141">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="99946-142">MacOS 用戶端已安裝至 [/Applications] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="99946-142">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="99946-143">使用 INSTALLER.PKG 檔案安裝團隊</span><span class="sxs-lookup"><span data-stu-id="99946-143">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="99946-144">從 [[團隊下載] 頁面](https://teams.microsoft.com/downloads)的 [ **Mac**] 底下，按一下 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="99946-144">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="99946-145">按兩下 INSTALLER.PKG 檔案。</span><span class="sxs-lookup"><span data-stu-id="99946-145">Double click the PKG file.</span></span>
3. <span data-ttu-id="99946-146">依照安裝精靈完成安裝。</span><span class="sxs-lookup"><span data-stu-id="99946-146">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="99946-147">團隊將會安裝至/Applications 資料夾。</span><span class="sxs-lookup"><span data-stu-id="99946-147">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="99946-148">這是整個電腦的安裝。</span><span class="sxs-lookup"><span data-stu-id="99946-148">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="99946-149">在安裝期間，INSTALLER.PKG 會提示您輸入管理員認證。</span><span class="sxs-lookup"><span data-stu-id="99946-149">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="99946-150">無論使用者是否為系統管理員，使用者都必須輸入管理員認證。</span><span class="sxs-lookup"><span data-stu-id="99946-150">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="99946-151">如果使用者目前已安裝 .DMG 的團隊，而想要將它取代為 INSTALLER.PKG 安裝，使用者應該：</span><span class="sxs-lookup"><span data-stu-id="99946-151">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="99946-152">結束團隊 app。</span><span class="sxs-lookup"><span data-stu-id="99946-152">Exit the Teams app.</span></span>
2. <span data-ttu-id="99946-153">卸載 [團隊] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="99946-153">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="99946-154">安裝 INSTALLER.PKG 檔案。</span><span class="sxs-lookup"><span data-stu-id="99946-154">Install the PKG file.</span></span>

<span data-ttu-id="99946-155">IT 管理員可以使用小組的 managed 部署來將安裝檔案發佈到其組織中的所有 Mac，例如 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="99946-155">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="99946-156">如果您在安裝 INSTALLER.PKG 時遇到問題，請告訴我們。</span><span class="sxs-lookup"><span data-stu-id="99946-156">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="99946-157">在本文結尾的 [**意見**反應] 區段中，按一下 [**產品意見**反應]。</span><span class="sxs-lookup"><span data-stu-id="99946-157">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="99946-158">Linux</span><span class="sxs-lookup"><span data-stu-id="99946-158">Linux</span></span>

<span data-ttu-id="99946-159">使用者將能夠安裝原生 Linux 套件`.deb`及`.rpm`格式。</span><span class="sxs-lookup"><span data-stu-id="99946-159">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span>

> [!NOTE] 
> <span data-ttu-id="99946-160">Linux 用戶端上的團隊可在有限的預覽中取得。</span><span class="sxs-lookup"><span data-stu-id="99946-160">The Teams on Linux client is available in limited preview.</span></span> <span data-ttu-id="99946-161">在用戶端`Report a Problem`中使用從用戶端提交的錯誤。</span><span class="sxs-lookup"><span data-stu-id="99946-161">Submit bugs using `Report a Problem` from within the client.</span></span> <span data-ttu-id="99946-162">如有已知問題，請參閱[已知問題](Known-issues.md)。</span><span class="sxs-lookup"><span data-stu-id="99946-162">For known issues, see [Known Issues](Known-issues.md).</span></span>

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="99946-163">使用 DEB 套件安裝團隊</span><span class="sxs-lookup"><span data-stu-id="99946-163">Install Teams using DEB package</span></span>

1. <span data-ttu-id="99946-164">從https://aka.ms/getteams下載套件。</span><span class="sxs-lookup"><span data-stu-id="99946-164">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="99946-165">（Linux 用戶端在有限預覽中，即將啟動。</span><span class="sxs-lookup"><span data-stu-id="99946-165">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="99946-166">如果您在 [下載] 頁面上沒有看到 Linux 用戶端，則它尚未啟動。</span><span class="sxs-lookup"><span data-stu-id="99946-166">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="99946-167">使用下列其中一項進行安裝：</span><span class="sxs-lookup"><span data-stu-id="99946-167">Install using one of the following:</span></span>  
    - <span data-ttu-id="99946-168">開啟相關的套件管理工具，並完成自行引導的 Linux app 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="99946-168">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="99946-169">或者，如果您喜歡 [終端]，請輸入：`sudo apt install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="99946-169">Or if you love Terminal, type: `sudo apt install **teams download file**`</span></span>

<span data-ttu-id="99946-170">您可以透過 [活動] 或 [透過終端] `Teams`啟動小組，只要輸入即可。</span><span class="sxs-lookup"><span data-stu-id="99946-170">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span> 

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="99946-171">使用 RPM 套件安裝團隊</span><span class="sxs-lookup"><span data-stu-id="99946-171">Install Teams using RPM package</span></span>

1. <span data-ttu-id="99946-172">從https://aka.ms/getteams下載套件。</span><span class="sxs-lookup"><span data-stu-id="99946-172">Download the package from https://aka.ms/getteams.</span></span> <span data-ttu-id="99946-173">（Linux 用戶端在有限預覽中，即將啟動。</span><span class="sxs-lookup"><span data-stu-id="99946-173">(The Linux client is in limited preview and will launch soon.</span></span> <span data-ttu-id="99946-174">如果您在 [下載] 頁面上沒有看到 Linux 用戶端，則它尚未啟動。</span><span class="sxs-lookup"><span data-stu-id="99946-174">If you don't see the Linux client on the downloads page then it has not launched yet.)</span></span>
2. <span data-ttu-id="99946-175">使用下列其中一項進行安裝：</span><span class="sxs-lookup"><span data-stu-id="99946-175">Install using one of the following:</span></span>
    - <span data-ttu-id="99946-176">開啟相關的套件管理工具，並完成自行引導的 Linux app 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="99946-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="99946-177">或者，如果您喜歡 [終端]，請輸入：`sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="99946-177">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="99946-178">您可以透過 [活動] 或 [透過終端] `Teams`啟動小組，只要輸入即可。</span><span class="sxs-lookup"><span data-stu-id="99946-178">You can launch Teams via Activities or via Terminal by typing `Teams`.</span></span>

## <a name="web-client"></a><span data-ttu-id="99946-179">網頁用戶端</span><span class="sxs-lookup"><span data-stu-id="99946-179">Web client</span></span> 

<span data-ttu-id="99946-180">Web 用戶端（[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)）是一種完整的功能用戶端，可在各種不同的瀏覽器中使用。</span><span class="sxs-lookup"><span data-stu-id="99946-180">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="99946-181">網頁用戶端支援使用 webRTC 進行通話與會議，因此在網頁瀏覽器中不需要使用外掛程式或下載來執行團隊。</span><span class="sxs-lookup"><span data-stu-id="99946-181">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="99946-182">瀏覽器必須設定為允許協力廠商 cookie。</span><span class="sxs-lookup"><span data-stu-id="99946-182">The browser must be configured to allow third-party cookies.</span></span> 

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="99946-183">網頁用戶端會在連線時執行瀏覽器[https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)版本檢測。</span><span class="sxs-lookup"><span data-stu-id="99946-183">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="99946-184">如果偵測到不受支援的瀏覽器版本，它會封鎖網頁介面的存取權，並建議使用者下載桌面用戶端或行動裝置 app。</span><span class="sxs-lookup"><span data-stu-id="99946-184">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="99946-185">行動用戶端</span><span class="sxs-lookup"><span data-stu-id="99946-185">Mobile clients</span></span>

<span data-ttu-id="99946-186">Microsoft 團隊行動應用程式適用于 Android 和 iOS，且適用于參與聊天交談和允許對等音訊通話的使用者。</span><span class="sxs-lookup"><span data-stu-id="99946-186">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="99946-187">若是行動裝置應用程式，請移至相關的行動裝置商店 [Google Play] 和 [Apple App Store]。</span><span class="sxs-lookup"><span data-stu-id="99946-187">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="99946-188">Windows Phone 應用程式已于2018年7月20日停用，可能無法再運作。</span><span class="sxs-lookup"><span data-stu-id="99946-188">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span> 

<span data-ttu-id="99946-189">Microsoft 團隊行動裝置 app 支援的行動平臺如下：</span><span class="sxs-lookup"><span data-stu-id="99946-189">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

-   <span data-ttu-id="99946-190">**Android**：4.4 或更新版本</span><span class="sxs-lookup"><span data-stu-id="99946-190">**Android**: 4.4 or later</span></span>

-   <span data-ttu-id="99946-191">**iOS**：10.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="99946-191">**iOS**: 10.0 or later</span></span>

> [!NOTE]
> <span data-ttu-id="99946-192">行動裝置版必須提供給公眾，小組才能如期運作。</span><span class="sxs-lookup"><span data-stu-id="99946-192">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="99946-193">行動應用程式只會透過各個行動平臺的 app store 進行散佈與更新。</span><span class="sxs-lookup"><span data-stu-id="99946-193">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="99946-194">Microsoft 不支援透過 MDM 或側載來傳播行動應用程式。</span><span class="sxs-lookup"><span data-stu-id="99946-194">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="99946-195">在支援的行動平臺上安裝行動應用程式後，如果版本在目前發行的三個月內，就會支援小組行動應用程式本身。</span><span class="sxs-lookup"><span data-stu-id="99946-195">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>


| | | |
|---------|---------|---------|
|![描述決策點的圖示](media/Get_clients_for_Microsoft_Teams_image4.png)      |<span data-ttu-id="99946-197">決策點</span><span class="sxs-lookup"><span data-stu-id="99946-197">Decision Point</span></span>         |<span data-ttu-id="99946-198">是否有任何限制讓使用者在他們的裝置上安裝適當的 Microsoft 團隊用戶端？</span><span class="sxs-lookup"><span data-stu-id="99946-198">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>         |
|![描繪後續步驟的圖示](media/Get_clients_for_Microsoft_Teams_image5.png)     |<span data-ttu-id="99946-200">後續步驟</span><span class="sxs-lookup"><span data-stu-id="99946-200">Next Steps</span></span>         |<span data-ttu-id="99946-201">如果您的組織限制軟體安裝，請確定此程式與 Microsoft 團隊相容。</span><span class="sxs-lookup"><span data-stu-id="99946-201">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="99946-202">注意：電腦用戶端安裝不需要系統管理員許可權，但在 Mac 上安裝則是必要的。</span><span class="sxs-lookup"><span data-stu-id="99946-202">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>         |

## <a name="client-update-management"></a><span data-ttu-id="99946-203">用戶端更新管理</span><span class="sxs-lookup"><span data-stu-id="99946-203">Client update management</span></span>

<span data-ttu-id="99946-204">用戶端目前會自動由 Microsoft 團隊服務更新，不需要 IT 管理員干預。</span><span class="sxs-lookup"><span data-stu-id="99946-204">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="99946-205">如果有可用的更新，用戶端會自動下載更新，當 app 在一段時間內有 idled 時，更新程式就會開始。</span><span class="sxs-lookup"><span data-stu-id="99946-205">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="99946-206">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="99946-206">Client-side configurations</span></span>

<span data-ttu-id="99946-207">目前，沒有任何受支援的選項可用來透過租使用者管理員、PowerShell、群組原則物件或登錄設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="99946-207">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="99946-208">通知設定</span><span class="sxs-lookup"><span data-stu-id="99946-208">Notification settings</span></span>

<span data-ttu-id="99946-209">目前沒有可供 IT 系統管理員設定用戶端通知設定的選項。</span><span class="sxs-lookup"><span data-stu-id="99946-209">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="99946-210">所有通知選項都是由使用者設定。</span><span class="sxs-lookup"><span data-stu-id="99946-210">All notification options are set by the user.</span></span> <span data-ttu-id="99946-211">下圖概述預設用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="99946-211">The figure below outlines the default client settings.</span></span>

![通知設定的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script"></a><span data-ttu-id="99946-213">範例 PowerShell 腳本</span><span class="sxs-lookup"><span data-stu-id="99946-213">Sample PowerShell Script</span></span>

<span data-ttu-id="99946-214">這個範例腳本（需要在已提升許可權的管理員帳戶的內容中執行用戶端電腦）會針對在 c:\users. 中找到的每個使用者資料夾，建立新的入站防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="99946-214">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="99946-215">當團隊找到這個規則時，會防止團隊應用程式在使用者第一次從小組通話時提示使用者建立防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="99946-215">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span> 

```

<#
.Synopsis
   Creates firewall rules for Teams.
.DESCRIPTION
   (c) Microsoft Corporation 2018. All rights reserved. Script provided as-is without any warranty of any kind. Use it freely at your own risks.
   Must be run with elevated permissions. Can be run as a GPO Computer Startup script, or as a Scheduled Task with elevated permissions. 
   The script will create a new inbound firewall rule for each user folder found in c:\users. 
   Requires PowerShell 3.0.
#>

#Requires -Version 3

$users = Get-ChildItem (Join-Path -Path $env:SystemDrive -ChildPath 'Users') -Exclude 'Public', 'ADMINI~*'
if ($users.Length -gt 0)
{
    foreach ($user in $users)
    {
        $progPath = Join-Path -Path $user.FullName -ChildPath "AppData\Local\Microsoft\Teams\Current\Teams.exe"
        if (Test-Path $progPath)
        {
            if (-not (Get-NetFirewallApplicationFilter -Program $progPath -ErrorAction SilentlyContinue))
            {
                $ruleName = "Teams.exe for user $($user.Name)"
                "UDP", "TCP" | ForEach-Object { New-NetFirewallRule -DisplayName $ruleName -Direction Inbound -Profile Domain -Program $progPath -Action Allow -Protocol $_ }
                Clear-Variable ruleName
            }
        }
        Clear-Variable progPath
    }
}

```
