---
title: 取得 Microsoft Teams 用戶端
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- m365initiative-deployteams
ms.reviewer: harij, rafarhi
localization_priority: Priority
search.appverid: MET150
description: 了解如何使用各種適用 Microsoft Teams 的用戶端，包括 Web、桌面 (Windows 和 Mac) 以及行動裝置 (Android 和 iOS)。
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8385e6721a24c3ad1bd320dd2f6e5e14091181b0
ms.sourcegitcommit: 616403037ddb2d44f06cd9b2eaa9da699b119ef8
ms.translationtype: HT
ms.contentlocale: zh-TW
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768222"
---
# <a name="get-clients-for-microsoft-teams"></a><span data-ttu-id="f5c72-103">取得 Microsoft Teams 用戶端</span><span class="sxs-lookup"><span data-stu-id="f5c72-103">Get clients for Microsoft Teams</span></span>

<span data-ttu-id="f5c72-104">Microsoft Teams 具有適用於 Web、桌面 (Windows、Mac 和 Linux) 及行動裝置 (Android 和 iOS) 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5c72-104">Microsoft Teams has clients available for desktop (Windows, Mac, and Linux), web, and mobile (Android and iOS).</span></span> <span data-ttu-id="f5c72-105">這些用戶端都需要使用有效的網際網路連線，且並不支援離線模式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-105">These clients all require an active internet connection and do not support an offline mode.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-106">如需有關不同平台上每個用戶端功能的詳細資訊，請參閱[依平台的 Teams 功能](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-106">For details about each clients' capabilities on different platforms, see [Teams features by platform](https://support.microsoft.com/office/teams-features-by-platform-debe7ff4-7db4-4138-b7d0-fcc276f392d3).</span></span>
>
> <span data-ttu-id="f5c72-107">2018 年 11 月 29 日起，您將無法再使用 Microsoft Store 提供的 Windows 10 S 版 Microsoft Teams (預覽版) 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-107">Effective November 29, 2018, you'll no longer be able to use the Microsoft Teams for Windows 10 S (Preview) app, available from the Microsoft Store.</span></span> <span data-ttu-id="f5c72-108">但是您現在可以在執行 Windows 10 S 模式的裝置上，下載並安裝 Teams 桌面版用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5c72-108">Instead, you can now download and install the Teams desktop client on devices running Windows 10 S mode.</span></span> <span data-ttu-id="f5c72-109">若要下載桌面版用戶端，請移至 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/p/?linkid=855754)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-109">To download the desktop client, go to [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/p/?linkid=855754).</span></span> <span data-ttu-id="f5c72-110">Teams 桌面版用戶端的 MSI 組建尚不適用於執行 Windows 10 S 模式的裝置。</span><span class="sxs-lookup"><span data-stu-id="f5c72-110">MSI builds of the Teams desktop client are not yet available for devices running Windows 10 S mode.</span></span>
>
> <span data-ttu-id="f5c72-111">如需有關 Windows 10 S 模式的詳細資訊，請參閱[引進 Windows 10 S 模式](https://www.microsoft.com/windows/s-mode)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-111">For more information about Windows 10 S mode, see [Introducing Windows 10 in S mode](https://www.microsoft.com/windows/s-mode).</span></span>

## <a name="desktop-client"></a><span data-ttu-id="f5c72-112">桌面版用戶端</span><span class="sxs-lookup"><span data-stu-id="f5c72-112">Desktop client</span></span>

> [!TIP]
> <span data-ttu-id="f5c72-113">請觀看下列工作階段，以了解 Windows 桌面版用戶端的優點、規劃方式及部署方式：[Teams 的 Windows 桌面版用戶端](https://aka.ms/teams-clients)</span><span class="sxs-lookup"><span data-stu-id="f5c72-113">Watch the following session to learn about the benefits of the Windows Desktop Client, how to plan for it, and how to deploy it: [Teams Windows Desktop Client](https://aka.ms/teams-clients)</span></span>

<span data-ttu-id="f5c72-114">Microsoft Teams 桌面版用戶端是獨立的應用程式，並且[可用於 Microsoft 365 Apps 企業版](/deployoffice/teams-install)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-114">The Microsoft Teams desktop client is a standalone application and is also [available in Microsoft 365 Apps for enterprise](/deployoffice/teams-install).</span></span> <span data-ttu-id="f5c72-115">Teams 適用於 32 位元和 64 位元版本的 Windows (8.1 或更新版本)、ARM 上適用於 Windows 10 的 ARM64 及 Windows Server (2012 R2 或更新版本)，也適用於 macOS 及 Linux (`.deb` 和 `.rpm` 格式)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-115">Teams is available for 32-bit and 64-bit versions of Windows (8.1 or later), ARM64 for Windows 10 on ARM, and Windows Server (2012 R2 or later), as well as for macOS and Linux (in `.deb` and `.rpm` formats).</span></span> <span data-ttu-id="f5c72-116">在 Windows 上，Teams 需要 .NET Framework 4.5 或更新版本；如果您沒有此元件，Teams 安裝程式將會為您安裝。</span><span class="sxs-lookup"><span data-stu-id="f5c72-116">On Windows, Teams requires .NET Framework 4.5 or later; the Teams installer will offer to install it for you if you don't have it.</span></span> <span data-ttu-id="f5c72-117">在 Linux 上，套件管理員 (例如 `apt` 和 `yum`) 會嘗試為您安裝任何需求。</span><span class="sxs-lookup"><span data-stu-id="f5c72-117">On Linux, package managers such as `apt` and `yum` will try to install any requirements for you.</span></span> <span data-ttu-id="f5c72-118">不過，如果套件管理員沒有這麼做，您必須先安裝所有回報的需求，然後再安裝 Linux 版 Teams。</span><span class="sxs-lookup"><span data-stu-id="f5c72-118">However, if they don't then you will need to install any reported requirements before installing Teams on Linux.</span></span>

<span data-ttu-id="f5c72-119">桌面版用戶端提供即時通訊支援 (音訊、視訊和內容共用)，可用於進行小組會議、群組通話和個人的一對一通話。</span><span class="sxs-lookup"><span data-stu-id="f5c72-119">The desktop clients provide real-time communications support (audio, video, and content sharing) for team meetings, group calling, and private one-on-one calls.</span></span>

<span data-ttu-id="f5c72-120">如果終端使用者擁有適當的本機權限 (在 PC 上安裝 Teams 用戶端不需要系統管理員權限，但在 Mac 上安裝則需要系統管理員權限)，他們可以直接從 [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) 下載和安裝桌面版用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5c72-120">Desktop clients can be downloaded and installed by end users directly from [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) if they have the appropriate local permissions (admin rights are not required to install the Teams client on a PC but are required on a Mac).</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-121">如需在 Chromebook 安裝 Teams 的詳細資訊，請參閱[如何在 Chromebook 應用程式安裝及執行 Microsoft Office](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-121">For more details about installing Teams on a Chromebook, please see [How to install and run Microsoft Office on a Chromebook](https://support.office.com/article/how-to-install-and-run-microsoft-office-on-a-chromebook-32f14a23-2c1a-4579-b973-d4b1d78561ad).</span></span>

<span data-ttu-id="f5c72-122">IT 系統管理員可以選擇其偏好的方式，將安裝檔案發佈到組織中的電腦。</span><span class="sxs-lookup"><span data-stu-id="f5c72-122">IT admins can choose their preferred method to distribute the installation files to computers in their organization.</span></span> <span data-ttu-id="f5c72-123">例如 Microsoft Endpoint Configuration Manager (Windows) 或 Jamf Pro (macOS)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-123">Some examples include Microsoft Endpoint Configuration Manager (Windows) or Jamf Pro (macOS).</span></span> <span data-ttu-id="f5c72-124">若要取得 Windows 發行版本的 MSI 套件，請參閱[使用 MSI 安裝 Microsoft Teams](msi-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-124">To get the MSI package for Windows distribution, see [Install Microsoft Teams using MSI](msi-deployment.md).</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-125">透過這些機制發佈的用戶端只適用於一開始的 Microsoft Team 用戶端安裝，不適用於未來的更新。</span><span class="sxs-lookup"><span data-stu-id="f5c72-125">Distribution of the client via these mechanisms is only for the initial installation of Microsoft Team clients and not for future updates.</span></span>

### <a name="windows"></a><span data-ttu-id="f5c72-126">Windows</span><span class="sxs-lookup"><span data-stu-id="f5c72-126">Windows</span></span>

<span data-ttu-id="f5c72-127">適用於 Windows 的 Microsoft Teams 安裝會提供 32 位元和 64 位元架構的可下載安裝程式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-127">The Microsoft Teams installation for Windows provides downloadable installers in 32-bit and 64-bit architecture.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-128">Microsoft Teams 的架構 (32 位元和 64 位元) 並不受限於已安裝的 Windows 和 Office 架構。</span><span class="sxs-lookup"><span data-stu-id="f5c72-128">The architecture (32-bit vs. 64-bit) of Microsoft Teams is agnostic to the architecture of Windows and Office that is installed.</span></span>

<span data-ttu-id="f5c72-129">Windows 用戶端會部署至使用者設定檔中的 [AppData] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f5c72-129">The Windows client is deployed to the AppData folder located in the user’s profile.</span></span> <span data-ttu-id="f5c72-130">部署至使用者的本機設定檔中，即可在不需要提高權限的情況下安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5c72-130">Deploying to the user’s local profile allows the client to be installed without requiring elevated rights.</span></span> <span data-ttu-id="f5c72-131">Windows 用戶端會利用下列位置：</span><span class="sxs-lookup"><span data-stu-id="f5c72-131">The Windows client leverages the following locations:</span></span>

- <span data-ttu-id="f5c72-132">%LocalAppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="f5c72-132">%LocalAppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="f5c72-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span><span class="sxs-lookup"><span data-stu-id="f5c72-133">%LocalAppData%\\Microsoft\\TeamsMeetingAddin</span></span>

- <span data-ttu-id="f5c72-134">%AppData%\\Microsoft\\Teams</span><span class="sxs-lookup"><span data-stu-id="f5c72-134">%AppData%\\Microsoft\\Teams</span></span>

- <span data-ttu-id="f5c72-135">%LocalAppData%\\SquirrelTemp</span><span class="sxs-lookup"><span data-stu-id="f5c72-135">%LocalAppData%\\SquirrelTemp</span></span>

<span data-ttu-id="f5c72-136">使用者第一次使用 Microsoft Teams 用戶端進行通話時，可能會注意到要求使用者允許通訊的 Windows 防火牆設定警告。</span><span class="sxs-lookup"><span data-stu-id="f5c72-136">When users initiate a call using the Microsoft Teams client for the first time, they might notice a warning with the Windows firewall settings that asks for users to allow communication.</span></span> <span data-ttu-id="f5c72-137">系統可能會指示使用者忽略這則訊息，因為即使忽略警告，您仍然能進行通話。</span><span class="sxs-lookup"><span data-stu-id="f5c72-137">Users might be instructed to ignore this message because the call will work, even when the warning is dismissed.</span></span>

![Windows 安全性警示對話方塊的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image3.png)

> [!NOTE]
> <span data-ttu-id="f5c72-139">即使您選取「取消」來忽略提示，Windows 防火牆設定仍會變更。</span><span class="sxs-lookup"><span data-stu-id="f5c72-139">Windows Firewall configuration will be altered even when the prompt is dismissed by selecting “Cancel”.</span></span> <span data-ttu-id="f5c72-140">針對 TCP 和 UDP 通訊協定，系統會為 teams.exe 建立包含允許動作的兩個輸入規則。</span><span class="sxs-lookup"><span data-stu-id="f5c72-140">Two inbound rules for teams.exe will be created with Allow action for both TCP and UDP protocols.</span></span>

<span data-ttu-id="f5c72-141">如果您想要防止 Teams 在使用者第一次從 Teams 進行呼叫時提示使用者建立防火牆規則，請使用以下的[範例 PowerShell 指令碼 - 輸入防火牆規則](#sample-powershell-script---inbound-firewall-rule)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-141">If you want to prevent Teams from prompting users to create firewall rules when the users make their first call from Teams, use the [Sample PowerShell script - inbound firewall rule](#sample-powershell-script---inbound-firewall-rule) below.</span></span>

### <a name="mac"></a><span data-ttu-id="f5c72-142">Mac</span><span class="sxs-lookup"><span data-stu-id="f5c72-142">Mac</span></span>

<span data-ttu-id="f5c72-143">Mac 使用者可以使用 macOS 電腦的 PKG 安裝檔來安裝 Teams。</span><span class="sxs-lookup"><span data-stu-id="f5c72-143">Mac users can install Teams by using a PKG installation file for macOS computers.</span></span> <span data-ttu-id="f5c72-144">安裝 Mac 用戶端必須具備系統管理存取權。</span><span class="sxs-lookup"><span data-stu-id="f5c72-144">Administrative access is required to install the Mac client.</span></span> <span data-ttu-id="f5c72-145">MacOS 用戶端會安裝至 /Applications 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f5c72-145">The macOS client is installed to the /Applications folder.</span></span>

#### <a name="install-teams-by-using-the-pkg-file"></a><span data-ttu-id="f5c72-146">使用 PKG 檔案來安裝 Teams</span><span class="sxs-lookup"><span data-stu-id="f5c72-146">Install Teams by using the PKG file</span></span>

1. <span data-ttu-id="f5c72-147">在 **Mac** 底下的 [Teams 下載頁面](https://teams.microsoft.com/downloads)中，按一下 [下載]。</span><span class="sxs-lookup"><span data-stu-id="f5c72-147">From the [Teams download page](https://teams.microsoft.com/downloads), under **Mac**, click **Download**.</span></span>
2. <span data-ttu-id="f5c72-148">按兩下 PKG 檔案。</span><span class="sxs-lookup"><span data-stu-id="f5c72-148">Double click the PKG file.</span></span>
3. <span data-ttu-id="f5c72-149">遵循安裝精靈來完成安裝。</span><span class="sxs-lookup"><span data-stu-id="f5c72-149">Follow the installation wizard to complete the installation.</span></span>
4. <span data-ttu-id="f5c72-150">Teams 將會安裝到 /Applications 資料夾。</span><span class="sxs-lookup"><span data-stu-id="f5c72-150">Teams will be installed to /Applications folder.</span></span> <span data-ttu-id="f5c72-151">這是全機器安裝。</span><span class="sxs-lookup"><span data-stu-id="f5c72-151">It is a machine-wide installation.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-152">在安裝期間，PKG 會提示您輸入系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f5c72-152">During the installation, the PKG will prompt for admin credentials.</span></span> <span data-ttu-id="f5c72-153">無論使用者是否為系統管理員，使用者都需要輸入系統管理員認證。</span><span class="sxs-lookup"><span data-stu-id="f5c72-153">The user needs to enter the admin credentials, regardless of whether or not the user is an admin.</span></span>

<span data-ttu-id="f5c72-154">如果使用者目前已具有 Teams 的 DMG 安裝，但想要將其取代為 PKG 安裝，使用者應該：</span><span class="sxs-lookup"><span data-stu-id="f5c72-154">If a user currently has a DMG installation of Teams and wants to replace it with the PKG installation, the user should:</span></span>

1. <span data-ttu-id="f5c72-155">結束 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-155">Exit the Teams app.</span></span>
2. <span data-ttu-id="f5c72-156">取消安裝 Teams 應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-156">Uninstall the Teams app.</span></span>
3. <span data-ttu-id="f5c72-157">安裝 PKG 檔案。</span><span class="sxs-lookup"><span data-stu-id="f5c72-157">Install the PKG file.</span></span>

<span data-ttu-id="f5c72-158">IT 系統管理員可以使用 Teams 的受控部署，將安裝檔案發佈到其組織中的所有 Mac，例如 Jamf Pro。</span><span class="sxs-lookup"><span data-stu-id="f5c72-158">IT admins can use managed deployment of Teams to distribute the installation files to all Macs in their organization, such as Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-159">如果您在安裝 PKG 時遇到問題，請告訴我們。</span><span class="sxs-lookup"><span data-stu-id="f5c72-159">If you experience issues installing the PKG, let us know.</span></span> <span data-ttu-id="f5c72-160">請在本文結尾的 **意見反應** 一節中，按一下 [產品意見反應]。</span><span class="sxs-lookup"><span data-stu-id="f5c72-160">In the **Feedback** section at the end of this article, click **Product feedback**.</span></span>

### <a name="linux"></a><span data-ttu-id="f5c72-161">Linux</span><span class="sxs-lookup"><span data-stu-id="f5c72-161">Linux</span></span>

<span data-ttu-id="f5c72-162">使用者能夠安裝 `.deb` 和 `.rpm` 格式的原生 Linux 套件。</span><span class="sxs-lookup"><span data-stu-id="f5c72-162">Users will be able to install native Linux packages in `.deb` and `.rpm` formats.</span></span> <span data-ttu-id="f5c72-163">安裝 DEB 或 RPM 套件時會自動安裝套件存放庫。</span><span class="sxs-lookup"><span data-stu-id="f5c72-163">Installing the DEB or RPM package will automatically install the package repository.</span></span>

- <span data-ttu-id="f5c72-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span><span class="sxs-lookup"><span data-stu-id="f5c72-164">DEB `https://packages.microsoft.com/repos/ms-teams stable main`</span></span>
- <span data-ttu-id="f5c72-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span><span class="sxs-lookup"><span data-stu-id="f5c72-165">RPM `https://packages.microsoft.com/yumrepos/ms-teams`</span></span>

<span data-ttu-id="f5c72-166">使用系統套件管理員來啟用自動更新所需的簽署金鑰也會自動安裝。</span><span class="sxs-lookup"><span data-stu-id="f5c72-166">The signing key to enable auto-updating using the system's package manager is installed automatically.</span></span> <span data-ttu-id="f5c72-167">不過，也可以在以下位置找到：<https://packages.microsoft.com/keys/microsoft.asc>。</span><span class="sxs-lookup"><span data-stu-id="f5c72-167">However, it can also be found at: <https://packages.microsoft.com/keys/microsoft.asc>.</span></span> <span data-ttu-id="f5c72-168">Microsoft Teams 會每月傳送，而且如果存放庫安裝正確，則系統套件管理員會使用與系統中其他套件相同的方式處理自動更新。</span><span class="sxs-lookup"><span data-stu-id="f5c72-168">Microsoft Teams ships monthly and if the repository was installed correctly, then your system package manager should handle auto-updating in the same way as other packages on the system.</span></span>

> [!NOTE] 
> <span data-ttu-id="f5c72-169">如果您發現錯誤，請使用用戶端內部的 `Report a Problem` 提交錯誤。</span><span class="sxs-lookup"><span data-stu-id="f5c72-169">If you find a bug, submit it using `Report a Problem` from within the client.</span></span> <span data-ttu-id="f5c72-170">如需已知問題，請參閱[在貴組織中支援 Teams](/MicrosoftTeams/troubleshoot/teams-welcome)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-170">For known issues, see [Support Teams in your organization](/MicrosoftTeams/troubleshoot/teams-welcome).</span></span>
> <span data-ttu-id="f5c72-171">如需適用於 Teams 的 Linux 支援，您可以使用 [Microsoft Q&A 上的 Linux 論壇支援頻道](/answers/topics/teams.html)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-171">For Teams for Linux support you can use the [Linux forum support channel on Microsoft Q&A](/answers/topics/teams.html).</span></span> <span data-ttu-id="f5c72-172">請務必在張貼問題時使用 `teams-linux` 標籤。</span><span class="sxs-lookup"><span data-stu-id="f5c72-172">Be sure to use the `teams-linux` tag when posting questions.</span></span> 

#### <a name="install-teams-using-deb-package"></a><span data-ttu-id="f5c72-173">使用 DEB 套件安裝 Teams</span><span class="sxs-lookup"><span data-stu-id="f5c72-173">Install Teams using DEB package</span></span>

1. <span data-ttu-id="f5c72-174">從 <https://aka.ms/getteams> 下載套件。</span><span class="sxs-lookup"><span data-stu-id="f5c72-174">Download the package from <https://aka.ms/getteams>.</span></span>
2. <span data-ttu-id="f5c72-175">利用下列其中一個選項進行安裝：</span><span class="sxs-lookup"><span data-stu-id="f5c72-175">Install using one of the following:</span></span>
    - <span data-ttu-id="f5c72-176">開啟相關套件管理工具，並進行自助式 Linux 應用程式安裝程序。</span><span class="sxs-lookup"><span data-stu-id="f5c72-176">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="f5c72-177">或者，如果您喜歡終端機，請輸入： `sudo dpkg -i **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="f5c72-177">Or if you love Terminal, type: `sudo dpkg -i **teams download file**`</span></span>

<span data-ttu-id="f5c72-178">您可以輸入 `teams`，以透過活動或終端機來啟動 Teams。</span><span class="sxs-lookup"><span data-stu-id="f5c72-178">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-teams-using-rpm-package"></a><span data-ttu-id="f5c72-179">使用 RPM 套件來安裝 Teams</span><span class="sxs-lookup"><span data-stu-id="f5c72-179">Install Teams using RPM package</span></span>

1. <span data-ttu-id="f5c72-180">從 <https://aka.ms/getteams> 下載套件。</span><span class="sxs-lookup"><span data-stu-id="f5c72-180">Download the package from <https://aka.ms/getteams>.</span></span>
2. <span data-ttu-id="f5c72-181">利用下列其中一個選項進行安裝：</span><span class="sxs-lookup"><span data-stu-id="f5c72-181">Install using one of the following:</span></span>
    - <span data-ttu-id="f5c72-182">開啟相關套件管理工具，並進行自助式 Linux 應用程式安裝程序。</span><span class="sxs-lookup"><span data-stu-id="f5c72-182">Open the relevant package management tool and go through the self-guided Linux app installation process.</span></span>
    - <span data-ttu-id="f5c72-183">或者，如果您喜歡終端機，請輸入： `sudo yum install **teams download file**`</span><span class="sxs-lookup"><span data-stu-id="f5c72-183">Or if you love Terminal, type: `sudo yum install **teams download file**`</span></span>

<span data-ttu-id="f5c72-184">您可以輸入 `teams`，以透過活動或終端機來啟動 Teams。</span><span class="sxs-lookup"><span data-stu-id="f5c72-184">You can launch Teams via Activities or via Terminal by typing `teams`.</span></span>

#### <a name="install-manually-from-the-command-line"></a><span data-ttu-id="f5c72-185">從命令列手動安裝</span><span class="sxs-lookup"><span data-stu-id="f5c72-185">Install manually from the command line</span></span>

<span data-ttu-id="f5c72-186">在 Debian 和 Ubuntu 發行版本上手動安裝：</span><span class="sxs-lookup"><span data-stu-id="f5c72-186">Install manually on Debian and Ubuntu distributions:</span></span>

```bash
curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -

sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/ms-teams stable main" > /etc/apt/sources.list.d/teams.list'

sudo apt update
sudo apt install teams
```

<span data-ttu-id="f5c72-187">在 RHEL、Fedora 和 CentOS 發行版本中手動安裝：</span><span class="sxs-lookup"><span data-stu-id="f5c72-187">Install manually on RHEL, Fedora and CentOS based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/teams.repo'

sudo dnf check-update
sudo dnf install teams
```

<span data-ttu-id="f5c72-188">或者，若要使用 yum (而不是 dnf)：</span><span class="sxs-lookup"><span data-stu-id="f5c72-188">Alternatively, to use yum instead of dnf:</span></span>

```bash
yum check-update
sudo yum install teams
```

<span data-ttu-id="f5c72-189">在 openSUSE 發行版本上手動安裝：</span><span class="sxs-lookup"><span data-stu-id="f5c72-189">Install manually on openSUSE based distributions:</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc

sudo sh -c 'echo -e "[teams]\nname=teams\nbaseurl=https://packages.microsoft.com/yumrepos/ms-teams\nenabled=1\nautorefresh=1\nkeeppackages=0\ntype=rpm-md\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/teams.repo'

sudo zypper refresh
sudo zypper install teams
```

## <a name="web-client"></a><span data-ttu-id="f5c72-190">Web 用戶端</span><span class="sxs-lookup"><span data-stu-id="f5c72-190">Web client</span></span>

<span data-ttu-id="f5c72-191">Web 用戶端 ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) 是功能完整的用戶端，可在多種瀏覽器中使用。</span><span class="sxs-lookup"><span data-stu-id="f5c72-191">The web client ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) is a full, functional client that can be used from a variety of browsers.</span></span> <span data-ttu-id="f5c72-192">Web 用戶端使用 webRTC 來支援通話和會議，因此不需要外掛程式或任何下載，即可在網頁瀏覽器中執行 Teams。</span><span class="sxs-lookup"><span data-stu-id="f5c72-192">The web client supports Calling and Meetings by using webRTC, so there is no plug-in or download required to run Teams in a web browser.</span></span> <span data-ttu-id="f5c72-193">瀏覽器必須設定為允許第三方 Cookie。</span><span class="sxs-lookup"><span data-stu-id="f5c72-193">The browser must be configured to allow third-party cookies.</span></span>

[!INCLUDE [browser-support](includes/browser-support.md)]

<span data-ttu-id="f5c72-194">Web 用戶端會在連線至 [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) 時執行瀏覽器版本偵測。</span><span class="sxs-lookup"><span data-stu-id="f5c72-194">The web client performs browser version detection upon connecting to [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753).</span></span> <span data-ttu-id="f5c72-195">如果偵測到不受支援的瀏覽器版本，則會封鎖 Web 介面的存取權，並建議使用者下載桌面版用戶端或行動裝置應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-195">If an unsupported browser version is detected, it will block access to the web interface and recommend that the user download the desktop client or mobile app.</span></span>

## <a name="mobile-clients"></a><span data-ttu-id="f5c72-196">行動裝置用戶端</span><span class="sxs-lookup"><span data-stu-id="f5c72-196">Mobile clients</span></span>

<span data-ttu-id="f5c72-197">Microsoft Teams 行動裝置應用程式適用於 Android 和 iOS，可讓使用者在任何地方參與聊天式對話，並且允許對等音訊通話。</span><span class="sxs-lookup"><span data-stu-id="f5c72-197">The Microsoft Teams mobile apps are available for Android and iOS, and are geared for on-the-go users participating in chat-based conversations and allow peer-to-peer audio calls.</span></span> <span data-ttu-id="f5c72-198">若需行動裝置應用程式，請移至相關的行動裝置商店：Google Play 和 Apple App Store。</span><span class="sxs-lookup"><span data-stu-id="f5c72-198">For mobile apps, go to the relevant mobile stores Google Play and the Apple App Store.</span></span> <span data-ttu-id="f5c72-199">Windows Phone 應用程式已於 2018 年 7 月 20 日停用，已不再適用。</span><span class="sxs-lookup"><span data-stu-id="f5c72-199">The Windows Phone App was retired July 20, 2018 and may no longer work.</span></span>

<span data-ttu-id="f5c72-200">以下說明如何在中國[取得 Android 版 Teams](get-teams-android-in-china.md)。</span><span class="sxs-lookup"><span data-stu-id="f5c72-200">In China, here's how to [get Teams for Android](get-teams-android-in-china.md).</span></span>

<span data-ttu-id="f5c72-201">Microsoft Teams 行動裝置應用程式支援的行動平台如下：</span><span class="sxs-lookup"><span data-stu-id="f5c72-201">Supported mobile platforms for Microsoft Teams mobile apps are the following:</span></span>

- <span data-ttu-id="f5c72-202">**Android**：僅支援 Android 最新的四個主要版本。</span><span class="sxs-lookup"><span data-stu-id="f5c72-202">**Android**: Support is limited to the last four major versions of Android.</span></span> <span data-ttu-id="f5c72-203">發行新的 Android 主要版本時，此新版本和前三個版本都可受到正式支援。</span><span class="sxs-lookup"><span data-stu-id="f5c72-203">When a new major version of Android is released, the new version and the previous three versions are officially supported.</span></span>

- <span data-ttu-id="f5c72-204">**iOS**：僅支援 iOS 最新的兩個主要版本。</span><span class="sxs-lookup"><span data-stu-id="f5c72-204">**iOS**: Support is limited to the two most recent major versions of iOS.</span></span> <span data-ttu-id="f5c72-205">發行新的 iOS 主要版本時，此新版 iOS 和前一版本都可受到正式支援。</span><span class="sxs-lookup"><span data-stu-id="f5c72-205">When a new major version of iOS is released, the new version of iOS and the previous version are officially supported.</span></span>

> [!NOTE]
> <span data-ttu-id="f5c72-206">為了讓 Teams 正常運作，您必須公開使用行動裝置版本。</span><span class="sxs-lookup"><span data-stu-id="f5c72-206">The mobile version must be available to the public in order for Teams to work as expected.</span></span>

<span data-ttu-id="f5c72-207">行動裝置應用程式只可透過各別行動平台的應用程式商店來發行及更新。</span><span class="sxs-lookup"><span data-stu-id="f5c72-207">Mobile apps are distributed and updated through the respective mobile platform’s app store only.</span></span> <span data-ttu-id="f5c72-208">Microsoft 不支援透過 MDM 或側載來發行行動裝置應用程式。</span><span class="sxs-lookup"><span data-stu-id="f5c72-208">Distribution of the mobile apps via MDM or side-loading is not supported by Microsoft.</span></span> <span data-ttu-id="f5c72-209">當行動裝置應用程式安裝在支援的行動裝置平台上之後，在目前版本發行後的三個月內，該版本仍能支援 Teams 行動裝置應用程式本身。</span><span class="sxs-lookup"><span data-stu-id="f5c72-209">Once the mobile app has been installed on a supported mobile platform, the Teams Mobile App itself will be supported provided the version is within three months of the current release.</span></span>

| | | |
|---|---|---|
|![描繪決策點的圖示](media/Get_clients_for_Microsoft_Teams_image4.png)|<span data-ttu-id="f5c72-211">決策點</span><span class="sxs-lookup"><span data-stu-id="f5c72-211">Decision Point</span></span>|<span data-ttu-id="f5c72-212">是否有任何限制會讓使用者無法在其裝置上安裝適當的 Microsoft Teams 用戶端？</span><span class="sxs-lookup"><span data-stu-id="f5c72-212">Are there any restrictions preventing users from installing the appropriate Microsoft Teams client on their devices?</span></span>|
|![描繪後續步驟的圖示](media/Get_clients_for_Microsoft_Teams_image5.png)|<span data-ttu-id="f5c72-214">後續步驟</span><span class="sxs-lookup"><span data-stu-id="f5c72-214">Next Steps</span></span>|<span data-ttu-id="f5c72-215">如果您的組織限制軟體安裝，請確認該程序與 Microsoft Teams 相容。</span><span class="sxs-lookup"><span data-stu-id="f5c72-215">If your organization restricts software installation, make sure that process is compatible with Microsoft Teams.</span></span> <span data-ttu-id="f5c72-216">附註：PC 版用戶端安裝程式不需要系統管理員權限，但這在 Mac 上安裝時是必要的權限。</span><span class="sxs-lookup"><span data-stu-id="f5c72-216">Note: Admin rights are not required for PC client installation but are required for installation on a Mac.</span></span>|
|

## <a name="client-update-management"></a><span data-ttu-id="f5c72-217">用戶端更新管理</span><span class="sxs-lookup"><span data-stu-id="f5c72-217">Client update management</span></span>

<span data-ttu-id="f5c72-218">用戶端目前由 Microsoft Teams 服務自動更新，無需 IT 系統管理員介入。</span><span class="sxs-lookup"><span data-stu-id="f5c72-218">Clients are currently updated automatically by the Microsoft Teams service with no IT administrator intervention required.</span></span> <span data-ttu-id="f5c72-219">一旦有可用的更新，用戶端就會自動下載更新，並且會在應用程式已閒置一段時間後，開始更新程序。</span><span class="sxs-lookup"><span data-stu-id="f5c72-219">If an update is available, the client will automatically download the update and when the app has idled for a period of time, the update process will begin.</span></span>

## <a name="client-side-configurations"></a><span data-ttu-id="f5c72-220">用戶端設定</span><span class="sxs-lookup"><span data-stu-id="f5c72-220">Client-side configurations</span></span>

<span data-ttu-id="f5c72-221">目前，沒有支援的選項可供您透過租用戶系統管理員、PowerShell、群組原則物件或登錄來設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="f5c72-221">Currently, there are no supported options available to configure the client either through the tenant admin, PowerShell, Group Policy Objects or the registry.</span></span>

## <a name="notification-settings"></a><span data-ttu-id="f5c72-222">通知設定</span><span class="sxs-lookup"><span data-stu-id="f5c72-222">Notification settings</span></span>

<span data-ttu-id="f5c72-223">目前沒有可供 IT 系統管理員設定用戶端通知設定的選項。</span><span class="sxs-lookup"><span data-stu-id="f5c72-223">There are currently no options available for IT administrators to configure client-side notification settings.</span></span> <span data-ttu-id="f5c72-224">所有通知選項皆由使用者設定。</span><span class="sxs-lookup"><span data-stu-id="f5c72-224">All notification options are set by the user.</span></span> <span data-ttu-id="f5c72-225">下圖概述預設的用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="f5c72-225">The figure below outlines the default client settings.</span></span>

![通知設定的螢幕擷取畫面。](media/Get_clients_for_Microsoft_Teams_image6.png)

## <a name="sample-powershell-script---inbound-firewall-rule"></a><span data-ttu-id="f5c72-227">PowerShell 指令碼範例 - 輸入防火牆規則</span><span class="sxs-lookup"><span data-stu-id="f5c72-227">Sample PowerShell script - inbound firewall rule</span></span>

<span data-ttu-id="f5c72-228">此指令碼範例必須在系統管理員帳戶權限已提升的用戶端電腦上執行，才能為 c:\users 中的每個使用者資料夾建立新的輸入防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="f5c72-228">This sample script, which needs to run on client computers in the context of an elevated administrator account, will create a new inbound firewall rule for each user folder found in c:\users.</span></span> <span data-ttu-id="f5c72-229">當 Teams 找到此規則時，該規則會防止 Teams 應用程式在使用者第一次從 Teams 進行通話時，提示使用者建立防火牆規則。</span><span class="sxs-lookup"><span data-stu-id="f5c72-229">When Teams finds this rule, it will prevent the Teams application from prompting users to create firewall rules when the users make their first call from Teams.</span></span>

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
